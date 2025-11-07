# Claude Code Web - Parallel Tasks Quick Reference

## 🚀 Quick Start (5 Minutes)

```
1. Go to: claude.ai/code
2. Connect GitHub account
3. Install Claude GitHub app
4. Start your first task
```

---

## 📝 Task Template Examples

### For Bug Fixes
```
Fix the [specific issue] in [filename] 
where [description of bug].
Expected behavior: [what should happen]
```

### For Features
```
Add [feature name] to [component/file] that:
- Does [action 1]
- Handles [action 2]
- Includes [action 3]
Add tests and documentation.
```

### For Refactoring
```
Refactor [filename] to:
- Improve [aspect 1]
- Simplify [aspect 2]
- Maintain all existing functionality
Ensure all tests still pass.
```

### For Documentation
```
Update documentation in [location] to:
- Explain [concept]
- Add examples for [feature]
- Fix any outdated information
```

---

## ✅ Parallel Tasks Checklist

Before starting parallel tasks, verify:

- [ ] Tasks work on different files/components
- [ ] Tasks are independent (no dependencies)
- [ ] Each task has clear, specific instructions
- [ ] You have enough rate limit quota
- [ ] You can monitor all sessions

---

## 🎯 Perfect Parallel Task Combinations

### Combination 1: Full Stack Feature
```
Tab 1: "Create backend API endpoint"
Tab 2: "Create frontend component" 
Tab 3: "Write tests for both"
Tab 4: "Update documentation"
```

### Combination 2: Multi-Component Updates
```
Tab 1: "Update Header component styling"
Tab 2: "Update Footer component styling"
Tab 3: "Update Sidebar component styling"
```

### Combination 3: Maintenance Sprint
```
Tab 1: "Update all dependencies in package.json"
Tab 2: "Fix linting errors in /src"
Tab 3: "Update README with new setup instructions"
Tab 4: "Add missing type definitions"
```

### Combination 4: Bug Bash
```
Tab 1: "Fix validation bug in login form"
Tab 2: "Fix date formatting bug in reports"
Tab 3: "Fix broken image links in docs"
Tab 4: "Fix memory leak in user session"
```

---

## ⚡ Power User Commands

### Multi-File Operations
```
"Update all files in /components to use TypeScript 
instead of JavaScript. Convert one file at a time 
and ensure types are correct."
```

### Bulk Updates
```
"Add error logging to all API endpoints in /api folder.
Use the logger utility from /utils/logger.js"
```

### Testing at Scale
```
"Add integration tests for all API endpoints in /api.
Each test should cover success and error cases."
```

### Documentation Sweep
```
"Review all .md files and:
- Fix broken links
- Update outdated examples
- Add missing sections
Create a summary of all changes."
```

---

## 🔄 Workflow Patterns

### Pattern 1: Sequential Parallel (Progressive)
```
Start with: 2-3 independent tasks
As they complete: Start 2-3 more
Continue: Until all work is done
```

### Pattern 2: Batch Processing
```
Morning: Start 5 small bug fixes
Review: Check progress at lunch
Afternoon: Review and merge completed tasks
```

### Pattern 3: Mixed Priority
```
High priority (Tab 1): Critical bug fix - monitor closely
Medium priority (Tabs 2-3): Features - check periodically
Low priority (Tabs 4-5): Documentation - review at end
```

---

## 📊 Session Tracking Template

Copy this to a text file for tracking:

```
=== Claude Code Parallel Sessions ===
Date: [Today's Date]

Session 1: [Task Description]
Branch: [branch-name]
Status: [🔄 Working | ✅ Done | ⚠️ Needs Review]
Priority: [High | Medium | Low]
Notes: [Any special notes]

Session 2: [Task Description]
Branch: [branch-name]
Status: [🔄 Working | ✅ Done | ⚠️ Needs Review]
Priority: [High | Medium | Low]
Notes: [Any special notes]

Session 3: [Task Description]
Branch: [branch-name]
Status: [🔄 Working | ✅ Done | ⚠️ Needs Review]
Priority: [High | Medium | Low]
Notes: [Any special notes]

=== Completed Today ===
- [Task] - Merged at [time]
- [Task] - Merged at [time]
```

---

## ⚠️ Common Mistakes to Avoid

### ❌ DON'T DO THIS:
```
Task 1: "Create database schema for users"
Task 2: "Create API that uses user schema"
❌ Task 2 depends on Task 1!
```

### ✅ DO THIS INSTEAD:
```
Task 1: "Create database schema for users"
Task 2: "Create database schema for posts"
✅ Both are independent!

(Then later, after merging both:)
Task 3: "Create API using user schema"
Task 4: "Create API using post schema"
```

---

## 🚨 Emergency Commands

### If Task Goes Wrong
```
"Stop current changes and revert to original state.
Explain what went wrong."
```

### If Task Needs Redirection
```
"I see you're modifying [file]. Instead, focus only 
on [specific file]. Ignore [other file] for now."
```

