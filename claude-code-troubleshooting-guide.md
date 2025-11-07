# Claude Code Web: Complete Troubleshooting Guide

**Real errors • Real solutions • Step-by-step fixes**

## 🚨 How to Use This Guide

1. Find the error message you're seeing
2. Follow the step-by-step solution
3. Check the "✅ Fixed" checkpoint
4. If still broken, try Alternative Solution

---

## Problem #1: Can't Connect GitHub

### Error Message:
```
"Unable to connect to GitHub"
or
"GitHub authorization failed"
```

### What You See:
- Button says "Connect GitHub" but clicking does nothing
- OR page redirects but shows error
- OR authorization page doesn't appear

### Solution - Step by Step:

**Step 1: Check if you're signed into GitHub**
```
1. Open new tab
2. Go to: github.com
3. Look at top-right corner
4. See your profile picture? → Yes: Go to Step 2
5. See "Sign in" button? → Click it and sign in first
```

**Step 2: Clear browser data**
```
Chrome/Edge:
1. Press Ctrl+Shift+Delete (Windows) or Cmd+Shift+Delete (Mac)
2. Select "Last hour"
3. Check: ☑️ Cookies and ☑️ Cached images
4. Click "Clear data"

Firefox:
1. Press Ctrl+Shift+Delete
2. Time range: "Last hour"  
3. Check: ☑️ Cookies and ☑️ Cache
4. Click "Clear Now"

Safari:
1. Safari menu → Preferences
2. Privacy tab
3. Click "Manage Website Data"
4. Click "Remove All"
```

**Step 3: Try connecting again**
```
1. Close ALL browser tabs
2. Open NEW tab
3. Go to: claude.ai/code
4. Sign in to Claude
5. Click "Connect GitHub"
6. Complete authorization
```

**✅ Fixed When:** You see "GitHub Connected" with green checkmark

### Alternative Solution:
```
Try different browser:
1. Do you use Chrome? Try Firefox
2. Do you use Firefox? Try Chrome
3. Try browser incognito/private mode:
   - Chrome: Ctrl+Shift+N
   - Firefox: Ctrl+Shift+P
   - Safari: Cmd+Shift+N
```

---

## Problem #2: Repository Not Showing Up

### Error Message:
```
"No repositories found"
or
Repository list is empty
```

### What You See:
- GitHub is connected
- But your repositories don't appear in the list
- OR specific repository is missing

### Solution - Step by Step:

**Step 1: Check repository permissions**
```
1. Go to: github.com/settings/installations
2. Find "Claude" in the list
3. Click "Configure"
4. Scroll to "Repository access"
5. Check what's selected:
   - "All repositories"? → Should see everything
   - "Only select repositories"? → Check if yours is listed
```

**Step 2: Grant access to repository**
```
If not in list:
1. Still on that page
2. Select "Only select repositories"
3. Click dropdown "Select repositories"
4. Find your repository
5. Click on it to add
6. Click "Save"
7. Wait 30 seconds
```

**Step 3: Refresh Claude Code**
```
1. Go back to: claude.ai/code
2. Refresh the page (F5 or Ctrl+R)
3. Wait for page to fully load
4. Click repository dropdown
5. Your repository should now appear
```

**✅ Fixed When:** Your repository appears in the dropdown list

### Alternative Solution:
```
Create new test repository:
1. Go to: github.com
2. Click "New" (green button)
3. Name: "claude-test"
4. Public
5. ☑️ Add README
6. Click "Create repository"
7. Go to: github.com/settings/installations
8. Click Configure on Claude
9. Add "claude-test"
10. Refresh claude.ai/code
11. Should see "claude-test" now
```

---

## Problem #3: Task Stuck on "Working..."

### Error Message:
```
Task shows "Working..." for more than 30 minutes
or
Progress bar doesn't move
```

### What You See:
- Task started but seems frozen
- No error message
- Just perpetual "Working on task..."

### Solution - Step by Step:

**Step 1: Check what Claude is doing**
```
1. Look at the task interface
2. See any recent activity? (file names, actions)
3. Is it showing same thing for 10+ minutes?
4. If yes → Task is likely stuck
```

**Step 2: Give more specific guidance**
```
1. Don't close the tab yet
2. Look for "Add guidance" or message input
3. Type this exact message:

"Focus only on [specific file name]. 
Make the minimal change needed.
Skip any additional improvements.
Don't run tests unless specifically required."

Example:
"Focus only on script.js.
Add the counter functionality only.
Skip testing and documentation."
```

