# 📅 Daily Workflow Guide

Geoptimaliseerde dagelijkse routine voor solo web developers die GitHub als projectmanagement systeem gebruiken.

## ⏰ Morning Routine (5-8 minuten)

### 🌅 Start van de Dag (3 min)
1. **Open Personal Dashboard**
   - Navigate to GitHub → Projects → Personal Dashboard
   - Review alle projecten in één overzicht

2. **Triage Gisteren's Werk**
   - Move completed items van "In Progress" naar "Done"
   - Check items die nog in "Review" staan
   - Close finished issues

3. **Plan Vandaag's Focus** 
   - Select 1-3 items from "Todo" column
   - Move selected items naar "In Progress"
   - Assign any missing labels/priorities

### 🎯 Quick Priority Check (2 min)
```
Daily Questions:
- Is er iets urgent dat vandaag af moet?
- Welk project heeft nu mijn focus?
- Zijn er blocked items die ik kan unblokken?
```

### 📋 Context Switching (3 min) 
If switching projects:
1. **Current Project**: Quick status update in active issues
2. **Target Project**: Review project-specific board
3. **Mental Setup**: Read last comment/progress note

## 🚧 During Work (Continuous)

### ⚡ Quick Updates (30 sec each)
**When starting a task**:
- Add comment: "🚧 Starting work on this"
- Move issue to "In Progress"
- Update any time estimates

**When taking a break**:
- Add quick progress note
- Update issue with current status
- Note any blockers encountered

**When context switching**:
- Comment current status/next steps
- Move card if status changed
- Set mental bookmark for return

### 💡 Idea Capture (1 min)
When new ideas come up:

**Quick Ideas** → Simple Todo:
1. GitHub → Issues → New Issue → Simple Todo
2. Add basic description
3. Label: "todo", "simple"  
4. Add to appropriate project

**Complex Ideas** → Feature Request:
1. Capture in "📝 Quick Notes" issue first
2. Later expand to full Feature Request template
3. Break down into smaller issues if needed

### 🐛 Bug Discovery (2 min)
When you find a bug:
1. **Immediate**: Add to "🚨 Bugs Found" tracking issue
2. **Urgent**: Create full Bug Report immediately
3. **Non-urgent**: Schedule for later triage

## 🌅 End of Day Routine (3-5 minuten)

### 📊 Progress Update (2 min)
1. **Update issue status**:
   - Add end-of-day comment to active issues
   - Move completed items to "Done"
   - Update progress on partially finished work

2. **Quick Wins Celebration**:
   - Review "Done" column - what did you accomplish?
   - Close any issues that are truly finished
   - Update project progress if applicable

### 📝 Tomorrow's Setup (3 min)
1. **Review "In Progress"**: 
   - What will you continue tomorrow?
   - Any blockers to resolve overnight?
   - Context notes for smooth restart?

2. **Priority Check**:
   - Are urgent items properly labeled?
   - Is tomorrow's first task clear?
   - Any deadlines approaching?

3. **Quick Backlog Scan**:
   - Any high priority items to promote to "Todo"?
   - Remove/deprioritize items that are no longer relevant

## 🔄 Context Switching Between Projects

### 📂 Leaving Project (2 min)
1. **Current Status Documentation**:
   ```markdown
   ## Status Update [DATE]
   - ✅ Completed: [what you finished]
   - 🚧 In Progress: [current tasks with % done]
   - 🚫 Blocked: [what's blocking you]
   - ➡️ Next: [next logical step]
   ```

2. **Clean Workspace**:
   - Save all work
   - Commit code with meaningful message
   - Update issue with current state

### 📂 Entering Project (3 min)
1. **Context Reload**:
   - Read last status update
   - Review project-specific board
   - Check for any urgent/blocking issues

2. **Environment Setup**:
   - Open relevant code editors
   - Start development servers if needed
   - Review recent commits/changes

3. **Mental Context**:
   - What was I working on?
   - What was the next step?
   - Any new dependencies or changes?

## 🔥 Fire Drill Workflow (Urgent Issues)

### 🚨 When Urgent Issues Arise (5 min max)
1. **Immediate Triage** (1 min):
   - How urgent is "urgent"? (Same day/hour/minute?)
   - Can it wait for current task completion?
   - Is it truly urgent or just feels urgent?

2. **Current Work Protection** (2 min):
   - Document exactly where you are
   - Commit/save all work
   - Add detailed "pause here" comment to current issue

3. **Emergency Task Setup** (2 min):
   - Create bug report or urgent issue
   - Label: "urgent", "bug" (if applicable)
   - Add to "In Progress" immediately
   - Set clear completion criteria

## 📈 Weekly Workflow Optimization

### 🗓️ Friday Review (15 min)
1. **Velocity Analysis** (5 min):
   - How many issues completed this week?
   - What took longer than expected?
   - What was faster than expected?

2. **Process Improvements** (5 min):
   - Which part of workflow was friction?
   - Are labels being used consistently?
   - Are issue descriptions helpful when returning to them?

3. **Next Week Planning** (5 min):
   - What are the top 3 priorities?
   - Any deadlines or dependencies?
   - Capacity planning (realistic expectations)

### 🎯 Workflow Personalization

**For Morning People**:
- Do complex planning in morning routine
- Save afternoon for quick updates
- Schedule heavy context switching early

**For Night Owls**:
- Minimal morning routine
- Detailed end-of-day planning
- Allow flexible start times

**For Interrupters** (many small tasks):
- Use "interrupt log" issue for tracking
- Batch similar interruptions
- Protect core focus blocks

**For Deep Workers** (long focus sessions):
- Minimal mid-day updates
- Longer planning sessions
- Clear "do not disturb" indicators

## 🛠️ Tools & Shortcuts

### Browser Bookmarks
Create bookmark folder "Daily GitHub":
- Personal Dashboard
- Current project board
- Issues assigned to you
- Recent repositories

### GitHub CLI Shortcuts
```bash
# Quick issue creation
gh issue create --title "[TODO] Quick task" --label "todo,simple"

# View your issues
gh issue list --assignee @me

# Quick project update
gh project item-edit [id] --field Status --value "In Progress"
```

### Keyboard Shortcuts (GitHub)
- `C` - Create new issue (when in Issues tab)
- `G I` - Go to Issues
- `G P` - Go to Pull Requests  
- `/` - Search anywhere

## ⚠️ Common Pitfalls & Solutions

**Pitfall**: Forgetting to update issues
**Solution**: Set phone reminder for end-of-day routine

**Pitfall**: Too many items "In Progress"  
**Solution**: Limit to max 3 items, use "Blocked" status

**Pitfall**: Issues become stale/irrelevant
**Solution**: Weekly cleanup, ruthless prioritization

**Pitfall**: Context switching chaos
**Solution**: Always document "where I left off"

**Pitfall**: Perfectionist issue descriptions
**Solution**: Start simple, improve as you learn more

## 📱 Mobile Workflow

For when you're away from desktop:

**GitHub Mobile App**:
- Quick issue triage
- Add comments/updates
- Check notifications
- Review project boards

**Quick Capture**:
- Use phone notes for immediate ideas
- Transfer to GitHub issues when back at desk
- Voice memos for complex ideas

---

🎯 **Remember**: The goal is **productivity**, not perfect process adherence. Adjust this workflow to match your natural rhythms and project needs!