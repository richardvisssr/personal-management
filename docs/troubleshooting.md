# 🔧 Troubleshooting Guide

Oplossingen voor veelvoorkomende problemen bij het gebruik van GitHub voor projectmanagement.

## 🚨 Common Issues & Solutions

### 🏷️ Labels & Templates

#### Problem: Labels niet zichtbaar bij issue creation
**Symptoms**: Labels lijst is leeg of toont alleen default labels  
**Solution**:
```bash
# Method 1: GitHub CLI
gh label create --file .github/labels.yml

# Method 2: Manual via GitHub UI
1. Go to repository → Issues → Labels
2. Click "New label" for each label in labels.yml
3. Copy name, color, and description exactly
```

**Prevention**: Always verify labels are created after repository setup

#### Problem: Issue templates niet beschikbaar
**Symptoms**: "New Issue" toont alleen blank template  
**Solutions**:
1. **Check file location**: Templates must be in `.github/ISSUE_TEMPLATE/`
2. **Verify YAML frontmatter**: Ensure proper formatting:
   ```yaml
   ---
   name: Template Name
   about: Description
   title: "[PREFIX] "
   labels: ["label1", "label2"]
   ---
   ```
3. **Check file permissions**: Ensure files are committed and pushed
4. **Wait for GitHub**: Sometimes takes 5-10 minutes to appear

#### Problem: Config.yml niet werkend
**Symptoms**: Contact links niet zichtbaar  
**Solution**: Verify file is named exactly `config.yml` in `.github/ISSUE_TEMPLATE/` folder

### 📋 GitHub Projects

#### Problem: Project board niet automatisch updating
**Symptoms**: Issues niet verschijnen in project board  
**Solutions**:
1. **Manual linking**: 
   - Open issue → Right sidebar → Projects → Select project
2. **Automation setup**:
   - Project → Settings → Workflows → Auto-add items
3. **Filter check**: Verify project filters aren't excluding items

#### Problem: Custom fields niet zichtbaar
**Symptoms**: Aangemaakte fields verschijnen niet in board  
**Solutions**:
1. **Refresh browser**: Hard refresh (Ctrl+F5)
2. **Check permissions**: Ensure you have write access to project
3. **Re-add field**: Delete and recreate the custom field
4. **View settings**: Check if field is hidden in current view

#### Problem: Project cards niet bewegend tussen columns
**Symptoms**: Drag & drop werkt niet  
**Solutions**:
1. **Browser issues**: Try different browser or incognito mode
2. **JavaScript disabled**: Ensure JavaScript is enabled
3. **Mobile issue**: Use desktop for complex board management
4. **Manual update**: Use dropdown menu to change status

### 🔄 Workflow Issues

#### Problem: Te veel items "In Progress"
**Symptoms**: Overvol "In Progress" column, verlies van focus  
**Solutions**:
1. **Implement WIP limits**: Max 3 items in progress
2. **Use "Blocked" status**: Move stuck items temporarily
3. **Weekly cleanup**: Review and realistically assess progress
4. **Better estimation**: Break large items into smaller tasks

#### Problem: Stale issues accumulating
**Symptoms**: Oude issues blijven in backlog  
**Solutions**:
1. **Monthly cleanup routine**:
   ```
   Filter: updated:<30 days ago
   Action: Review, close, or update
   ```
2. **Automated cleanup**: Setup stale bot via GitHub Actions
3. **Ruthless prioritization**: Close issues that are no longer relevant
4. **Archive vs close**: Archive instead of delete for reference

#### Problem: Notification overload
**Symptoms**: Te veel GitHub notifications  
**Solutions**:
1. **Notification settings**:
   - GitHub → Settings → Notifications
   - Customize per repository
   - Turn off automatic watching
2. **Selective watching**: Only watch repositories you actively work on
3. **Email vs web**: Choose one primary notification method
4. **Filter setup**: Use email filters to organize GitHub notifications

### 💻 Development Workflow

#### Problem: Forgetting to update issues during development
**Symptoms**: Issues status niet in sync met werkelijke progress  
**Solutions**:
1. **Commit message linking**:
   ```bash
   git commit -m "Fix navigation bug, closes #123"
   ```
2. **Set reminders**: Phone alarm for end-of-day updates
3. **IDE integration**: Use VS Code GitHub extension
4. **Habit stacking**: Link issue updates to existing habits

#### Problem: Context switching chaos
**Symptoms**: Vergeten waar je was na project wissel  
**Solutions**:
1. **Status documentation template**:
   ```markdown
   ## Pause Point [DATE]
   - Currently working on: [specific task]
   - Next step: [what to do when returning]
   - Blockers: [what's preventing progress]
   - Files modified: [list of changed files]
   ```