### If You Need to Split Task
```
"This task is too large. Just complete [specific part]
and I'll create a separate task for the rest."
```

---

## 💰 Rate Limit Management

### For Pro Users (~45 messages/5 hours per feature)
```
Conservative: 2-3 parallel tasks
Moderate: 4-5 parallel tasks  
Aggressive: 6+ parallel tasks (risk hitting limit)
```

### For Max Users (~100 messages/5 hours per feature)
```
Conservative: 5-7 parallel tasks
Moderate: 8-12 parallel tasks
Aggressive: 13+ parallel tasks
```

**Pro Tip:** Have a secondary account ready if you're doing heavy parallel work!

---

## 📈 Progress Monitoring Script

Use this mental model while monitoring:

```
Every 5 minutes:
├─ Quick scan all tabs
├─ Check for "✅ Complete" status
├─ Read any questions Claude has
└─ Provide feedback if needed

Every 15 minutes:
├─ Deep dive into one task
├─ Review code changes so far
├─ Steer if going off track
└─ Note progress in tracking doc

Every 30 minutes:
├─ Review all completed tasks
├─ Create PRs for finished work
├─ Start new tasks to replace completed ones
└─ Update priorities if needed
```

---

## 🎯 Task Sizing Guide

### Small Task (5-10 min)
```
- Fix a typo
- Update a config value
- Add a simple comment
- Fix a broken link
```

### Medium Task (15-30 min)
```
- Fix a bug in one file
- Add a new function
- Write tests for one module
- Update documentation page
```

### Large Task (30-60 min)
```
- Add a new feature component
- Refactor a module
- Write comprehensive tests
- Create detailed documentation
```

**Parallel Strategy:**
- 5-6 small tasks OR
- 3-4 medium tasks OR
- 2-3 large tasks

---

## 🔧 Environment Variables Cheat Sheet

Common env vars you might need to set:

```
API_KEY=your-api-key
DATABASE_URL=postgres://...
NODE_ENV=development
DEBUG=true
PORT=3000
```

Set these in the environment configuration before starting tasks that need them!

---

## 📱 Mobile Workflow

Using Claude Code from your phone:

```
1. Use iOS Claude app
2. Start tasks on commute
3. Monitor via mobile browser
4. Review PRs on desktop later
```

**Best for Mobile:**
- Starting simple tasks
- Monitoring progress
- Providing quick feedback
- Reading summaries

**Not Good for Mobile:**
- Detailed code review
- Complex troubleshooting
- Merging PRs
- Editing Claude's work

---

## 🏆 Success Metrics

Track your efficiency:

```
Week 1 Baseline:
- Tasks per day: _____
- Completion rate: _____%
- Time saved: _____ hours

Week 2 With Parallel:
- Tasks per day: _____
- Completion rate: _____%
- Time saved: _____ hours

Improvement: _____%
```

---

## 🎓 Leveling Up

### Beginner (Week 1-2)
- Run 2-3 parallel tasks
- Focus on bug fixes
- Review everything carefully

### Intermediate (Week 3-4)
- Run 4-6 parallel tasks
- Mix features and fixes
- Trust Claude more, review less

### Advanced (Week 5+)
- Run 6+ parallel tasks
- Complex features in parallel
- Efficient review process
- Custom workflows

---

## 📞 Get Help

**If stuck:**
1. Check Claude Code docs
2. Search GitHub issues
3. Ask in developer communities
4. Review this cheat sheet again

**Common search queries:**
- "claude code parallel tasks"
- "claude code rate limits"
- "claude code best practices"
- "claude code troubleshooting"

---

## 🎁 Bonus: Keyboard Shortcuts

```
Ctrl/Cmd + T: New tab (for new task)
Ctrl/Cmd + W: Close tab
Ctrl/Cmd + Tab: Switch between tabs
Ctrl/Cmd + Shift + T: Reopen closed tab
```

Use these to quickly manage multiple parallel sessions!

---

## ⏱️ Time-Saving Tips

1. **Batch similar tasks**: All bug fixes together, all docs together
2. **Use templates**: Save common task descriptions
3. **Monitor strategically**: Don't check every 30 seconds
4. **Trust the process**: Let Claude work without constant steering
5. **Review efficiently**: Scan for major issues first, details second

---

## 🔄 Daily Routine

```
Morning (9 AM):
- Review yesterday's PRs
- Start 3-4 high-priority tasks
- Let them run while you plan

Midday (12 PM):
- Check task progress
- Provide steering if needed
- Start 2-3 more medium tasks

Afternoon (3 PM):
- Review completed tasks
- Create and merge PRs
- Start low-priority cleanup tasks

End of Day (5 PM):
- Review all completions
- Plan tomorrow's tasks
- Let low-priority tasks finish overnight
```

---

**Print this cheat sheet and keep it handy!** 🖨️

*Last Updated: November 2025*
