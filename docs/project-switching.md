# 🔄 Project Switching Guide

Efficiënt wisselen tussen meerdere web development projecten zonder context verlies of workflow onderbreking.

## 🎯 Multi-Project Overview Strategy

### Personal Dashboard Setup
**Central Hub**: One project board that aggregates all repositories  
**Purpose**: Daily planning and cross-project priority management

#### Dashboard Structure
```
📊 Personal Dashboard Project:
├── 🔥 Today's Focus (max 3 items across all projects)
├── 📅 This Week (weekly commitment across projects)  
├── 🚧 In Progress (active work across repositories)
├── 👀 Review/Waiting (items needing external input)
└── ✅ Done This Week (celebration and velocity tracking)
```

#### Custom Fields for Multi-Project View
```
Project Field (Select):
- 📱 Portfolio Website
- 🛒 E-commerce Platform  
- 📊 Analytics Dashboard
- 🔧 DevTools Library
- 📚 Learning Projects

Technology Field (Select):
- ⚛️ React Frontend
- 🟢 Node.js Backend
- 🐍 Python API
- 📱 Mobile App
- 🔷 TypeScript

Client/Type Field (Select):
- 💼 Client Work
- 🏠 Personal Project
- 📖 Learning/Research
- 🔧 Open Source
```

## 🚪 Context Switching Protocol

### Leaving a Project (3-5 minutes)
**Goal**: Preserve maximum context for future resumption

#### 1. Document Current State
```markdown
## Project Pause - [DATE] [TIME]
**Current Task**: [Specific issue/feature being worked on]
**Progress**: [What's completed, what's in progress]  
**Next Step**: [Exact next action to take]
**Blockers**: [What's preventing progress]

**Mental State**:
- Key insight/decision: [Important realization or choice made]
- Problem being solved: [Core challenge being addressed]
- Solution approach: [How you're approaching it]

**Code State**:
- Branch: [Current git branch]
- Modified files: [List of changed files]
- Commit needed: [Y/N and what to include]
- Tests passing: [Y/N/Partial]

**Environment**:
- Services running: [What dev servers/services are active]
- Data state: [Database/API state relevant to current work]
```

#### 2. Clean Up Workspace
```bash
# Save all work
git add .
git commit -m "WIP: [BRIEF_DESCRIPTION] - pausing work"

# Update issue with current status
# Add comment with current state and next steps

# Clean shutdown of development environment
npm run stop  # or equivalent for your stack
```

#### 3. Update Project Board
- Move current issue to appropriate status
- Add progress comment to issue
- Update any time estimates if learned more
- Check if anything is blocking others

### Entering a Project (5-10 minutes)
**Goal**: Rapidly rebuild context and mental model

#### 1. Review Project State
```bash
# Quick git status check
git status
git log --oneline -5  # See recent commits

# Check what's currently in development
git branch  # What branches exist?
```

#### 2. Reload Mental Context
**Review Sources** (in order):
1. **Last pause comment** - What was I doing?
2. **Project board** - What's the current state?
3. **Recent issue comments** - Any updates while away?
4. **Recent commits** - What changed recently?

#### 3. Environment Setup
```bash
# Start development environment
npm run dev  # or equivalent

# Verify environment health
npm run test  # Quick smoke test
curl localhost:3000/health  # API health check
```

#### 4. Quick Re-orientation (2 minutes)
- **File check**: Open the files you were working on
- **Browser check**: Load the relevant pages/features
- **Mental check**: "What was the problem I was solving?"

## 📋 Project-Specific Boards

### Repository Project Structure
**Each project repository has its own focused board**

#### Standard Columns Across Projects
```
📋 Backlog
├── Long-term ideas
├── Future features  
├── Technical debt
└── Nice-to-have improvements

🎯 Sprint Ready  
├── Well-defined tasks
├── Estimated effort
├── Dependencies resolved
└── Ready to start immediately

🚧 Active Development
├── Currently coding (max 2 items)
├── In active development
└── Daily progress expected

🧪 Testing/Review
├── Development complete
├── Needs testing/validation
├── Awaiting feedback
└── Ready for deployment

✅ Done
├── Completed this sprint
├── Deployed/released
└── Verified working
```

#### Project-Specific Customizations

**Frontend Project Additions**:
```
🎨 Design Review
├── Mockups to implement
├── UI/UX feedback needed
└── Design system updates

📱 Device Testing  
├── Mobile testing needed
├── Browser compatibility
└── Responsive design validation
```

**Backend API Project Additions**:
```
📝 API Documentation
├── Endpoint documentation needed
├── Schema updates required
└── Example requests/responses

🔍 Performance Review
├── Query optimization needed
├── Load testing required
└── Monitoring and alerts
```

**Full-Stack Project Additions**:
```
🔄 Integration Testing
├── Frontend + Backend integration
├── End-to-end user flows
└── Cross-component testing
```

## ⚡ Quick Switching Techniques

### The "5-Minute Switch"
**For brief context switches** (< 30 minutes away):
```
1. Quick commit with "WIP:" prefix (30 sec)
2. Add one-line comment to current issue (30 sec)  
3. Switch to other project (immediate)
4. Return by reading last comment (30 sec)
```

### The "Deep Switch"
**For extended work on different project** (> 2 hours):
```
1. Complete current logical unit of work (varies)
2. Full documentation protocol (5 min)
3. Clean environment shutdown (2 min)
4. Full context reload for new project (10 min)
```