**Step 3: If still stuck after 5 minutes**
```
1. Copy your original task description
2. Close the stuck tab
3. Open new tab: claude.ai/code
4. Write NEW, more specific task:

Instead of:
"Add dark mode to the app"

Write:
"Add dark mode by creating these CSS classes in style.css:
.dark { background: #1a1a1a; color: #fff; }
.dark .container { background: #2d2d2d; }
.dark input { background: #404040; color: #fff; }
Only modify style.css. Don't modify HTML or JavaScript yet."
```

**✅ Fixed When:** Task completes within 15 minutes

### Alternative Solution:
```
Break task into smaller pieces:

Original stuck task:
"Add user authentication with login, signup, password reset, and email verification"

Break into 4 separate parallel tasks:
Task 1: "Create login form HTML and basic styling"
Task 2: "Create signup form HTML and basic styling"
Task 3: "Add login API integration in auth.js"
Task 4: "Add signup API integration in auth.js"

Smaller tasks = faster completion
```

---

## Problem #4: Merge Conflicts

### Error Message:
```
"This branch has conflicts that must be resolved"
or
Pull request shows red "×" with "Conflicts"
```

### What You See:
- Cannot click "Merge pull request"
- GitHub shows conflicting files
- Red text saying "Resolve conflicts"

### Solution - Step by Step:

**Step 1: Understand what conflicted**
```
1. On the PR page, look for red "×"
2. Click "Resolve conflicts"
3. GitHub shows the conflicting file(s)
4. You'll see sections marked with:
   <<<<<<< HEAD
   [Version from main branch]
   =======
   [Version from your branch]
   >>>>>>> branch-name
```

**Step 2: Decide which version to keep**
```
Look at both versions:
- Which one is correct?
- Do you need BOTH changes?
- Is one clearly wrong?

Example conflict:
<<<<<<< HEAD
<h1>My Todo App</h1>
=======
<h1>Task Manager Pro</h1>
>>>>>>> claude-update-title

Decision: Want second version
```

**Step 3: Manually resolve**
```
1. In GitHub's conflict editor
2. Delete the lines you DON'T want
3. Delete the markers: <<<<<<<, =======, >>>>>>>
4. Keep only what you want:

Before (conflicted):
<<<<<<< HEAD
<h1>My Todo App</h1>
=======
<h1>Task Manager Pro</h1>
>>>>>>> claude-update-title

After (resolved):
<h1>Task Manager Pro</h1>

5. Click "Mark as resolved"
6. Click "Commit merge"
```

**✅ Fixed When:** PR shows green checkmark, "Ready to merge" button

### Alternative Solution (Let Claude Fix It):
```
1. Note the branch name with conflict: "claude-add-feature"
2. Note the conflicting file: "index.html"
3. Open NEW Claude Code tab
4. Give this prompt:

"Resolve merge conflicts in branch 'claude-add-feature'.
The conflict is in index.html.
Keep the changes from the feature branch (claude-add-feature).
Make sure the file is valid HTML after merging.
Test that it works."

5. Claude will fix conflicts and push update
6. Refresh PR page
7. Should now be mergeable
```

---

## Problem #5: Task Completed But Feature Doesn't Work

### Error Message:
```
Console shows errors like:
"Uncaught ReferenceError: functionName is not defined"
or
"TypeError: Cannot read property 'x' of undefined"
or
Feature just doesn't work - no visible error
```

### What You See:
- PR merged successfully
- But app is broken or feature doesn't work
- Browser console (F12) shows red errors

### Solution - Step by Step:

**Step 1: Open browser console**
```
1. Open your app in browser
2. Press F12 (or right-click → Inspect)
3. Click "Console" tab
4. Look for red error messages
5. Screenshot or copy the EXACT error text
```

**Step 2: Try to use the feature**
```
1. Do the action that should work
2. Watch console for new errors
3. Note what happens (or doesn't happen)
4. Write down the steps you took
```

**Step 3: Create bug fix task**
```
1. Open NEW Claude Code tab
2. Give detailed bug report:

"There's a bug in the merged code.

What I did:
1. [Your steps]
2. [What you clicked/typed]
3. [Expected result]

What happened:
[What actually occurred]

Console error:
[Paste exact error message]

Please fix this bug in [file name].
Make sure the feature works after fixing."

Example:
"There's a bug in the merged code.

What I did:
1. Added a new task
2. Clicked dark mode button
3. Expected dark mode to activate

What happened:
Nothing changed, page stayed light

Console error:
Uncaught ReferenceError: toggleDarkMode is not defined at HTMLButtonElement.onclick

Please fix this bug in script.js.
Add the missing toggleDarkMode function.
Test that dark mode actually toggles."
```

