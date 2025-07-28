# 📋 Project Configuration Examples

Ready-to-use configuraties voor verschillende types GitHub Projects, geoptimaliseerd voor solo web development.

## 🎯 Personal Dashboard Configuration

### Project Settings
```yaml
Name: "Personal Dashboard"
Description: "Cross-project task management and priority overview"
Visibility: Private
Template: Board
README: "Central hub for all my development projects and tasks"
```

### Board Configuration
#### Columns
```yaml
Columns:
  - name: "🔥 Today"
    description: "Maximum 3 items - today's focus"
    automation: "manual"
    
  - name: "📅 This Week"  
    description: "Weekly commitments across all projects"
    automation: "manual"
    
  - name: "🚧 In Progress"
    description: "Active work across repositories"
    automation: "auto-add when status changes to in-progress"
    
  - name: "👀 Review/Waiting"
    description: "Completed work awaiting feedback/review"
    automation: "auto-add when labeled 'review'"
    
  - name: "✅ Done"
    description: "Completed this week - archive monthly"
    automation: "auto-add when issue closed"
```

#### Custom Fields
```yaml
Custom Fields:
  - name: "Priority"
    type: "select"
    options:
      - name: "🔴 Urgent"
        color: "#d73027"
      - name: "🟠 High"  
        color: "#fc8d59"
      - name: "🟡 Medium"
        color: "#fee08b"
      - name: "🟢 Low"
        color: "#91cf60"
        
  - name: "Project"
    type: "select"
    options:
      - name: "📱 Portfolio"
        color: "#ff6b6b"
      - name: "🛒 E-commerce"
        color: "#4ecdc4"
      - name: "📊 Analytics"
        color: "#45b7d1"
      - name: "🔧 DevTools"
        color: "#96ceb4"
      - name: "📚 Learning"
        color: "#ffeaa7"
        
  - name: "Type"
    type: "select"
    options:
      - name: "🚀 Feature"
        color: "#0052cc"
      - name: "🐛 Bug"
        color: "#d73027"  
      - name: "📚 Docs"
        color: "#1d76db"
      - name: "🔧 Chore"
        color: "#fef2c0"
        
  - name: "Due Date"
    type: "date"
    description: "For deadlines and milestones"
```

### Views Configuration
```yaml
Views:
  - name: "📊 Dashboard"
    type: "board"
    group_by: "Status"
    sort: ["Priority", "Due Date"]
    filter: "status:open"
    
  - name: "📅 Calendar"
    type: "calendar"
    date_field: "Due Date"
    color_by: "Priority"
    filter: "has:due-date"
    
  - name: "📋 All Tasks"
    type: "table"
    columns: ["Title", "Status", "Priority", "Project", "Due Date", "Labels"]
    sort: ["Priority", "Due Date"]
    group_by: "Project"
    
  - name: "🚀 This Sprint"
    type: "board"
    filter: "label:current-sprint OR column:'Today' OR column:'This Week'"
    sort: "Priority"
```

## 🚀 Web App Project Configuration

### Project Settings
```yaml
Name: "[Repository Name] Development"
Description: "Feature development and task tracking for [repository name]"
Visibility: Private (or Public for open source)
Template: Board
Linked Repositories: ["owner/repository-name"]
```

### Board Configuration
#### Columns
```yaml
Columns:
  - name: "📋 Backlog"
    description: "Future features and improvements"
    automation: "auto-add new issues"
    
  - name: "🎯 Sprint Ready"
    description: "Defined, estimated, ready to start"
    automation: "manual"
    
  - name: "🚧 Development"
    description: "In active development"
    automation: "auto-add when PR opened"
    
  - name: "🧪 Testing"
    description: "Development complete, testing needed"
    automation: "auto-add when labeled 'testing'"
    
  - name: "👀 Code Review"  
    description: "PR created, awaiting review"
    automation: "auto-add when PR ready for review"
    
  - name: "🚀 Staging"
    description: "Deployed to staging, final validation"
    automation: "auto-add when deployed to staging"
    
  - name: "✅ Released"
    description: "In production, feature complete"
    automation: "auto-add when PR merged to main"
```