### Emergency Switching
**For urgent interruptions**:
```
1. Immediate commit of current state (1 min)
2. Create urgent issue in target project (2 min)
3. Quick environment switch (2 min)
4. Document return path in calendar/notes (1 min)
```

## 🔧 Tools & Automation

### Browser Workspace Organization
```
Browser Profile: Development
├── Bookmarks Folder: "Active Projects"
    ├── 📱 Portfolio Dashboard
    ├── 🛒 E-commerce Board  
    ├── 📊 Analytics Board
    └── 🎯 Personal Dashboard

Browser Profile: Production
├── Bookmarks Folder: "Live Projects"  
    ├── 📱 Portfolio Live Site
    ├── 🛒 E-commerce Live Site
    └── 📊 Analytics Live Site
```

### Development Environment Management
```bash
# Create project-specific shell functions
alias proj-portfolio="cd ~/projects/portfolio && code . && npm run dev"
alias proj-ecommerce="cd ~/projects/ecommerce && code . && npm run dev"
alias proj-analytics="cd ~/projects/analytics && code . && npm run dev"

# Or use a project switcher script
switch-to() {
  PROJECT=$1
  cd ~/projects/$PROJECT
  code .
  npm run dev
  open "https://github.com/[username]/$PROJECT/projects"
}
```

### IDE/Editor Configuration
```json
// VS Code workspace switcher
{
  "folders": [
    {"name": "Portfolio", "path": "./portfolio"},
    {"name": "E-commerce", "path": "./ecommerce"}, 
    {"name": "Analytics", "path": "./analytics"}
  ],
  "settings": {
    "workbench.startupEditor": "readme"
  }
}
```

## 📊 Multi-Project Planning

### Weekly Planning Session (30 minutes)
**Goal**: Allocate time across projects and set priorities

#### 1. Capacity Planning (10 min)
```
Total Available Hours: [X hours]
├── Project A: [Y hours] ([Y/X]% of time)
├── Project B: [Z hours] ([Z/X]% of time)  
├── Learning/Research: [W hours]
└── Buffer/Interruptions: [Buffer hours]
```

#### 2. Priority Matrix (10 min)
```
High Impact + Urgent:
- [Items that must be done this week]

High Impact + Not Urgent:
- [Important long-term items]

Low Impact + Urgent:  
- [Quick wins and maintenance]

Low Impact + Not Urgent:
- [Backlog/someday items]
```

#### 3. Context Switch Optimization (10 min)
```
Batching Strategy:
- Monday/Tuesday: Frontend work (all projects)
- Wednesday/Thursday: Backend work (all projects)  
- Friday: Testing, deployment, planning

Or:

- Morning: Deep work on Project A
- Afternoon: Maintenance across all projects
- End of day: Planning and quick updates
```

### Monthly Project Health Review
**Goal**: Assess project progress and adjust strategy

#### Questions per Project:
1. **Velocity**: How much progress this month?
2. **Blockers**: What's consistently slowing down progress?
3. **Scope**: Is the project scope still realistic?
4. **Priority**: Does this project still deserve its time allocation?
5. **Learning**: What insights can be applied to other projects?

## 🎯 Focus Strategies

### Time Boxing by Project
```
Monday: Project A (full day focus)
Tuesday: Project B (full day focus)  
Wednesday: Project C (full day focus)
Thursday: Cross-project maintenance
Friday: Planning and smaller tasks
```

### Energy-Based Allocation
```
High Energy Times: Complex features, new development
Medium Energy Times: Bug fixes, refactoring, testing
Low Energy Times: Documentation, planning, code review
```

### Deadline-Driven Switching
```
Sprint Planning:
- Identify upcoming deadlines across all projects
- Allocate time working backwards from deadlines
- Buffer time for unexpected issues
- Communicate any conflicts early
```

## 🚫 Common Multi-Project Pitfalls

### The "Shiny Object" Problem
**Symptom**: Constantly switching to newest/most interesting project  
**Solution**: 
- Explicit time allocation per project
- Finish current sprint before major switches
- "New idea" capture process without immediate action

### The "Context Thrash" Problem  
**Symptom**: Spending more time switching than working  
**Solution**:
- Minimum time blocks (2+ hours per project)
- Batch similar work across projects
- Dedicated switching time slots

### The "Stalled Project" Problem
**Symptom**: One project gets ignored and becomes stale  
**Solution**:
- Weekly check-in on all active projects
- Explicit project pause/resume decisions
- Archive projects that aren't progressing

### The "Overcommitment" Problem
**Symptom**: Too many active projects, nothing gets finished  
**Solution**:
- Limit active projects (max 3 for solo developer)
- Use "Someday/Maybe" category for future projects
- Regular project portfolio review

## 📈 Success Metrics

### Project Health Indicators
- **Velocity**: Issues completed per week per project
- **Freshness**: Days since last commit/update per project
- **Momentum**: Consistent progress vs sporadic bursts
- **Balance**: Relatively even progress across active projects

### Personal Effectiveness Indicators  
- **Context Switch Time**: How long to resume work after switch
- **Decision Fatigue**: Ease of choosing what to work on
- **Progress Satisfaction**: Feeling of accomplishment across projects
- **Learning Transfer**: Insights from one project helping others

---

🎯 **Key Principle**: Better to make steady progress on fewer projects than sporadic progress on many. Choose your active project count deliberately and stick to it!