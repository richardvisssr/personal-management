# New Issue Template Guide

This guide explains how to create new issue templates for different project types or workflows.

## Template Structure

GitHub issue templates use YAML frontmatter to define form fields. Here's the basic structure:

```yaml
name: Template Name
description: Brief description of what this template is for
title: "[PREFIX] "
labels: ["label1", "label2"]
assignees:
  - richardvisssr
body:
  - type: dropdown
    id: unique_id
    attributes:
      label: Field Label
      description: Help text for this field
      options:
        - Option 1
        - Option 2
    validations:
      required: true
  
  - type: textarea
    id: description
    attributes:
      label: Description
      description: Detailed description
      placeholder: Placeholder text
    validations:
      required: true
```

## Available Field Types

### Dropdown
```yaml
- type: dropdown
  id: priority
  attributes:
    label: Priority Level
    options:
      - High
      - Medium
      - Low
  validations:
    required: true
```

### Text Input
```yaml
- type: input
  id: deadline
  attributes:
    label: Deadline
    placeholder: "YYYY-MM-DD"
  validations:
    required: false
```

### Textarea
```yaml
- type: textarea
  id: description
  attributes:
    label: Detailed Description
    description: Provide context and requirements
    placeholder: Describe what needs to be done...
  validations:
    required: true
```

### Checkboxes
```yaml
- type: checkboxes
  id: prerequisites
  attributes:
    label: Prerequisites
    description: What needs to be completed first?
    options:
      - label: Research completed
        required: false
      - label: Resources gathered
        required: true
```

## Creating a New Template

1. **Plan the Template**
   - Identify the project type or workflow
   - List required information fields
   - Determine appropriate labels and prefixes

2. **Create the Template File**
   ```bash
   touch .github/ISSUE_TEMPLATE/new-template.yml
   ```

3. **Define the Structure**
   - Add name, description, and title prefix
   - Set appropriate labels
   - Design form fields for required information

4. **Test the Template**
   - Create a test issue using the new template
   - Verify all fields work correctly
   - Adjust field types and validation as needed

5. **Update Documentation**
   - Add template to main README.md
   - Update relevant documentation sections
   - Add to project workflow guides

## Example: Study Session Template

```yaml
name: 📚 Study Session
description: Plan and track study sessions
title: "[STUDY] "
labels: ["learning", "study"]
assignees:
  - richardvisssr
body:
  - type: dropdown
    id: subject
    attributes:
      label: Subject Area
      options:
        - Computer Science
        - Mathematics
        - Research Methods
        - Academic Writing
        - Other
    validations:
      required: true
  
  - type: input
    id: duration
    attributes:
      label: Planned Duration
      placeholder: "e.g., 2 hours"
    validations:
      required: true
  
  - type: textarea
    id: topics
    attributes:
      label: Topics to Cover
      placeholder: |
        - Topic 1
        - Topic 2
        - Topic 3
    validations:
      required: true
  
  - type: textarea
    id: resources
    attributes:
      label: Study Resources
      description: Books, papers, videos, etc.
      placeholder: List resources you'll use
    validations:
      required: false
```

## Best Practices

### Design Principles
- **Keep it simple**: Only include essential fields
- **Be specific**: Use clear, descriptive labels
- **Provide guidance**: Include helpful descriptions and placeholders
- **Set appropriate defaults**: Use smart default values where possible

### Field Guidelines
- **Required vs Optional**: Only mark truly essential fields as required
- **Dropdown vs Text**: Use dropdowns for predefined options, text for open-ended input
- **Validation**: Add validation to prevent common mistakes
- **Placeholder Text**: Provide examples of expected input format

### Label Strategy
- **Consistent Naming**: Use consistent label naming conventions
- **Color Coding**: Assign meaningful colors to label categories
- **Hierarchy**: Create label hierarchies for better organization
- **Automation**: Consider labels that trigger automation workflows

## Integration with Automation

### Automatic Labeling
Templates can trigger automatic actions based on selected options:

```yaml
# In workflow file
if: contains(github.event.issue.labels.*.name, 'study')
```

### Cross-Repository Sync
Templates can be designed to work with repository synchronization:

```yaml
- type: input
  id: related_repo
  attributes:
    label: Related Repository
    description: If this relates to another repo
```

### Reporting Integration
Include fields that support automated reporting:

```yaml
- type: dropdown
  id: time_estimate
  attributes:
    label: Time Estimate
    options:
      - "< 1 hour"
      - "1-4 hours"
      - "1-3 days"
      - "1+ weeks"
```

## Maintenance

### Regular Review
- Monitor template usage and effectiveness
- Gather feedback on missing fields or confusion
- Update options based on evolving needs
- Remove unused or ineffective templates

### Version Control
- Document template changes in commit messages
- Consider template versioning for major changes
- Maintain backward compatibility when possible
- Archive old templates rather than deleting them

### Documentation Updates
- Keep README.md links current
- Update workflow documentation
- Maintain integration guides
- Update automation workflows as needed