# 📝 Task Creation Workflow Guide

Van idee naar gestructureerde GitHub issue - een praktische guide voor het effectief vastleggen en organiseren van werk.

## 🧠 Idea Capture Strategies

### 💡 Immediate Capture (< 2 minuten)
**When**: Tijdens andere werkzaamheden, in meetings, onderweg  
**Goal**: Vastleggen zonder context verlies

#### Quick Capture Methods:
1. **GitHub Mobile**: Direct Simple Todo maken
2. **Phone Notes**: Voice memo of text note  
3. **Email to Self**: Met "GitHub:" prefix
4. **Quick File**: `ideas.md` in je repository

#### Quick Capture Template:
```
💡 [BRIEF_DESCRIPTION]
Context: [WHERE/WHEN DID THIS COME UP]
Priority: [HIGH/MEDIUM/LOW GUESS]
```

### 🔍 Later Processing (5-15 minuten)
**When**: Dedicated planning time, end of day  
**Goal**: Transform captures into actionable issues

## 🎯 Issue Type Decision Tree

### Decision Matrix:
```
Time to Complete? 
├── < 30 minutes → Simple Todo
├── 30 min - 4 hours → Simple Todo (but detailed)
├── 4 hours - 2 days → Feature Request
└── > 2 days → Epic (break into smaller features)

Complexity?
├── Clear how to do it → Simple Todo
├── Need some research → Feature Request  
├── Significant uncertainty → Research spike first
└── Major architectural change → Epic

Scope?
├── Single file/component → Simple Todo
├── Multiple files/components → Feature Request
├── Multiple features → Epic
└── Cross-project impact → Epic
```

## 📝 Template Usage Guide

### Simple Todo - When & How
**Perfect for**:
- Bug fixes (clear steps to reproduce)
- Small improvements (UI tweaks, text changes)
- Documentation updates
- Code cleanup/refactoring
- Configuration changes

**Template Filling Strategy**:
```markdown
## Todo Item
[ONE SENTENCE DESCRIPTION]

### Beschrijving  
[2-3 SENTENCES WITH CONTEXT]
- What needs to be done?
- Why is this needed?
- Where in the codebase?

### Acceptatiecriteria
- [ ] [SPECIFIC OUTCOME 1]
- [ ] [SPECIFIC OUTCOME 2] 
- [ ] [VERIFICATION METHOD]

### Extra Context
- Files to modify: [LIST]
- Related issues: #[NUMBER]
- Useful links: [DOCUMENTATION/REFERENCES]
```

### Feature Request - When & How
**Perfect for**:
- New functionality
- User-facing features
- API endpoints
- Complex integrations
- Multi-step workflows

**Template Filling Strategy**:
```markdown
## Feature Beschrijving
[PARAGRAPH EXPLAINING THE FEATURE]

### User Story
Als [USER_TYPE]
Wil ik [ACTION/FUNCTIONALITY]
Zodat [GOAL/BENEFIT]

### Acceptatiecriteria
- [ ] [USER CAN DO X]
- [ ] [SYSTEM RESPONDS WITH Y]
- [ ] [EDGE CASE Z IS HANDLED]

### Technical Requirements
#### Frontend Requirements
- [ ] [UI COMPONENT NEEDED]
- [ ] [STATE MANAGEMENT]
- [ ] [API INTEGRATION]

#### Backend Requirements  
- [ ] [API ENDPOINT]
- [ ] [DATABASE CHANGES]
- [ ] [BUSINESS LOGIC]

### Definition of Done
- [ ] Feature is implemented and tested
- [ ] Documentation is updated
- [ ] Code review completed
- [ ] Deployed to staging environment
```

### Bug Report - When & How
**Perfect for**:
- Unexpected behavior
- Errors and crashes
- Performance issues
- Security vulnerabilities

**Template Filling Strategy**:
```markdown
## Bug Beschrijving
[CLEAR STATEMENT OF WHAT'S WRONG]

### Stappen om te Reproduceren
1. [EXACT STEP 1]
2. [EXACT STEP 2] 
3. [EXACT STEP 3]

### Verwacht Gedrag
[WHAT SHOULD HAPPEN]

### Actueel Gedrag  
[WHAT ACTUALLY HAPPENS]

### Omgeving
- Browser: [CHROME 91, FIREFOX 89, ETC.]
- OS: [WINDOWS 10, MACOS BIG SUR, ETC.]
- Screen: [MOBILE/TABLET/DESKTOP]

### Logs & Error Messages
```
[PASTE EXACT ERROR MESSAGES]
```

### Prioriteit Reden
- [ ] Blocks critical functionality
- [ ] Impacts user experience significantly
- [ ] Cosmetic issue only
- [ ] Performance degradation
```

## 🏗️ Progressive Issue Development

### Level 1: Basic Issue Creation
```
Title: [TODO] Fix navigation menu styling
Description: Menu items not aligned properly on mobile
Labels: bug, frontend, simple
```

### Level 2: Add Context
```
Description: Menu items not aligned properly on mobile devices.
Items are stacked vertically but have inconsistent spacing.
Affects user experience on phones and tablets.

Files to check: 
- src/components/Navigation.vue
- src/styles/navigation.scss
```