#### Custom Fields
```yaml
Custom Fields:
  - name: "Frontend/Backend"
    type: "select"
    options:
      - name: "🎨 Frontend"
        color: "#ff6b6b"
      - name: "⚙️ Backend"
        color: "#4ecdc4"
      - name: "🔄 Full-Stack"
        color: "#a29bfe"
      - name: "📱 Mobile"
        color: "#00b894"
        
  - name: "Framework"
    type: "select"
    options:
      - name: "⚛️ React"
        color: "#61dafb"
      - name: "💚 Vue.js"
        color: "#4fc08d"
      - name: "🔺 Angular"
        color: "#dd0031"
      - name: "🟢 Node.js"
        color: "#68a063"
      - name: "🐍 Python"
        color: "#306998"
        
  - name: "Complexity"
    type: "select"
    options:
      - name: "🟢 Simple"
        color: "#00b894"
        description: "< 2 hours"
      - name: "🟡 Medium"
        color: "#fdcb6e"
        description: "2-8 hours"
      - name: "🟠 Complex"
        color: "#e17055"
        description: "> 8 hours"
        
  - name: "Epic"
    type: "select"
    options:
      - name: "🔐 Authentication"
        color: "#6c5ce7"
      - name: "💳 Payments"
        color: "#fd79a8"
      - name: "📊 Dashboard"
        color: "#00cec9"
      - name: "🎨 UI Redesign"
        color: "#e84393"
        
  - name: "Story Points"
    type: "number"
    description: "Effort estimation (1-13 Fibonacci)"
```

### Views Configuration
```yaml
Views:
  - name: "🏃 Development Flow"
    type: "board"
    group_by: "Status"
    sort: "Priority"
    filter: "status:open"
    
  - name: "🎨 Frontend Tasks"
    type: "board"
    filter: "Frontend/Backend:'Frontend'"
    sort: ["Priority", "Complexity"]
    
  - name: "⚙️ Backend Tasks"
    type: "board"
    filter: "Frontend/Backend:'Backend'"
    sort: ["Priority", "Complexity"]
    
  - name: "📊 Sprint Planning"
    type: "table"
    columns: ["Title", "Complexity", "Story Points", "Epic", "Framework"]
    sort: "Story Points"
    group_by: "Epic"
    
  - name: "🚀 Release Planning"
    type: "timeline"
    start_date: "Created"
    target_date: "Due Date"
    group_by: "Epic"
    color_by: "Priority"
```

## 🔧 API Development Project Configuration

### Project Settings
```yaml
Name: "[API Name] Development"
Description: "API development, documentation, and testing"
Visibility: Private
Template: Board
Linked Repositories: ["owner/api-repository"]
```

### Board Configuration
```yaml
Columns:
  - name: "📋 API Backlog"
    description: "Endpoint requests and improvements"
    
  - name: "📝 Specification"
    description: "API design and documentation"
    
  - name: "🔧 Implementation"  
    description: "Coding endpoints and logic"
    
  - name: "🧪 Testing"
    description: "Unit, integration, and API testing"
    
  - name: "📚 Documentation"
    description: "API docs and examples"
    
  - name: "🚀 Deployed"
    description: "Live in production"
```

### Custom Fields
```yaml
Custom Fields:
  - name: "HTTP Method"
    type: "select"
    options:
      - name: "GET"
        color: "#00b894"
      - name: "POST"
        color: "#0984e3"
      - name: "PUT"
        color: "#fdcb6e"
      - name: "DELETE"
        color: "#e17055"
      - name: "PATCH"
        color: "#a29bfe"
        
  - name: "API Version"
    type: "select"
    options:
      - name: "v1"
        color: "#ddd"
      - name: "v2"
        color: "#74b9ff"
      - name: "v3"
        color: "#fd79a8"
        
  - name: "Authentication"
    type: "select"
    options:
      - name: "🔓 Public"
        color: "#00b894"
      - name: "🔑 API Key"
        color: "#fdcb6e"
      - name: "🔐 JWT"
        color: "#e17055"
      - name: "👤 User Auth"
        color: "#6c5ce7"
```

## 🏭 Full-Stack Project Configuration

### Project Settings
```yaml
Name: "[App Name] Full-Stack Development"
Description: "Complete application development - frontend + backend"
Visibility: Private
Template: Board
Linked Repositories: ["owner/fullstack-app"]
```