**✅ Fixed When:** Feature works without console errors

### Alternative Solution (Revert and Retry):
```
If feature is completely broken:

1. Go to GitHub repository
2. Click "Commits" (above file list)
3. Find the merge commit for broken feature
4. Click "Revert" button (right side)
5. Create revert PR
6. Merge the revert (removes broken code)
7. Start NEW Claude Code task with better instructions
8. Be more specific about testing requirements
```

---

## Problem #6: Can't Create Pull Request

### Error Message:
```
"There isn't anything to compare"
or
"No changes between branches"
or
Button says "Compare" but nothing happens
```

### What You See:
- Claude says task completed
- Branch was created
- But can't create PR

### Solution - Step by Step:

**Step 1: Check if branch exists**
```
1. Go to your GitHub repository
2. Click branch dropdown (shows "main" by default)
3. Type the branch name Claude gave you
4. Does it appear in the list?
   - Yes → Go to Step 2
   - No → Go to Alternative Solution
```

**Step 2: Manually create PR**
```
1. Click the branch dropdown
2. Select Claude's branch
3. You'll see: "This branch is X commits ahead of main"
4. Click "Contribute" button
5. Click "Open pull request"
6. Fill in title and description
7. Click "Create pull request"
```

**Step 3: If it says "No changes"**
```
This means the changes are already in main.
Check:
1. Was this already merged?
2. Look at recent commits in main
3. Do you see Claude's commit already there?
4. If yes → Task is done! No PR needed.
```

**✅ Fixed When:** PR created successfully OR changes already in main

### Alternative Solution (Branch Missing):
```
If branch doesn't exist:

1. Check Claude's task output
2. Did it actually complete? Or error?
3. Look for error messages in Claude's response
4. If error occurred:
   a. Copy the task description
   b. Start new task with same description
   c. Monitor closely this time
   d. Wait for "Task completed" confirmation
```

---

## Problem #7: Rate Limited

### Error Message:
```
"Rate limit exceeded. Please try again later."
or
"You've reached your usage limit"
```

### What You See:
- Can't start new tasks
- Error appears immediately when trying
- May show time until reset

### Solution - Step by Step:

**Step 1: Check your plan limits**
```
Pro Plan:
- ~45 messages per 5 hours per feature
- Running 3 parallel tasks = 3x usage
- Expected: Can run 2-3 sets of parallel tasks

Max Plan:
- ~100 messages per 5 hours per feature
- Running 3 parallel tasks = 3x usage  
- Expected: Can run 5-6 sets of parallel tasks
```

**Step 2: Calculate wait time**
```
If you hit rate limit:
1. Note the current time
2. Rate limit resets after 5 hours
3. Calculate: Current time + 5 hours
4. Set a reminder

Example:
Hit limit at: 2:00 PM
Can resume at: 7:00 PM (2 + 5 hours)
```

**Step 3: Optimize task usage**
```
While waiting, plan better:
1. Are your tasks too broad?
   - Broad: "Build entire feature"
   - Specific: "Add button that does X"
2. Can you merge tasks?
   - Instead of 3 tasks for 3 CSS files
   - Do 1 task for all CSS changes
3. Prioritize most important tasks
```

**✅ Fixed When:** Can start new tasks after wait period

### Alternative Solutions:

**Option 1: Upgrade plan**
```
1. Go to: claude.ai/settings
2. Click "Subscription"
3. Upgrade Pro → Max
4. Max has 2x the rate limit
5. Costs $100/month vs $20/month
```

**Option 2: Use second account**
```
1. Create new email address
2. Sign up for second Claude account
3. Subscribe to Pro plan again
4. Switch accounts when one hits limit
5. Continue working

Note: Need separate GitHub account OR
      Share repository access to both
```

**Option 3: Work locally instead**
```
1. Install Claude Code CLI
2. Use terminal instead of web
3. Different rate limits
4. Can continue working
5. See: docs.claude.com/claude-code
```

---

## Problem #8: Wrong Files Modified

### Error Message:
```
No specific error, but:
"Claude modified files I didn't want changed"
or
"PR shows changes to unexpected files"
```

### What You See:
- PR has changes to files you didn't ask for
- More files changed than expected
- Some original files are broken

