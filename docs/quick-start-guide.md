# 🚀 Quick Start Guide

Get je GitHub projectmanagement systeem operationeel in 30 minuten. Perfect voor als je direct wilt beginnen!

## ⏱️ 30-Minute Setup

### 🎯 Step 1: Repository Setup (5 min)

#### Copy Templates to Your Repository
```bash
# Navigate to your main repository
cd your-main-project

# Copy .github folder (if you have this management repo locally)
cp -r /path/to/personal-management/.github .github/

# Or download files manually from GitHub
# Go to: https://github.com/richardvisssr/personal-management
# Download the .github folder contents
```

#### Install Labels
```bash
# Option A: GitHub CLI (recommended)
gh label create --file .github/labels.yml

# Option B: Manual via GitHub UI
# Go to Issues → Labels → New label (repeat for each label)
```

### 🎯 Step 2: Test Issue Templates (5 min)

#### Create Test Issues
1. **Go to Issues** → New Issue
2. **Verify templates appear**:
   - 📝 Simple Todo
   - 🚀 Feature Request
   - 🐛 Bug Report
   - 📚 Documentation Task

#### Create Your First Real Issue
```markdown
Template: Simple Todo
Title: [TODO] Setup GitHub project management system
Description: Complete the setup and familiarize myself with the workflow
Labels: todo, simple
```

### 🎯 Step 3: Create Personal Dashboard (10 min)

#### Setup Main Project
1. **GitHub Profile** → Projects → New Project
2. **Choose**: Board template
3. **Name**: "Personal Dashboard"  
4. **Description**: "My main task management hub"

#### Configure Board Columns
```
📝 Todo        (Items ready to work on)
🚧 Doing       (Currently working on - max 3)
👀 Review      (Complete, needs verification)
✅ Done        (Finished this week)
```

#### Add Your Test Issue
1. **Open your test issue**
2. **Right sidebar** → Projects → Select "Personal Dashboard"
3. **Drag to "Todo"** column

### 🎯 Step 4: Repository Project (5 min)

#### Create Repository-Specific Project
1. **Your repository** → Projects → Link a project → Create new project
2. **Template**: Board
3. **Name**: "[Repository Name] Tasks"

#### Basic Columns
```
📋 Backlog     (Future items)
🎯 Ready       (This sprint)
🚧 Active      (In development)
✅ Complete    (Done)
```

### 🎯 Step 5: First Workflow Test (5 min)

#### Create and Process an Issue
1. **Create simple task**:
   ```
   Title: [TODO] Write project README
   Template: Simple Todo
   Label: docs, simple
   ```

2. **Add to project**: Link to both Personal Dashboard and Repository project

3. **Move through workflow**:
   - Start: Move to "Doing"
   - Complete: Move to "Done"
   - Close: Mark issue as closed

#### Verify Everything Works
- ✅ Issue created with template
- ✅ Labels applied correctly
- ✅ Issue appears in both projects
- ✅ Can move between columns
- ✅ Issue can be closed

## 🎯 Essential Daily Workflow (5 min/day)

### Morning Routine (2 min)
```
1. Open Personal Dashboard
2. Check "Doing" column - continue or move to "Done"
3. Pick 1-2 items from "Todo" to move to "Doing"
```

### During Work (30 sec per update)
```
When starting: Move issue to "Doing"
When finishing: Move issue to "Done" + close
New ideas: Quick issue creation
```

### Evening (3 min)
```
1. Update status of "Doing" items
2. Move completed work to "Done"
3. Plan tomorrow: ensure 1-2 items ready in "Todo"
```

## 📋 Week 1 Learning Checklist

### Day 1: Basic Setup
- [ ] Install templates and labels
- [ ] Create Personal Dashboard
- [ ] Create first test issue
- [ ] Practice moving issues between columns

### Day 2-3: Issue Creation Practice
- [ ] Create issues using different templates
- [ ] Practice applying appropriate labels
- [ ] Add real work items to your board

### Day 4-5: Workflow Practice
- [ ] Use system for actual work
- [ ] Update issues with progress
- [ ] Close completed issues

### Weekend: First Review
- [ ] Review what was accomplished
- [ ] Clean up "Done" column
- [ ] Plan next week's priorities
- [ ] Note what worked and what didn't

## 🎯 Common First-Week Mistakes

### ❌ Mistake 1: Over-complicating
**Problem**: Trying to use all features immediately  
**Solution**: Start with Simple Todo template only for first week

### ❌ Mistake 2: Perfect Issue Descriptions
**Problem**: Spending too much time writing perfect issues  
**Solution**: Start with basic description, improve over time

### ❌ Mistake 3: Too Many Projects
**Problem**: Creating separate projects for everything  
**Solution**: Start with just Personal Dashboard for first month

### ❌ Mistake 4: Forgetting to Update
**Problem**: Issues getting stale without updates  
**Solution**: Set phone reminder for daily 5-minute update

## 🚀 Quick Wins for Immediate Value

### Win 1: Capture All Ideas (Day 1)
Instead of losing ideas, immediately create Simple Todo issues
```
Example: "[TODO] Research better CSS animations"
Time: 30 seconds
Value: Never lose ideas again
```

### Win 2: Visual Progress (Day 2)
Seeing tasks move from "Todo" → "Done" is motivating
```
Visual feedback of accomplishment
Clear what's completed vs in progress
Sense of momentum and achievement
```

### Win 3: Context Switching (Day 3)
When interrupted, issue comments preserve context
```
Before: "Wait, what was I doing?"
After: Read last comment to immediately resume
```

### Win 4: Priority Clarity (Week 1)
Always know what to work on next
```
Before: Decision fatigue about task selection
After: Clear priority order in "Todo" column
```

## 📱 Mobile Quick Start

### GitHub Mobile App Setup
1. **Download** GitHub mobile app
2. **Login** with your account
3. **Navigate** to your repository
4. **Test** creating and updating issues

### Mobile Workflow
```
Morning Commute: Review dashboard on phone
Lunch Break: Quick status updates via mobile
Evening: Planning tomorrow's priorities
Weekend: Weekly review and cleanup
```

## 🔧 Troubleshooting Quick Fixes

### Issue Templates Not Showing
```bash
# Check file location
ls .github/ISSUE_TEMPLATE/

# Verify files are committed
git status
git add .github/
git commit -m "Add issue templates"
git push
```

### Labels Not Available
```bash
# Re-import labels
gh label create --file .github/labels.yml

# Or create manually via GitHub UI
```

### Project Board Not Working
- Try hard refresh (Ctrl+F5)
- Check browser JavaScript is enabled
- Test in incognito mode
- Use different browser

## 📈 Next Steps After Week 1

### Week 2: Refinement
- Add custom fields (Priority, Type)
- Create calendar view for deadlines  
- Setup repository-specific project

### Week 3: Optimization
- Create more project views (Table view)
- Start using Feature Request template
- Establish weekly review routine

### Week 4: Expansion
- Add second repository to system
- Create cross-project views
- Document your personal customizations

## 🎯 Success Criteria

**After 30 minutes setup, you should have**:
- ✅ Working issue templates
- ✅ Applied label system
- ✅ Functional Personal Dashboard
- ✅ One test issue processed through workflow
- ✅ Understanding of daily routine

**After Week 1, you should be**:
- ✅ Creating 3-5 issues per week
- ✅ Using system daily without thinking
- ✅ Completing and closing issues regularly
- ✅ Feeling more organized and focused

---

🎉 **Congratulations!** You now have a working GitHub projectmanagement system. Focus on consistency over perfection - use it daily and improve gradually!