### Board Configuration
```yaml
Columns:
  - name: "💡 Ideas"
    description: "Feature ideas and user stories"
    
  - name: "📋 Planned"
    description: "Defined features ready for development"
    
  - name: "🎨 Frontend Dev"
    description: "UI/UX development in progress"
    
  - name: "⚙️ Backend Dev"
    description: "API/server development in progress"
    
  - name: "🔄 Integration"
    description: "Connecting frontend + backend"
    
  - name: "🧪 Testing"
    description: "E2E and integration testing"
    
  - name: "🚀 Production"
    description: "Deployed and live"
```

### Custom Fields
```yaml
Custom Fields:
  - name: "Component"
    type: "select"
    options:
      - name: "🎨 UI Component"
        color: "#ff6b6b"
      - name: "📱 Page/View"
        color: "#4ecdc4"
      - name: "🔌 API Endpoint"
        color: "#45b7d1"
      - name: "🗄️ Database"
        color: "#96ceb4"
      - name: "🔐 Auth/Security"
        color: "#fd79a8"
      - name: "🧪 Testing"
        color: "#fdcb6e"
        
  - name: "User Impact"
    type: "select"
    options:
      - name: "🔥 High Impact"
        color: "#e17055"
        description: "Core user functionality"
      - name: "🟡 Medium Impact"
        color: "#fdcb6e"
        description: "Improves experience"
      - name: "🟢 Low Impact"
        color: "#00b894"
        description: "Nice to have"
        
  - name: "Technical Debt"
    type: "select"
    options:
      - name: "🟢 Clean"
        color: "#00b894"
      - name: "🟡 Some Debt"
        color: "#fdcb6e"
      - name: "🔴 High Debt"
        color: "#e17055"
```

## 🎨 Workflow Automation Examples

### GitHub Actions Integration
```yaml
# .github/workflows/project-automation.yml
name: Project Board Automation

on:
  issues:
    types: [opened, closed, labeled]
  pull_request:
    types: [opened, closed, merged]

jobs:
  update-project:
    runs-on: ubuntu-latest
    steps:
      - name: Add issue to project
        if: github.event.action == 'opened'
        run: |
          gh project item-add [PROJECT_ID] --content-id ${{ github.event.issue.node_id }}
          
      - name: Move to "In Progress" when PR opened
        if: github.event.action == 'opened' && github.event_name == 'pull_request'
        run: |
          gh project item-edit [ITEM_ID] --field Status --value "In Progress"
          
      - name: Move to "Done" when PR merged
        if: github.event.pull_request.merged == true
        run: |
          gh project item-edit [ITEM_ID] --field Status --value "Done"
```

### Auto-labeling Rules
```yaml
# Label automation based on title patterns
Rules:
  - pattern: "[BUG]"
    labels: ["bug", "high"]
    status: "Todo"
    
  - pattern: "[FEATURE]"  
    labels: ["feature", "medium"]
    status: "Backlog"
    
  - pattern: "[TODO]"
    labels: ["todo", "simple"]
    status: "Todo"
    
  - pattern: "[DOCS]"
    labels: ["docs", "low"]
    status: "Backlog"
```

## 🔄 Template Deployment Script

```bash
#!/bin/bash
# deploy-project-config.sh

PROJECT_NAME=$1
PROJECT_TYPE=$2  # "webapp", "api", "fullstack", "dashboard"

echo "Creating GitHub project: $PROJECT_NAME"

# Create project
gh project create --title "$PROJECT_NAME" --body "Auto-generated project for $PROJECT_NAME"

# Add custom fields based on type
if [ "$PROJECT_TYPE" = "webapp" ]; then
  gh project field-create --project-id $PROJECT_ID --name "Frontend/Backend" --type select
  gh project field-create --project-id $PROJECT_ID --name "Framework" --type select
  gh project field-create --project-id $PROJECT_ID --name "Complexity" --type select
elif [ "$PROJECT_TYPE" = "api" ]; then
  gh project field-create --project-id $PROJECT_ID --name "HTTP Method" --type select
  gh project field-create --project-id $PROJECT_ID --name "API Version" --type select
elif [ "$PROJECT_TYPE" = "dashboard" ]; then
  gh project field-create --project-id $PROJECT_ID --name "Priority" --type select
  gh project field-create --project-id $PROJECT_ID --name "Project" --type select
fi

echo "Project created successfully: $PROJECT_NAME"
```

---

💡 **Pro Tip**: Start with one of these templates and customize based on your specific needs. Copy the configuration that matches your project type and adapt the fields/columns to your workflow!