### Solution - Step by Step:

**Step 1: Don't merge the PR yet**
```
1. Review PR carefully
2. Look at each changed file
3. Ask yourself: "Should this file change?"
4. If NO → Don't merge
```

**Step 2: Close the PR**
```
1. Scroll to bottom of PR
2. Click "Close pull request"
3. DON'T click "Merge" by accident
4. Add comment: "Too many files modified, will redo"
5. PR is closed but branch remains
```

**Step 3: Start more specific task**
```
1. Open NEW Claude Code tab
2. Write VERY specific prompt:

Bad (caused problem):
"Add dark mode to the app"

Good (prevents problem):
"Add dark mode CSS classes to ONLY style.css.

Add these classes:
- .dark (for body)
- .dark .container
- .dark input
- .dark button

Do NOT modify:
- index.html
- script.js  
- Any other files

Only modify style.css"
```

**✅ Fixed When:** New PR only shows intended file

### Alternative Solution (Save What You Want):
```
If PR has some good changes:

1. Look at the PR
2. Find files with good changes
3. Copy those changes manually:
   a. Click on the good file
   b. Click "View file"
   c. Copy the code you want
   d. Paste into your local copy
   e. Commit manually
4. Close the PR
5. Delete the branch
```

---

## Problem #9: Task Takes Different Approach Than Expected

### Error Message:
```
No error, but:
"Claude solved it differently than I wanted"
or
"The code works but uses wrong approach"
```

### What You See:
- Task completes successfully
- Code works correctly
- But implementation is not what you wanted
- Different library, pattern, or structure

### Solution - Step by Step:

**Step 1: Decide if it matters**
```
Ask yourself:
1. Does the code work correctly? → Yes
2. Is it readable and maintainable? → Yes
3. Does it meet requirements? → Yes

If all yes → Consider accepting it
Sometimes different approach is fine
```

**Step 2: If you really need your approach**
```
1. Close the PR (don't merge)
2. Start NEW task with SPECIFIC implementation:

Instead of:
"Add form validation"

Write:
"Add form validation to ContactForm.jsx

IMPORTANT - Use this specific approach:
1. Use Yup library for validation schema
2. Install with: npm install yup
3. Define schema at top of file
4. Validate on blur and submit
5. Show errors below each field

Do NOT use:
- Manual validation functions
- Other validation libraries
- Inline validation

Example structure:
import * as Yup from 'yup';

const schema = Yup.object().shape({
  email: Yup.string().email().required(),
  // ...
});

Use this exact pattern."
```

**✅ Fixed When:** Implementation matches your requirements

### Alternative Solution (Provide Example Code):
```
Show Claude exactly what you want:

"Refactor the validation in ContactForm.jsx to match this pattern:

```javascript
// Example of pattern I want
const validateEmail = (email) => {
  const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return regex.test(email);
};

const handleSubmit = (e) => {
  e.preventDefault();
  const errors = {};
  
  if (!validateEmail(email)) {
    errors.email = 'Invalid email';
  }
  
  if (Object.keys(errors).length > 0) {
    setErrors(errors);
    return;
  }
  
  // Submit form
};
```

Use this exact pattern for all form fields.
Replace existing validation code with this approach."
```

---

## Problem #10: Multiple Tasks Changed Same File

### Error Message:
```
"Merge conflicts" on 2-3 PRs
or
All PRs conflict with each other
```

### What You See:
- Started 3 parallel tasks
- All three modified same file
- Now all three have merge conflicts
- Complicated to resolve

### Solution - Step by Step:

**Step 1: Merge in order**
```
1. Pick the SMALLEST change first
2. Look at each PR
3. Count lines changed
4. Merge the one with fewest changes

Example:
- PR 1: 50 lines changed
- PR 2: 10 lines changed ← Merge this first
- PR 3: 100 lines changed
```

**Step 2: Let GitHub auto-update**
```
After merging first PR:
1. Wait 30 seconds
2. Refresh other PR pages
3. GitHub may auto-resolve conflicts
4. If green checkmark appears → Merge next
5. If still conflicted → Go to Step 3
```

**Step 3: Resolve remaining conflicts**
```
For each remaining PR:
1. Click "Resolve conflicts"
2. Look at conflicting sections
3. Keep BOTH changes if possible:
   - Both added new functions? Keep both
   - Both modified same line? Combine them
4. Delete conflict markers
5. Mark as resolved
6. Merge
```

