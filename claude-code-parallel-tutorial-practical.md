# Claude Code Web: Practical Parallel Tasks Tutorial

**Zero Assumptions • Real Code • Step-by-Step**

## 🎯 What You'll Build

By the end of this tutorial, you will have:
- ✅ A real GitHub repository with working code
- ✅ Completed 3 parallel coding tasks simultaneously
- ✅ Created and merged 3 pull requests
- ✅ A working Todo List web application

**Time Required:** 2 hours  
**Cost:** Free (requires Claude Pro or Max account)

---

## Part 1: Setup Your GitHub Repository (15 minutes)

### Step 1.1: Create a New Repository

1. **Go to GitHub:**
   - Open your browser
   - Navigate to [https://github.com](https://github.com)
   - Log in to your account

2. **Create New Repository:**
   - Click the **green "New"** button (top left)
   - OR click your profile picture → "Your repositories" → "New"

3. **Repository Settings:**
   ```
   Repository name: todo-app-practice
   Description: Practice project for Claude Code parallel tasks
   Visibility: ☑️ Public (or Private - your choice)
   ☑️ Add a README file
   ☑️ Add .gitignore → Choose: Node
   License: MIT License (optional)
   ```

4. **Click "Create repository"**

**✅ CHECKPOINT:** You should see your new repository with a README.md file

---

### Step 1.2: Add Initial Code Files

We'll create a simple todo app with HTML, CSS, and JavaScript.

1. **Click "Add file" → "Create new file"**

2. **Create `index.html`:**
   
   Filename: `index.html`
   
   Copy and paste this code:
   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Simple Todo App</title>
       <link rel="stylesheet" href="style.css">
   </head>
   <body>
       <div class="container">
           <h1>My Todo List</h1>
           <div class="input-section">
               <input type="text" id="todoInput" placeholder="Add a new task...">
               <button onclick="addTodo()">Add Task</button>
           </div>
           <ul id="todoList"></ul>
       </div>
       <script src="script.js"></script>
   </body>
   </html>
   ```
   
   Click **"Commit new file"**

3. **Create `style.css`:**
   
   Click "Add file" → "Create new file"
   
   Filename: `style.css`
   
   ```css
   body {
       font-family: Arial, sans-serif;
       background-color: #f5f5f5;
       margin: 0;
       padding: 20px;
   }

   .container {
       max-width: 600px;
       margin: 0 auto;
       background: white;
       padding: 30px;
       border-radius: 10px;
       box-shadow: 0 2px 10px rgba(0,0,0,0.1);
   }

   h1 {
       color: #333;
       text-align: center;
   }

   .input-section {
       display: flex;
       gap: 10px;
       margin-bottom: 20px;
   }

   #todoInput {
       flex: 1;
       padding: 10px;
       border: 2px solid #ddd;
       border-radius: 5px;
       font-size: 16px;
   }

   button {
       padding: 10px 20px;
       background-color: #4CAF50;
       color: white;
       border: none;
       border-radius: 5px;
       cursor: pointer;
       font-size: 16px;
   }

   button:hover {
       background-color: #45a049;
   }

   #todoList {
       list-style: none;
       padding: 0;
   }

   .todo-item {
       display: flex;
       align-items: center;
       padding: 15px;
       background: #f9f9f9;
       margin-bottom: 10px;
       border-radius: 5px;
   }

   .todo-item.completed {
       text-decoration: line-through;
       opacity: 0.6;
   }

   .delete-btn {
       margin-left: auto;
       background-color: #f44336;
       padding: 5px 10px;
       font-size: 14px;
   }

   .delete-btn:hover {
       background-color: #da190b;
   }
   ```
   
   Click **"Commit new file"**

4. **Create `script.js`:**
   
   Click "Add file" → "Create new file"
   
   Filename: `script.js`
   
   ```javascript
   // Todo app functionality
   let todos = [];

   function addTodo() {
       const input = document.getElementById('todoInput');
       const todoText = input.value.trim();
       
       if (todoText === '') {
           alert('Please enter a task!');
           return;
       }
       
       const todo = {
           id: Date.now(),
           text: todoText,
           completed: false
       };
       
       todos.push(todo);
       input.value = '';
       renderTodos();
   }

   function toggleTodo(id) {
       const todo = todos.find(t => t.id === id);
       if (todo) {
           todo.completed = !todo.completed;
           renderTodos();
       }
   }

   function deleteTodo(id) {
       todos = todos.filter(t => t.id !== id);
       renderTodos();
   }

   function renderTodos() {
       const todoList = document.getElementById('todoList');
       todoList.innerHTML = '';
       
       todos.forEach(todo => {
           const li = document.createElement('li');
           li.className = 'todo-item' + (todo.completed ? ' completed' : '');
           li.innerHTML = `
               <input type="checkbox" 
                      ${todo.completed ? 'checked' : ''} 
                      onchange="toggleTodo(${todo.id})">
               <span style="margin-left: 10px;">${todo.text}</span>
               <button class="delete-btn" onclick="deleteTodo(${todo.id})">Delete</button>
           `;
           todoList.appendChild(li);
       });
   }

   // Allow Enter key to add todo
   document.addEventListener('DOMContentLoaded', function() {
       const input = document.getElementById('todoInput');
       input.addEventListener('keypress', function(e) {
           if (e.key === 'Enter') {
               addTodo();
           }
       });
   });
   ```
   
   Click **"Commit new file"**

**✅ CHECKPOINT:** Your repository should now have 5 files:
- README.md
- .gitignore
- index.html
- style.css
- script.js

---

### Step 1.3: Test Your App

1. **View the files:**
   - Click on `index.html` in your repository
   - Click the **"Raw"** button
   - Copy the URL

2. **Use GitHub Pages (optional):**
   - Go to repository Settings → Pages
   - Under "Source", select "main" branch
   - Click Save
   - Wait 1-2 minutes
   - Your app will be live at: `https://YOUR-USERNAME.github.io/todo-app-practice`