2. **Git branch naming**: Use descriptive branch names
3. **WIP commits**: Commit work-in-progress with clear messages
4. **Comment documentation**: Add comments in code for mental bookmarks

### 🔗 Integration Problems

#### Problem: GitHub CLI not working
**Symptoms**: `gh` commands fail or not recognized  
**Solutions**:
1. **Installation check**:
   ```bash
   # Install GitHub CLI
   # macOS: brew install gh
   # Windows: winget install GitHub.cli
   # Linux: See github.com/cli/cli
   ```
2. **Authentication**:
   ```bash
   gh auth login
   ```
3. **Repository context**: Ensure you're in a git repository
4. **Permissions**: Check if you have write access to repository

#### Problem: Mobile workflow limitations
**Symptoms**: Kan niet alles doen via GitHub mobile app  
**Solutions**:
1. **Know the limitations**:
   - ✅ Can: View boards, update issues, add comments
   - ❌ Cannot: Create projects, configure fields, bulk actions
2. **Desktop for setup**: Use mobile only for updates
3. **Browser fallback**: Use mobile browser for advanced features
4. **Offline capture**: Use phone notes, transfer later

### 📊 Performance Issues

#### Problem: Large project boards loading slowly
**Symptoms**: Board takes long time to load  
**Solutions**:
1. **Archive old items**: Move completed items to separate archive project
2. **Limit visible items**: Use filters to show only relevant items
3. **Split projects**: Create separate projects for different phases
4. **Browser performance**: Clear cache, close other tabs

#### Problem: Too many repositories to manage
**Symptoms**: Personal dashboard becomes overwhelming  
**Solutions**:
1. **Project grouping**: Use project field to group related repositories
2. **Separate dashboards**: Create focused dashboards per project type
3. **Archive inactive**: Move old projects to archive status
4. **Prioritization**: Focus dashboard on active projects only

## 🛡️ Prevention Strategies

### Setup Phase Prevention
1. **Template testing**: Create test issues to verify templates work
2. **Label verification**: Check all labels are created correctly
3. **Project testing**: Test project board workflow with dummy items
4. **Documentation**: Document your specific setup for future reference

### Ongoing Prevention
1. **Weekly reviews**: Catch issues before they compound
2. **Process documentation**: Write down what works for you
3. **Backup strategy**: Export project data monthly
4. **Version control**: Keep project configurations in git

## 🆘 Emergency Procedures

### When Everything Breaks
1. **Don't panic**: Most GitHub issues are temporary
2. **Check GitHub Status**: Visit status.github.com
3. **Basic functionality**: Use basic GitHub features (issues without projects)
4. **Local backup**: Keep important tasks in local notes as backup

### Data Recovery
1. **Issue recovery**: Issues are rarely lost, check closed/archived
2. **Project recovery**: Projects can be recreated from issue history
3. **Label recovery**: Re-import from labels.yml file
4. **Export data**: Regularly export project data via API

## 📱 Mobile-Specific Troubleshooting

### GitHub Mobile App Issues
**Problem**: App not syncing or loading  
**Solutions**:
1. **Force close** and restart app
2. **Check internet** connection
3. **Update app** to latest version
4. **Clear app cache** (Android) or reinstall (iOS)

**Problem**: Limited functionality on mobile  
**Solutions**:
1. **Use mobile browser** for full GitHub features
2. **Desktop shortcuts**: Bookmark project URLs for quick access
3. **Offline workflow**: Capture ideas in notes, process later

## 🔍 Debugging Techniques

### GitHub API Issues
```bash
# Check rate limits
gh api rate_limit

# Test API access
gh api user

# Verify repository access
gh repo view [owner/repo]
```

### Project Configuration Debugging
1. **Check permissions**: Ensure write access to projects
2. **Browser dev tools**: Check for JavaScript errors
3. **Incognito test**: Rule out browser extension conflicts
4. **Different device**: Test on mobile/different computer

### Workflow Debugging
1. **Process audit**: Document your actual workflow vs intended
2. **Time tracking**: Measure time spent on process vs work
3. **Friction points**: Note where workflow feels slow or confusing
4. **User testing**: Have someone else try your setup

## 📞 Getting Help

### GitHub Support Channels
1. **GitHub Community**: community.github.com
2. **GitHub Support**: For account and billing issues
3. **GitHub Docs**: docs.github.com
4. **Stack Overflow**: For technical questions

### Self-Help Resources
1. **GitHub Changelog**: Keep up with new features
2. **GitHub Blog**: Learn about best practices
3. **Community Forums**: See how others solve similar problems
4. **YouTube Tutorials**: Visual learning for complex setups

---

🔧 **Remember**: Most issues have simple solutions. Document your fixes to help yourself (and others) in the future!