**✅ Fixed When:** All PRs merged, feature works

### Prevention for Next Time:
```
To avoid this issue:

Before starting parallel tasks, ask:
1. Will these tasks touch the same file?
2. Will they modify the same section?

If YES to either:
- Don't run in parallel
- OR split file into smaller modules
- OR run tasks sequentially

Good parallel: File A, File B, File C
Bad parallel: 3 tasks all editing File A
```

---

## Problem #11: Cannot Move Session to Local CLI

### Error Message:
```
"Cannot move this session to CLI"
or
"Session must be started locally to move"
or
Command doesn't work in terminal
```

### What You See:
- Claude shows "Open in CLI" button
- Copy the command
- Paste in terminal
- Error or nothing happens

### Solution - Step by Step:

**Step 1: Verify Claude Code CLI is installed**
```
Open terminal and type:
claude --version

See version number?
→ Yes: Go to Step 2
→ No: Install Claude Code CLI first

To install:
npm install -g @anthropic-ai/claude-code

Then try 'claude --version' again
```

**Step 2: Check authentication**
```
In terminal, type:
claude auth status

See "Authenticated"?
→ Yes: Go to Step 3
→ No: Authenticate first

To authenticate:
claude auth login

Follow the prompts
```

**Step 3: Verify repository location**
```
The command only works if:
1. You're in the repository directory
2. Repository is cloned locally
3. Git remote matches Claude's session

Check:
cd path/to/your/repository
git remote -v

Should show your GitHub repo URL
```

**Step 4: Try the command again**
```
1. Copy command from Claude Code web
2. Make sure you're in repo directory
3. Paste command
4. Press Enter
5. Should show: "Loading session..."
```

**✅ Fixed When:** Session loads in local terminal

### Alternative Solution:
```
If you can't move session:

Option 1: Just finish on web
- Let task complete online
- Review and merge PR
- No need to move local

Option 2: Start fresh locally
- Don't move existing session
- Open terminal in your repo
- Run: claude
- Start same task from scratch locally
- Web session continues separately
```

---

## Quick Diagnostic Checklist

**Before asking for help, check:**

```
Basic Checks:
□ Is my internet connection working?
□ Am I signed into Claude?
□ Am I signed into GitHub?
□ Is the repository still there?
□ Did I wait long enough (tasks take 10-30 min)?

Browser Checks:
□ Did I try refreshing the page?
□ Did I clear browser cache?
□ Did I try incognito/private mode?
□ Did I try different browser?

Task Checks:
□ Was my prompt specific enough?
□ Did I specify which files to modify?
□ Are the tasks actually independent?
□ Did I check for error messages?

After Task:
□ Did task actually complete?
□ Did I review the PR before merging?
□ Did I test after merging?
□ Are there console errors?
```

---

## Still Stuck? Try This Process

**Systematic Debugging:**

```
1. Identify the exact problem
   - What were you trying to do?
   - What happened instead?
   - What error message do you see?

2. Find similar problem in this guide
   - Use Ctrl+F to search error text
   - Look for similar symptoms
   - Read the solution carefully

3. Follow solution step-by-step
   - Don't skip steps
   - Check each checkpoint
   - Take your time

4. If still broken after solution:
   - Try Alternative Solution
   - Restart from scratch
   - Try simpler version of task

5. Document what worked
   - Keep notes for next time
   - Learn from the issue
   - Improve your prompts
```

---

## Emergency Reset Procedure

**When everything is broken:**

```
FULL RESET (Last Resort):

1. Sign out of Claude completely
2. Sign out of GitHub completely
3. Close ALL browser tabs
4. Clear ALL browser data (not just cache)
5. Restart your browser
6. Sign into GitHub fresh
7. Sign into Claude fresh
8. Connect GitHub again
9. Start with simple task first
10. Make sure simple task works

Then gradually return to normal usage.
```

---

## Contact Support

**When to contact support:**
- None of these solutions work
- Consistent errors not listed here
- Payment/billing issues
- Account access problems

**Where to get help:**
- Claude Support: support.claude.com
- GitHub Support: support.github.com
- Community Forums: Check product websites

**What to include in support request:**
1. Exact error message
2. What you were doing
3. What you already tried
4. Screenshots if relevant
5. Browser and OS version

---

**Most problems have simple solutions. Work through this guide systematically!** 🔧

*Troubleshooting Guide Version: 1.0*  
*Last Updated: November 2025*  
*Clear Errors • Clear Solutions*