**✅ CHECKPOINT:** You can see your HTML, CSS, and JS files in the repository

---

## Part 2: Connect Claude Code Web (10 minutes)

### Step 2.1: Access Claude Code

1. **Open a new browser tab**
2. **Go to:** [https://claude.ai/code](https://claude.ai/code)
3. **Sign in** with your Claude Pro or Max account

**✅ CHECKPOINT:** You should see the Claude Code interface with "Connect GitHub" button

---

### Step 2.2: Connect Your GitHub

1. **Click "Connect GitHub"**
2. **Authorize Claude** when prompted
3. **Install Claude GitHub App:**
   - You'll see a list of your repositories
   - Find "todo-app-practice"
   - Click **"Install"** or check the box next to it
   - Click **"Install & Authorize"**

**✅ CHECKPOINT:** You should see "GitHub Connected" and your repository listed

---

### Step 2.3: Configure Environment

1. **Select your repository:** `todo-app-practice`
2. **Choose network access:** 
   - Select **"Limited"** (this is fine for our tutorial)
3. **Environment variables:** 
   - Leave blank (we don't need any)

**✅ CHECKPOINT:** The interface should show "Ready to start a task"

---

## Part 3: Your First Single Task (15 minutes)

Before running parallel tasks, let's complete ONE task to understand the workflow.

### Step 3.1: Start a Simple Task

**In the Claude Code interface, type this exact prompt:**

```
Add a header comment to script.js that includes:
- File name
- Description: "Todo list application with add, toggle, and delete functionality"
- Author: [Your Name]
- Date: November 2025

Make sure it's properly formatted as a JavaScript comment block.
```

**Click "Start Task" or press Enter**

---

### Step 3.2: Watch Claude Work

You'll see Claude:
1. **Clone your repository** (shows progress)
2. **Analyze the code** (reads script.js)
3. **Make the change** (adds the comment)
4. **Commit the change** (creates a commit)
5. **Push to a new branch** (something like `claude-add-header-comment`)

**This takes about 2-5 minutes**

**✅ CHECKPOINT:** Claude should show "Task completed" with a branch name

---

### Step 3.3: Review the Change

1. **Copy the branch name** (shown by Claude)
2. **Go to your GitHub repository** (in another tab)
3. **Click "branches"** (above the file list)
4. **Find Claude's branch** (the one you just copied)
5. **Click "Compare & pull request"**

You should see the change Claude made:
```javascript
/**
 * File: script.js
 * Description: Todo list application with add, toggle, and delete functionality
 * Author: [Your Name]
 * Date: November 2025
 */

// Todo app functionality
let todos = [];
// ... rest of the code
```

**✅ CHECKPOINT:** You can see the new comment in the pull request

---

### Step 3.4: Merge Your First PR

1. **Review the changes** (should look correct)
2. **Click "Create pull request"**
3. **Add a title:** "Add header comment to script.js"
4. **Click "Create pull request"** again
5. **Click "Merge pull request"**
6. **Click "Confirm merge"**
7. **Click "Delete branch"** (cleanup)

**✅ CHECKPOINT:** Your main branch now has the header comment. You've completed your first Claude Code task!

---

## Part 4: Running 3 Tasks in Parallel (30 minutes)

Now for the exciting part - running multiple tasks at the same time!

### Step 4.1: Identify Your 3 Tasks

We're going to improve our todo app with 3 separate features:

**Task 1:** Add a task counter  
**Task 2:** Add a "Clear Completed" button  
**Task 3:** Add dark mode toggle  

These are perfect for parallel work because they touch different parts of the code.

---

### Step 4.2: Start Task 1 (Task Counter)

1. **Keep your current Claude Code tab open**
2. **Open TWO MORE tabs** and go to [https://claude.ai/code](https://claude.ai/code) in each

Now you have 3 tabs with Claude Code. Let's label them mentally:
- **Tab 1:** Task Counter
- **Tab 2:** Clear Completed
- **Tab 3:** Dark Mode

---

### Step 4.3: Launch All Three Tasks

**⏱️ Do this quickly - start all three within 2 minutes**

**TAB 1 - Task Counter:**
```
Add a counter that shows the number of active (not completed) tasks.

Requirements:
- Add a paragraph element below the h1 title that displays: "Active tasks: X"
- Update the counter whenever tasks are added, completed, or deleted
- Style it with gray text, centered, margin-bottom: 20px
- Update both the HTML and JavaScript

Test that it counts correctly.
```
**Click "Start Task"**

---

**Immediately switch to TAB 2 - Clear Completed:**
```
Add a "Clear Completed" button that removes all completed tasks from the list.

Requirements:
- Add a button below the task list
- Button text: "Clear Completed Tasks"
- Button should be styled with red background (#f44336)
- Only show the button if there are completed tasks
- Update script.js with a clearCompleted() function
- Update HTML structure

Test that it works.
```
**Click "Start Task"**

---

**Immediately switch to TAB 3 - Dark Mode:**
```
Add a dark mode toggle button to the app.

Requirements:
- Add a toggle button in the top-right corner of the container
- Button text: "🌙 Dark Mode" when light, "☀️ Light Mode" when dark
- Dark mode colors:
  * Background: #1a1a1a
  * Container: #2d2d2d
  * Text: #ffffff
  * Inputs: #404040 with white text
- Save preference to localStorage
- Apply saved preference on page load
- Update both HTML, CSS, and JavaScript

Test that it persists after page reload.
```
**Click "Start Task"**

---

**✅ CHECKPOINT:** All 3 tabs should now show "Working on task..." with progress

---

### Step 4.4: Monitor Progress

Now the magic happens - all 3 Claude instances are working simultaneously!

**Create a simple tracker** (use a text file or note app):

```
PARALLEL TASK TRACKER
Started: [Current time]

Tab 1 - Task Counter
Status: 🔄 Working
Branch: [will fill in when complete]

Tab 2 - Clear Completed
Status: 🔄 Working
Branch: [will fill in when complete]

Tab 3 - Dark Mode
Status: 🔄 Working
Branch: [will fill in when complete]
```

**Check each tab every 5 minutes:**
- Switch to Tab 1 → See status
- Switch to Tab 2 → See status
- Switch to Tab 3 → See status

**⏱️ Expected completion time:** 10-15 minutes for each task

---

### Step 4.5: As Tasks Complete

When a task finishes (you'll see "Task completed"):

1. **Copy the branch name** Claude created
2. **Update your tracker:**
   ```
   Tab 1 - Task Counter
   Status: ✅ Done
   Branch: claude-add-task-counter
   ```

3. **Don't merge yet!** Wait for all 3 to finish

**✅ CHECKPOINT:** When all 3 show "Task completed", you have 3 new branches

---

### Step 4.6: Review All Changes

Now let's see what our parallel agents created!

**Go to your GitHub repository:**

1. **Click "Pull requests"** tab
2. **You should see 3 pull requests!** (or you'll create them)

**For EACH branch, create a PR if not auto-created:**

**PR 1 - Task Counter:**
- Click the branch → "Compare & pull request"
- Title: "Add task counter feature"
- Review the changes - you should see:
  * New paragraph in HTML for counter
  * New `updateCounter()` function in JS
  * Counter updates called in appropriate places
  * CSS styling for counter

**PR 2 - Clear Completed:**
- Same process
- Review changes - you should see:
  * New "Clear Completed" button in HTML
  * New `clearCompleted()` function in JS
  * Button visibility logic
  * Red button styling in CSS

**PR 3 - Dark Mode:**
- Same process
- Review changes - you should see:
  * Toggle button in HTML
  * Dark mode CSS classes
  * JavaScript for toggle functionality
  * localStorage integration

**✅ CHECKPOINT:** 3 pull requests created, all with different changes

---

### Step 4.7: Handle Any Conflicts

**Check each PR for conflicts:**

**If NO conflicts:**
- ✅ Great! All tasks worked on different code sections

**If conflicts appear:**
- This is normal when tasks overlap
- **Solution:** Merge them one at a time

**Merge Order (if conflicts exist):**
1. Merge the SMALLEST change first
2. Then the medium change
3. Then the largest change
4. GitHub will auto-update remaining PRs

---

### Step 4.8: Merge All Three PRs

**Merge them in this order:**

**1. Merge PR 1 (Task Counter):**
```
1. Review changes one more time
2. Click "Merge pull request"
3. Click "Confirm merge"
4. Click "Delete branch"
```

**2. Merge PR 2 (Clear Completed):**
```
1. Refresh the PR page (it may auto-update)
2. If conflicts, click "Resolve conflicts" and fix
3. Click "Merge pull request"
4. Click "Confirm merge"
5. Click "Delete branch"
```

**3. Merge PR 3 (Dark Mode):**
```
1. Refresh the PR page
2. If conflicts, resolve them
3. Click "Merge pull request"
4. Click "Confirm merge"
5. Click "Delete branch"
```

**✅ CHECKPOINT:** All 3 PRs merged! Main branch has all 3 features!

---

## Part 5: Test Your Enhanced App (10 minutes)

### Step 5.1: View Your Updated App

**Option 1 - If using GitHub Pages:**
- Go to: `https://YOUR-USERNAME.github.io/todo-app-practice`
- Wait 1-2 minutes for GitHub Pages to rebuild
- Refresh the page

**Option 2 - Download and open locally:**
1. Click "Code" → "Download ZIP"
2. Unzip the file
3. Open `index.html` in your browser

---

### Step 5.2: Test All Features

**Test Checklist:**

**Task Counter:**
- [ ] Open the app
- [ ] See "Active tasks: 0" below the title
- [ ] Add a task → Counter shows "Active tasks: 1"
- [ ] Add another → Counter shows "Active tasks: 2"
- [ ] Mark one as complete → Counter shows "Active tasks: 1"
- [ ] Delete a task → Counter updates

**Clear Completed:**
- [ ] Mark 2 tasks as completed
- [ ] See "Clear Completed Tasks" button appear
- [ ] Click button → Completed tasks disappear
- [ ] Button hides when no completed tasks

**Dark Mode:**
- [ ] See dark mode toggle button (top-right)
- [ ] Click toggle → Background turns dark
- [ ] All text is readable
- [ ] Click again → Returns to light mode
- [ ] Refresh page → Mode is remembered

**✅ CHECKPOINT:** All 3 features work correctly!

---

## Part 6: Second Parallel Exercise (30 minutes)

Let's do another round with 4 tasks to solidify your skills!

### Step 6.1: Four New Features

We'll add:
1. **Priority levels** (High/Medium/Low for tasks)
2. **Filter buttons** (Show All/Active/Completed)
3. **Edit task** functionality
4. **Export to JSON** button

---

### Step 6.2: Launch All Four Tasks

**Open 4 Claude Code tabs:**

**TAB 1 - Priority Levels:**
```
Add priority levels to tasks with color coding.

Requirements:
- Add a dropdown select for priority when adding task (High/Medium/Low)
- Default to "Medium"
- Store priority in todo object
- Display priority with colored badges:
  * High: red background (#ff4444)
  * Medium: orange background (#ffaa00)
  * Low: green background (#44aa44)
- Badge should show before task text
- Update HTML, CSS, and JavaScript

Test with tasks of different priorities.
```

---

**TAB 2 - Filter Buttons:**
```
Add filter buttons to show All/Active/Completed tasks.

Requirements:
- Add three buttons above the todo list: "All", "Active", "Completed"
- Style them as a button group (side by side)
- Active button has darker background
- Clicking a button filters the displayed tasks
- "All" shows all tasks (default)
- "Active" shows only incomplete tasks
- "Completed" shows only completed tasks
- Update HTML, CSS, and JavaScript

Test all three filter modes.
```

---

**TAB 3 - Edit Task:**
```
Add ability to edit existing task text.

Requirements:
- Add "Edit" button next to each task (before Delete button)
- Clicking Edit:
  * Makes task text editable (convert to input field)
  * Shows "Save" and "Cancel" buttons
  * Hides Edit and Delete buttons
- Clicking Save updates the task text
- Clicking Cancel reverts changes
- Update HTML, CSS, and JavaScript

Test editing and canceling edits.
```

---

**TAB 4 - Export to JSON:**
```
Add export functionality to save todos as JSON file.

Requirements:
- Add "Export Todos" button at the bottom
- Clicking button downloads todos.json file with all tasks
- JSON should include: id, text, completed, timestamp
- Use proper JSON formatting
- Button styled with blue background (#2196F3)
- Update HTML, CSS, and JavaScript

Test that downloaded file contains correct data.
```

---

**✅ CHECKPOINT:** All 4 tasks running in parallel

---

### Step 6.3: Track and Merge

Use the same process:
1. Monitor every 5-10 minutes
2. Wait for all to complete
3. Review all 4 PRs
4. Merge in order (smallest to largest changes)
5. Test all features

**Time to complete:** 15-20 minutes

---

## Part 7: Troubleshooting Guide

### Problem 1: "Can't connect to GitHub"

**Symptoms:** Claude Code won't connect when you click "Connect GitHub"

**Solution:**
```
1. Sign out of Claude completely
2. Sign out of GitHub completely
3. Clear your browser cache
4. Sign back into GitHub first
5. Then sign into Claude
6. Try connecting again
```

**✅ CHECKPOINT:** Should see "GitHub Connected"

---

### Problem 2: Task Takes Too Long (>30 min)

**Symptoms:** Task is running but seems stuck

**Solution:**
```
1. Look at what Claude is doing (shown in interface)
2. If it seems stuck in a loop, close the tab
3. Start a new task with MORE specific instructions:

Instead of: "Add dark mode"
Use: "Add ONLY the dark mode CSS classes to style.css. 
      Do not modify HTML or JavaScript yet."

Then do HTML and JS in separate tasks.
```

**✅ CHECKPOINT:** Smaller tasks complete faster

---

### Problem 3: Merge Conflicts

**Symptoms:** PR shows "This branch has conflicts"

**Solution Option 1 - Let GitHub resolve:**
```
1. Click "Resolve conflicts"
2. GitHub shows the conflicting code
3. Delete the lines you don't want
4. Keep the lines you do want
5. Remove the <<< === >>> markers
6. Click "Mark as resolved"
7. Click "Commit merge"
```

**Solution Option 2 - Let Claude fix it:**
```
1. Start a NEW Claude Code task
2. Give this prompt:
   "The branch [branch-name] has merge conflicts with main.
    Please resolve the conflicts and keep both features working."
3. Claude will fix and push updated version
```

**✅ CHECKPOINT:** PR shows "Ready to merge"

---

### Problem 4: Feature Doesn't Work After Merge

**Symptoms:** App broken after merging PR

**Solution:**
```
1. Open browser console (F12 → Console tab)
2. Look for error messages
3. Start new Claude Code task:
   "There's an error in the merged code. The console shows: [error message]
    Please fix this bug and ensure [feature name] works correctly."
```

**✅ CHECKPOINT:** Feature works without console errors

---

### Problem 5: Hit Rate Limit

**Symptoms:** "Rate limit exceeded" message

**Solutions:**
```
Pro users: ~45 messages per 5 hours
- Wait 5 hours for reset
- OR upgrade to Max plan
- OR use a second account

Max users: ~100 messages per 5 hours
- Wait 5 hours for reset
- OR space out your tasks more
```

**Pro Tip:** Each parallel task uses messages independently. Running 3 tasks uses 3x the messages!

**✅ CHECKPOINT:** Can start new tasks again

---

### Problem 6: Wrong Files Modified

**Symptoms:** Claude changed files you didn't want changed

**Solution:**
```
1. DON'T merge the PR
2. Close it
3. Start new task with MORE specific instructions:

Bad prompt: "Add dark mode"
Good prompt: "Add dark mode ONLY by modifying style.css. 
              Add these specific CSS rules: [list rules]
              Do not modify HTML or JavaScript files."
```

**✅ CHECKPOINT:** PR only shows intended files changed

---

## Part 8: Practice Exercises

### Exercise 1: Solo Practice (Do on your own)

**Create 3 parallel tasks for:**
1. Add task timestamps (show when task was created)
2. Add task search/filter by text
3. Add task categories/tags

**Time limit:** 1 hour  
**Success criteria:** All 3 merged and working

---

### Exercise 2: Error Fixing Sprint

**Introduce 3 bugs** (make these changes manually in GitHub):

In `script.js`, break these:
```javascript
// Bug 1: Change line to: if (todoText = '') {
// Bug 2: Change line to: todos.pus(todo);
// Bug 3: Comment out: renderTodos();
```

**Create 3 parallel tasks to fix each bug**

**Time limit:** 30 minutes  
**Success criteria:** All bugs fixed, app works

---

### Exercise 3: New Project

**Start a NEW repository:** `calculator-app`

**Create 4 parallel tasks to build:**
1. HTML structure with display and buttons
2. CSS styling for calculator layout
3. Basic operations (add, subtract, multiply, divide)
4. Advanced features (clear, backspace, decimal)

**Time limit:** 90 minutes  
**Success criteria:** Working calculator app

---

## Part 9: Success Checklist

After completing this tutorial, you should be able to:

- [ ] Create a GitHub repository from scratch
- [ ] Connect Claude Code to your repository
- [ ] Start a single coding task
- [ ] Review and merge a pull request
- [ ] Start 3+ tasks in parallel
- [ ] Monitor multiple running tasks
- [ ] Handle merge conflicts
- [ ] Test features after merging
- [ ] Troubleshoot common problems
- [ ] Choose good tasks for parallel execution

**If you checked all boxes:** 🎉 Congratulations! You've mastered Claude Code parallel workflows!

---

## Part 10: Next Steps

### Skill Progression Path

**Week 1: Foundation**
- Run 2-3 parallel tasks daily
- Focus on simple features
- Build confidence with merges

**Week 2: Expansion**  
- Run 4-5 parallel tasks
- Mix features and bug fixes
- Faster review process

**Week 3: Optimization**
- Run 6+ parallel tasks
- Complex multi-file features
- Efficient workflow

**Week 4+: Mastery**
- Custom workflows
- Own projects
- Teaching others

---

### Real-World Applications

**Use parallel tasks for:**

**Daily Development:**
- Fix 3-5 small bugs at once
- Add multiple small features
- Update documentation across files
- Write tests for different modules

**Maintenance Sprints:**
- Update dependencies (each in parallel)
- Fix linting errors per file
- Update outdated code patterns
- Refactor different components

**Feature Development:**
- Frontend + Backend + Tests in parallel
- Different UI components
- Multiple API endpoints
- Documentation while coding

---

## Quick Reference Card

**Print This Page:**

```
╔══════════════════════════════════════════════════╗
║     CLAUDE CODE PARALLEL TASKS CHEAT SHEET       ║
╚══════════════════════════════════════════════════╝

BEFORE STARTING:
□ Tasks work on different files?
□ Tasks are independent (no dependencies)?
□ Instructions are specific and clear?

STARTING PARALLEL TASKS:
1. Open multiple tabs: claude.ai/code
2. Start each task within 2 minutes
3. Use specific prompts (what, where, how)

MONITORING:
✓ Check every 5-10 minutes
✓ Look for "Task completed" status
✓ Copy branch names as they finish

MERGING:
1. Review each PR individually
2. Merge smallest changes first
3. Resolve conflicts if needed
4. Test after each merge

TROUBLESHOOTING:
• Task stuck → Make prompt more specific
• Conflicts → Merge one at a time
• Wrong files → Be more specific about which files
• Rate limit → Wait or space out tasks

GOOD PROMPTS:
✓ "Add [feature] to [file] that does [specific thing]"
✓ "Fix [bug] in [file] on [line number]"
✓ "Update [specific section] to [specific change]"

BAD PROMPTS:
✗ "Make it better"
✗ "Fix everything"
✗ "Add more features"
```

---

## Resources

**Official Documentation:**
- Claude Code Docs: https://docs.claude.com/en/docs/claude-code
- GitHub Docs: https://docs.github.com

**Your Repository:**
- https://github.com/YOUR-USERNAME/todo-app-practice

**Questions?**
- Review Part 7 (Troubleshooting)
- Check the official docs
- Re-read relevant sections

---

**You're ready to start! Begin with Part 1 and work through each section carefully.**

*Tutorial Version: 2.0 - Practical Edition*  
*Last Updated: November 2025*  
*Zero Assumptions • Real Code • Hands-On*
