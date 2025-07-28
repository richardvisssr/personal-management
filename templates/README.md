# 📦 Repository Templates

Template bestanden voor consistente project setup en documentatie.

## 📁 Folder Structure

```
templates/
├── readme-templates/           # README templates voor verschillende project types
│   ├── webapp-readme.md       # Web applicatie template
│   ├── api-readme.md          # API/Backend service template
│   ├── fullstack-readme.md    # Full-stack project template
│   └── library-readme.md      # JavaScript/Node library template
│
├── project-configs/           # GitHub project configuratie voorbeelden
│   ├── webapp-project.md     # Project board setup voor web apps
│   ├── api-project.md        # Project board setup voor APIs
│   └── personal-dashboard.md # Personal dashboard configuratie
│
└── github-templates/          # .github folder templates
    ├── issue-templates/       # Issue template varianten
    ├── workflows/            # GitHub Actions workflows
    └── project-settings/     # Project instellingen
```

## 🚀 Quick Start

### Voor een nieuwe Web App:
1. Copy `readme-templates/webapp-readme.md` naar je nieuwe repo
2. Gebruik `project-configs/webapp-project.md` voor project setup
3. Apply labels met: `gh label create --file .github/labels.yml`

### Voor een nieuwe API:
1. Copy `readme-templates/api-readme.md` naar je nieuwe repo  
2. Gebruik `project-configs/api-project.md` voor project setup
3. Extra labels voor API's: endpoint documentation, rate limiting

### Voor Full-Stack projecten:
1. Copy `readme-templates/fullstack-readme.md` naar je nieuwe repo
2. Setup beide frontend én backend project boards
3. Gebruik epic labels voor features die beide kanten raken

## 🏗️ Repository Naming Conventions

### Recommended Pattern:
```
[your-username]-[project-type]-[project-name]
```

### Examples:
```
✅ Good Names:
richard-webapp-portfolio
richard-api-bookstore
richard-fullstack-ecommerce
richard-lib-ui-components
richard-tool-deployment-scripts

❌ Avoid:
my-awesome-app
untitled-project
new-website
test123
```

### Project Type Prefixes:
- `webapp-` - Frontend web applications
- `api-` - Backend APIs and services  
- `fullstack-` - Full-stack applications
- `lib-` - Libraries and packages
- `tool-` - Development tools and scripts
- `docs-` - Documentation projects
- `template-` - Template repositories

## 🎨 Customization Guide

### Modifying Templates:
1. **Copy template** to your new repository
2. **Search and replace** placeholder values:
   - `[PROJECT_NAME]` → Your project name
   - `[YOUR_USERNAME]` → Your GitHub username
   - `[TECH_STACK]` → Your technology choices
   - `[DESCRIPTION]` → Project description

3. **Remove unused sections** - Don't include everything if not needed
4. **Add project-specific** sections as required

### Template Variables:
All templates use these consistent placeholders:

```markdown
[PROJECT_NAME]        # Full project name
[SHORT_DESCRIPTION]   # One-line description  
[YOUR_USERNAME]       # GitHub username
[TECH_STACK]         # Primary technologies used
[LIVE_URL]           # Production URL (if applicable)
[STAGING_URL]        # Staging URL (if applicable)
[API_BASE_URL]       # API endpoint base (for APIs)
```

## 📋 Project Setup Checklist

When creating a new repository:

### Repository Setup:
- [ ] Create repository with descriptive name
- [ ] Add README from appropriate template
- [ ] Copy `.github/` folder from this repository
- [ ] Setup labels: `gh label create --file .github/labels.yml`
- [ ] Create initial commit with basic structure

### Project Board Setup:
- [ ] Create GitHub Project linked to repository
- [ ] Configure board columns (Todo, In Progress, Review, Done)
- [ ] Add custom fields (Priority, Type, Complexity)
- [ ] Create first "Setup" issue to track initial tasks

### Development Environment:
- [ ] Setup local development environment
- [ ] Configure linting and formatting tools
- [ ] Setup testing framework (if applicable)
- [ ] Create development and production deployment processes

### Documentation:
- [ ] Complete README with project-specific information
- [ ] Document API endpoints (for APIs)
- [ ] Create user documentation (for user-facing apps)
- [ ] Setup changelog tracking

## 🔄 Template Updates

### Keeping Templates Current:
1. **Monthly review** - Check if templates need updates
2. **Learn from projects** - Update templates based on real usage
3. **Version control** - Track template changes over time
4. **Feedback loop** - Note what works and what doesn't

### Contributing Template Improvements:
1. Test changes on real projects first
2. Document why changes are beneficial
3. Update all affected templates consistently
4. Update this documentation

## 📖 Usage Examples

### Example 1: New React Web App
```bash
# 1. Create repository
gh repo create richard-webapp-taskmanager --public

# 2. Clone and setup
git clone https://github.com/richard/richard-webapp-taskmanager
cd richard-webapp-taskmanager

# 3. Copy templates
cp ../personal-management/templates/readme-templates/webapp-readme.md README.md
cp -r ../personal-management/.github .github/

# 4. Setup labels and project
gh label create --file .github/labels.yml
```

### Example 2: New Node.js API
```bash
# 1. Create repository  
gh repo create richard-api-inventory --public

# 2. Setup with API template
cp ../personal-management/templates/readme-templates/api-readme.md README.md

# 3. Customize for API-specific needs
# Edit README.md with your API details
```

---

💡 **Pro Tip**: Start with a simple template and add complexity as your project grows. It's easier to add sections than to remove unused ones!