### Level 3: Full Specification
```
[Complete template with]:
- Detailed acceptance criteria
- Technical specifications  
- Design requirements
- Testing considerations
- Definition of done
```

## 🔄 Issue Lifecycle Management

### From Idea to Implementation

#### Phase 1: Capture (30 seconds)
```
💡 Idea → Quick note/Simple Todo
Goal: Don't lose the thought
Quality: Rough, basic
```

#### Phase 2: Clarification (5 minutes)  
```
Rough idea → Detailed issue
Goal: Make it actionable
Quality: Clear, specific
```

#### Phase 3: Refinement (During work)
```
Basic issue → Rich documentation
Goal: Help future self
Quality: Comprehensive, useful
```

#### Phase 4: Completion (After work)
```
Active issue → Documented resolution
Goal: Knowledge capture
Quality: Complete, referenceable
```

### Issue Enhancement During Development
**As you learn more**:
- Add implementation notes to comments
- Update acceptance criteria if needed
- Link to related issues discovered
- Document decisions made

## 🏷️ Labeling Strategy for Task Creation

### Label Application Rules
```
Priority (Always add one):
🔴 urgent - Same day completion needed
🟠 high - This week completion  
🟡 medium - This month completion
🟢 low - Someday/maybe

Type (Always add one):
🚀 feature - New functionality
🐛 bug - Something's broken
📚 docs - Documentation work
🔧 chore - Maintenance tasks

Complexity (Add when known):
🟢 simple - < 2 hours
🟡 medium - 2-8 hours  
🟠 complex - > 8 hours

Technology (Add if relevant):
frontend, backend, database, api
react, nodejs, python, etc.
```

### Smart Label Combinations
```
Common Patterns:
- bug + urgent + simple = Quick hotfix
- feature + medium + frontend = UI improvement
- docs + low + simple = Documentation debt
- chore + high + backend = Technical debt
```

## 📊 Issue Organization Patterns

### Batch Creation Sessions
**Weekly Planning (30 min)**:
- Review idea capture notes
- Create 5-10 well-formed issues
- Assign priorities and milestones
- Link related issues

**Project Kickoff (1 hour)**:
- Create epic issue for major feature
- Break down into constituent features
- Create initial Simple Todos for research
- Set up milestone for completion

### Issue Relationships
```
Epic → Feature → Tasks Pattern:
├── Epic: "User Authentication System"
    ├── Feature: "User Registration"
        ├── Task: "Create registration form UI"
        ├── Task: "Implement email validation"
        └── Task: "Add password strength checking"
    ├── Feature: "User Login"  
        ├── Task: "Create login form"
        └── Task: "Implement JWT authentication"
    └── Feature: "Password Reset"
        ├── Task: "Email reset flow"
        └── Task: "Reset form UI"
```

### Cross-Reference Strategies
```
Dependency Linking:
- "Depends on: #123"
- "Blocks: #456"  
- "Related to: #789"

Feature Grouping:
- "Part of epic: #100"
- "Milestone: v1.2"
- "Sprint: 2024-01"
```

## 🎯 Quality Criteria for Issues

### Well-Formed Issue Checklist
- [ ] **Clear title** with appropriate prefix
- [ ] **Actionable description** (what to do, not just what's wrong)
- [ ] **Acceptance criteria** (how to know it's done)
- [ ] **Appropriate labels** (priority, type, complexity)
- [ ] **Linked to project** (for visibility)
- [ ] **Time estimate** (implicit or explicit)

### Red Flags to Avoid
❌ Vague titles: "Fix the thing"  
❌ Missing context: "This doesn't work"  
❌ No acceptance criteria: How do you know when done?  
❌ Wrong template: Bug report for feature request  
❌ Missing labels: Can't filter or prioritize  

## 🔧 Advanced Issue Creation

### Issue Templates Customization
Create project-specific variants:
```
Templates/
├── web-feature.md (Frontend-focused)
├── api-feature.md (Backend-focused)  
├── bug-frontend.md (UI bug template)
├── bug-backend.md (API bug template)
└── research-spike.md (Investigation template)
```

### Automation Helpers
```bash
# GitHub CLI shortcuts
alias todo="gh issue create --title '[TODO]' --label 'todo,simple'"
alias bug="gh issue create --template bug-report.md"
alias feature="gh issue create --template feature-request.md"

# Quick issue creation with preset labels
gh issue create --title "[TODO] $1" --label "todo,simple" --body "Quick task: $1"
```

## 📈 Continuous Improvement

### Weekly Issue Quality Review
**Questions to ask**:
- Which issues took longer than estimated? Why?
- Which issues needed significant clarification during work?
- What patterns am I seeing in my work?
- How can I improve my issue creation process?

### Template Evolution
- **Month 1**: Use standard templates as-is
- **Month 2**: Customize based on your project needs
- **Month 3**: Create specialized templates for common patterns
- **Ongoing**: Refine based on usage patterns

---

🎯 **Remember**: Perfect issues aren't created, they evolve. Start with good enough and improve as you learn more about the work!