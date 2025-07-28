# Repository Integration Guide

This guide explains how to integrate the personal management system with other repositories, particularly EnableLens projects.

## Integration Strategies

### 1. Issue Synchronization

#### Automatic Issue Creation
Create personal management issues when issues are created in linked repositories:

```yaml
# .github/workflows/sync-issues.yml
name: Sync Issues from External Repos
on:
  repository_dispatch:
    types: [external-issue-created]

jobs:
  create-personal-issue:
    runs-on: ubuntu-latest
    steps:
      - name: Create Personal Management Issue
        uses: actions/github-script@v6
        with:
          script: |
            const { data: issue } = await github.rest.issues.create({
              owner: 'richardvisssr',
              repo: 'personal-management',
              title: `[SYNC] ${context.payload.client_payload.title}`,
              body: `
                **Synced from**: ${context.payload.client_payload.repo}
                **Original Issue**: ${context.payload.client_payload.url}
                
                ${context.payload.client_payload.body}
              `,
              labels: ['synced', context.payload.client_payload.project]
            });
```

#### Status Updates
Keep issues in sync when status changes:

```yaml
# In source repository
name: Notify Personal Management
on:
  issues:
    types: [closed, reopened, labeled]

jobs:
  notify:
    runs-on: ubuntu-latest
    steps:
      - name: Send Repository Dispatch
        uses: peter-evans/repository-dispatch@v2
        with:
          token: ${{ secrets.PERSONAL_REPO_TOKEN }}
          repository: richardvisssr/personal-management
          event-type: external-issue-updated
          client-payload: |
            {
              "action": "${{ github.event.action }}",
              "issue_number": ${{ github.event.issue.number }},
              "issue_url": "${{ github.event.issue.html_url }}",
              "repository": "${{ github.repository }}"
            }
```

### 2. Project Board Integration

#### Cross-Repository Project Boards
Use GitHub Projects (beta) to aggregate issues from multiple repositories:

1. Create a project board in personal-management
2. Add repositories to the project
3. Configure automation rules
4. Set up custom fields for tracking

#### Automation Rules Example
```yaml
# Project automation
- when: item.assignee is richardvisssr
  then: set status to "In Progress"
- when: item.labels includes "enablelens"
  then: set priority to "High"
- when: item.is_closed
  then: set status to "Done"
```

### 3. Webhook Configuration

#### Setting Up Webhooks
For real-time integration, set up webhooks in source repositories:

1. Go to repository Settings → Webhooks
2. Add webhook URL: `https://api.github.com/repos/richardvisssr/personal-management/dispatches`
3. Select events: Issues, Pull requests, Pushes
4. Add secret for security

#### Webhook Handler
```yaml
# .github/workflows/webhook-handler.yml
name: Handle External Webhooks
on:
  repository_dispatch:
    types: [webhook-*]

jobs:
  process-webhook:
    runs-on: ubuntu-latest
    steps:
      - name: Process EnableLens Update
        if: contains(github.event.action, 'enablelens')
        run: |
          echo "Processing EnableLens webhook"
          # Custom processing logic here
```

## Repository-Specific Integration

### EnableLens Website
```yaml
# enablelens/website/.github/workflows/sync-to-personal.yml
name: Sync to Personal Management
on:
  issues:
    types: [opened, closed]
  pull_request:
    types: [opened, merged]

jobs:
  sync:
    runs-on: ubuntu-latest
    steps:
      - name: Sync to Personal Repo
        uses: peter-evans/repository-dispatch@v2
        with:
          token: ${{ secrets.PERSONAL_REPO_TOKEN }}
          repository: richardvisssr/personal-management
          event-type: enablelens-website-update
          client-payload: |
            {
              "type": "${{ github.event_name }}",
              "action": "${{ github.event.action }}",
              "number": "${{ github.event.number }}",
              "title": "${{ github.event.issue.title || github.event.pull_request.title }}",
              "url": "${{ github.event.issue.html_url || github.event.pull_request.html_url }}"
            }
```

### EnableLens Chrome Extension
```yaml
# enablelens/extension/.github/workflows/sync-to-personal.yml
name: Sync Extension Progress
on:
  push:
    branches: [main]
  issues:
    types: [opened, closed]
  release:
    types: [published]

jobs:
  sync:
    runs-on: ubuntu-latest
    steps:
      - name: Sync Extension Progress
        uses: peter-evans/repository-dispatch@v2
        with:
          token: ${{ secrets.PERSONAL_REPO_TOKEN }}
          repository: richardvisssr/personal-management
          event-type: enablelens-extension-update
          client-payload: |
            {
              "type": "${{ github.event_name }}",
              "ref": "${{ github.ref }}",
              "sha": "${{ github.sha }}"
            }
```

## Required Secrets

Set up these secrets in your repositories:

1. **PERSONAL_REPO_TOKEN**: Personal access token with repo permissions
2. **WEBHOOK_SECRET**: Secret for webhook verification
3. **GITHUB_TOKEN**: Default token (usually available automatically)

## Testing Integration

### Manual Testing
1. Create a test issue in source repository
2. Verify issue appears in personal management
3. Update issue status and check sync
4. Close issue and verify completion

### Automated Testing
```yaml
# .github/workflows/test-integration.yml
name: Test Repository Integration
on:
  workflow_dispatch:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Test Issue Sync
        uses: actions/github-script@v6
        with:
          script: |
            // Create test issue
            // Verify sync worked
            // Clean up test data
```

## Troubleshooting

### Common Issues
1. **Token permissions**: Ensure token has correct scopes
2. **Rate limiting**: Implement retry logic and delays
3. **Webhook failures**: Check webhook delivery logs
4. **Sync conflicts**: Handle duplicate issues gracefully

### Monitoring
- Set up alerts for failed workflows
- Monitor webhook delivery success rates
- Track sync accuracy and performance
- Regular review of integration effectiveness