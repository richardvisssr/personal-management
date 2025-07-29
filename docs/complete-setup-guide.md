# 🔧 Complete Setup Guide

Deze guide leidt je stap-voor-stap door het opzetten van je GitHub-gebaseerde projectmanagement systeem.

## 📋 Voorbereiding

### Benodigdheden
- GitHub account
- [GitHub CLI](https://cli.github.com/) (optioneel maar aanbevolen)
- Git lokaal geïnstalleerd

### Tijd Investment
- **Initial setup**: ~30 minuten
- **Learning curve**: ~1 week om gewend te raken
- **Daily overhead**: ~5 minuten per dag

## 🚀 Stap 1: Repository Setup

### 1.1 Labels Installeren
```bash
# Navigate to your repository
cd your-repository

# Install all labels (requires GitHub CLI)
gh label create --file .github/labels.yml

# Alternative: Manual setup via GitHub UI
# Go to Issues → Labels → New label
```

### 1.2 Issue Templates Verificatie
✅ Controleer dat deze templates werken:
- Go to Issues → New Issue
- Verifieer dat je 4 templates ziet:
  - 📝 Simple Todo
  - 🚀 Feature Request  
  - 🐛 Bug Report
  - 📚 Documentation Task

### 1.3 Pull Request Template
✅ De PR template wordt automatisch geladen bij nieuwe Pull Requests

## 📋 Stap 2: GitHub Projects Setup

### 2.1 Personal Dashboard Project
1. **Ga naar GitHub** → Your profile → Projects → New Project
2. **Kies template**: "Board"
3. **Naam**: "Personal Dashboard"
4. **Beschrijving**: "Overview of all my projects and tasks"

### 2.2 Project Views Configureren
#### Kanban Board View (Default)
- **Columns**: 
  - 📝 `Todo` (todo, simple labels)
  - 🚧 `In Progress` (in-progress label)
  - 👀 `Review` (review label)  
  - ✅ `Done` (done label)

#### Table View
1. Create new view → Table
2. **Columns toevoegen**:
   - Title
   - Status
   - Priority
   - Repository
   - Labels
   - Assignee
   - Created Date

#### Calendar View  
1. Create new view → Calendar
2. **Date field**: Due Date (custom field)
3. Useful voor deadlines en planning

### 2.3 Custom Fields Toevoegen
Add these custom fields to your project:

1. **Priority** (Select)
   - Options: Urgent, High, Medium, Low
   - Colors: Red, Orange, Yellow, Green

2. **Type** (Select)
   - Options: Feature, Bug, Docs, Chore
   - Colors: Blue, Red, Purple, Gray

3. **Complexity** (Select)
   - Options: Simple, Medium, Complex
   - Colors: Light Green, Yellow, Orange

4. **Framework** (Select)
   - Options: React, Vue, Node.js, Django, etc.
   - Customize based on your tech stack

5. **Due Date** (Date)
   - For deadlines and milestones

## 🏷️ Stap 3: Repository-Specific Projects

Voor elk web app project:

### 3.1 Per-Repository Project
1. **Go to repository** → Projects → Link a project → Create new project
2. **Template**: Board
3. **Name**: "[ProjectName] Tasks"  
4. **Link**: Link to repository

### 3.2 Repository Project Columns
- **Backlog**: Ideas en future features
- **Todo**: Ready to work on
- **In Progress**: Currently working
- **Testing**: Ready for testing
- **Done**: Completed

## 🔄 Stap 4: Workflow Setup

### 4.1 Daily Workflow Template
Create this routine:

**Morning (5 min)**:
1. Open Personal Dashboard
2. Check "In Progress" column
3. Move completed items to "Done"
4. Select 1-3 items for today from "Todo"

**During Work**:
1. Update issue comments with progress
2. Move cards between columns
3. Create new issues as ideas come up

**Evening (2 min)**:
1. Update issue status
2. Plan tomorrow's priorities
3. Review what was accomplished

### 4.2 Task Creation Workflow

**For Quick Tasks (< 30 min)**:
1. Use "📝 Simple Todo" template
2. Add to "Todo" column
3. Assign "simple" label

**For Features (> 1 hour)**:
1. Use "🚀 Feature Request" template
2. Break down into subtasks
3. Add to "Backlog" or "Todo"
4. Assign appropriate complexity

**For Bugs**:
1. Use "🐛 Bug Report" template
2. Add priority based on impact
3. Move directly to "Todo" if urgent

## 📊 Stap 5: Monitoring & Analytics

### 5.1 Weekly Review
Every Friday, spend 15 minutes on:

1. **Velocity Check**: How many issues completed?
2. **Bottleneck Analysis**: What's stuck in "In Progress"?
3. **Backlog Grooming**: Clean up old issues
4. **Label Analysis**: Are priorities realistic?

### 5.2 Monthly Cleanup
Every month:

1. **Close stale issues** (>30 days inactive)
2. **Review label usage** (add/remove as needed)
3. **Update project views** based on workflow changes
4. **Archive completed projects**

## 🎨 Stap 6: Customization

### 6.1 Personal Preferences
Customize based on your workstyle:

**Visual Learner**: 
- Add screenshots to all issues
- Use project calendar view extensively
- Create visual project boards

**Detail Oriented**:
- Use extensive issue templates
- Add custom fields for tracking
- Create detailed acceptance criteria

**Speed Focused**:
- Stick to simple todo templates
- Minimal labels
- Quick Kanban updates

### 6.2 Project-Specific Adjustments

**Frontend Projects**:
- Add "ui/ux" labels
- Create design review columns
- Track browser compatibility

**Backend Projects**:
- Add "api", "database" labels  
- Track endpoint documentation
- Monitor performance issues

**Full-Stack Projects**:
- Separate frontend/backend columns
- Use epic labels for large features
- Track integration issues

## 🔧 Stap 7: Automation (Advanced)

### 7.1 GitHub Actions (Optional)
Create automation for:
- Auto-assign labels based on title keywords
- Auto-close stale issues  
- Auto-update project boards
- Generate weekly reports

### 7.2 Integrations
Consider connecting:
- **Time tracking** tools (Toggl, RescueTime)
- **Calendar** integration for deadlines
- **Slack/Discord** for notifications
- **Code quality** tools for automatic issue creation

## ✅ Verification Checklist

After setup, verify:

- [ ] All labels are created and colored correctly
- [ ] Issue templates work when creating new issues
- [ ] Personal dashboard project is configured
- [ ] At least one repository project is set up
- [ ] Custom fields are added and configured
- [ ] You can create and move issues through workflow
- [ ] Views (Board, Table, Calendar) are working
- [ ] You've created your first few test issues
- [ ] Daily workflow is clear and documented

## 🆘 Common Issues & Solutions

**Problem**: Labels not showing in issues
**Solution**: Manually add labels.yml via GitHub UI → Issues → Labels

**Problem**: Project not updating automatically  
**Solution**: Manually link issues to project via issue sidebar

**Problem**: Too many notifications
**Solution**: Adjust notification settings in GitHub Settings → Notifications

**Problem**: Issues feel overwhelming
**Solution**: Start with only Simple Todo template, add complexity gradually

## 📈 Next Steps

Once comfortable with basic setup:

1. **Read** [Daily Workflow Guide](daily-workflow.md)
2. **Explore** [Advanced Features](scaling-guide.md)
3. **Customize** based on your [Project Types](project-switching.md)
4. **Scale up** with [Automation Options](scaling-guide.md)

---

🎉 **Congratulations!** Je GitHub project management systeem is nu klaar voor gebruik. Begin met een paar eenvoudige taken om gewend te raken aan de workflow.