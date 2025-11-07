# Claude Code Parallel Tasks: Copy-Paste Prompt Library

**Ready-to-use prompts for common parallel task scenarios**

## 🎯 How to Use This Library

1. Find the scenario that matches your needs
2. Copy the exact prompts
3. Paste into Claude Code tabs
4. Modify the file names/details to match your project
5. Start all tasks within 2 minutes

---

## Scenario 1: Bug Fix Sprint

**Use when:** You have multiple bugs to fix in different files

### Bug Fix #1: Form Validation
```
Fix the email validation bug in src/components/LoginForm.js on line 23.

Current problem: Email validation accepts invalid emails like "test@"

Requirements:
- Use regex pattern: /^[^\s@]+@[^\s@]+\.[^\s@]+$/
- Show error message: "Please enter a valid email address"
- Error should appear below the email input field
- Test with: valid@email.com (should pass) and invalid@ (should fail)

Only modify LoginForm.js
```

### Bug Fix #2: Date Display
```
Fix the date formatting bug in src/utils/dateFormatter.js

Current problem: Dates display as "undefined" on the dashboard

Requirements:
- Function should handle null/undefined dates gracefully
- Return "Not set" for null/undefined dates
- Format valid dates as: "MMM DD, YYYY" (e.g., "Nov 06, 2025")
- Update the formatDate function only
- Add a test case for null dates

Only modify dateFormatter.js
```

### Bug Fix #3: Button State
```
Fix the disabled button state issue in src/components/SubmitButton.jsx

Current problem: Button stays disabled after form submission fails

Requirements:
- Reset button to enabled state after error
- Add proper error handling in the onClick handler
- Update button text to show "Submit" or "Submitting..."
- Button should be disabled only during active submission
- Add loading spinner during submission

Only modify SubmitButton.jsx
```

**⏱️ Expected time:** 10-15 minutes each  
**✅ Success criteria:** All three bugs fixed, no new errors introduced

---

## Scenario 2: UI Component Creation

**Use when:** Building multiple independent components

### Component #1: Loading Spinner
```
Create a reusable LoadingSpinner component.

File to create: src/components/LoadingSpinner.jsx

Requirements:
- Accept prop: size ('small' | 'medium' | 'large')
- Accept prop: color (default: '#3b82f6')
- Use CSS animation for smooth spinning
- Export as default component
- Add PropTypes validation
- Include example usage in comment

Component should render a spinning circular animation.
Create both the JSX file and a corresponding LoadingSpinner.css file.
```

### Component #2: Alert Banner
```
Create a reusable AlertBanner component.

File to create: src/components/AlertBanner.jsx

Requirements:
- Accept props: type ('success' | 'error' | 'warning' | 'info'), message, onClose
- Different colors for each type:
  * success: green background (#10b981)
  * error: red background (#ef4444)
  * warning: yellow background (#f59e0b)
  * info: blue background (#3b82f6)
- Include close button (X) that calls onClose
- Add icon for each type (✓ success, ✗ error, ⚠ warning, ℹ info)
- Auto-dismiss after 5 seconds (optional, controlled by autoDismiss prop)
- Export as default, add PropTypes

Create both JSX and CSS files.
```

### Component #3: Modal Dialog
```
Create a reusable Modal component.

File to create: src/components/Modal.jsx

Requirements:
- Accept props: isOpen, onClose, title, children
- Centered on screen with dark overlay background
- Overlay click closes modal
- ESC key closes modal
- Prevent body scroll when modal is open
- Include header with title and close button
- Smooth fade-in/fade-out animation
- Accessible (proper ARIA labels)
- Export as default, add PropTypes

Create both JSX and CSS files.
```

**⏱️ Expected time:** 20-25 minutes each  
**✅ Success criteria:** All components render correctly and are reusable

---

## Scenario 3: API Integration

**Use when:** Adding multiple API endpoints

### API #1: User Authentication
```
Create user authentication API endpoint.

File to create: src/api/auth.js

Requirements:
- Function: login(email, password)
- POST request to: /api/auth/login
- Return: { token, user } on success
- Handle errors: 401 (invalid credentials), 500 (server error)
- Set Authorization header for future requests
- Store token in localStorage
- Include try-catch error handling
- Use fetch API
- Add JSDoc comments

Export login, logout, and getCurrentUser functions.
```

### API #2: User Profile
```
Create user profile API functions.

File to create: src/api/userProfile.js

Requirements:
- Function: getProfile(userId)
  * GET request to: /api/users/${userId}
  * Return user profile data
- Function: updateProfile(userId, data)
  * PUT request to: /api/users/${userId}
  * Send updated profile data
  * Return updated profile
- Function: uploadAvatar(userId, file)
  * POST request with FormData to: /api/users/${userId}/avatar
  * Return new avatar URL
- Include auth token in all requests
- Proper error handling for each function
- Add JSDoc comments

Export all three functions.
```

### API #3: Todo Operations
```
Create todo CRUD API functions.

File to create: src/api/todos.js

Requirements:
- Function: getTodos()
  * GET /api/todos
  * Return array of todos
- Function: createTodo(text, priority)
  * POST /api/todos
  * Send { text, priority }
  * Return created todo with id
- Function: updateTodo(id, updates)
  * PUT /api/todos/${id}
  * Send update object
  * Return updated todo
- Function: deleteTodo(id)
  * DELETE /api/todos/${id}
  * Return success message
- Include auth token in all requests
- Proper error handling
- Add JSDoc comments

Export all functions.
```

**⏱️ Expected time:** 25-30 minutes each  
**✅ Success criteria:** All API functions work with proper error handling

---

## Scenario 4: Testing Suite

**Use when:** Writing tests for different modules

### Test Suite #1: Utility Functions
```
Create comprehensive tests for string utilities.

File to create: src/utils/__tests__/stringUtils.test.js

Test the following functions from src/utils/stringUtils.js:
- capitalize(str)
- truncate(str, maxLength)
- slugify(str)
- removeWhitespace(str)

Requirements for each function:
- Test with normal input
- Test with empty string
- Test with null/undefined
- Test with special characters
- Test edge cases (very long strings, etc.)
- Use Jest and expect assertions
- Group tests using describe blocks
- Each test should have clear description

Aim for 100% code coverage.
```

### Test Suite #2: React Components
```
Create tests for Button component.

File to create: src/components/__tests__/Button.test.jsx

Test the Button component at src/components/Button.jsx:

Requirements:
- Test: renders with default props
- Test: renders with custom text
- Test: calls onClick handler when clicked
- Test: applies custom className
- Test: shows loading state correctly
- Test: disables when disabled prop is true
- Test: renders different variants (primary, secondary, danger)
- Use React Testing Library
- Use @testing-library/user-event for interactions
- Mock functions with jest.fn()

Group related tests in describe blocks.
```

### Test Suite #3: API Integration
```
Create integration tests for auth API.

File to create: src/api/__tests__/auth.test.js

Test the auth API functions from src/api/auth.js:

Requirements:
- Mock fetch using jest.mock
- Test: login() with valid credentials (success case)
- Test: login() with invalid credentials (401 error)
- Test: login() with network error (500 error)
- Test: logout() clears localStorage
- Test: getCurrentUser() returns user when token exists
- Test: getCurrentUser() returns null when no token
- Verify localStorage.setItem and localStorage.removeItem are called
- Use beforeEach to reset mocks
- Use afterEach to cleanup

Each test should be isolated and independent.
```

**⏱️ Expected time:** 30-35 minutes each  
**✅ Success criteria:** All tests pass, good coverage

---

## Scenario 5: Documentation Updates

**Use when:** Updating docs for different features

### Documentation #1: API Reference
```
Create API documentation for user endpoints.

File to create: docs/api/users.md

Requirements:
Document these endpoints:
- GET /api/users/:id (Get user profile)
- PUT /api/users/:id (Update profile)
- POST /api/users/:id/avatar (Upload avatar)

For each endpoint include:
- HTTP method and URL
- Authentication requirements
- Request parameters (path, query, body)
- Request example with curl
- Response example (JSON)
- Possible error codes (400, 401, 404, 500)
- Error response examples

Use clear markdown formatting with code blocks.
Add a table of contents at the top.
```

### Documentation #2: Component Guide
```
Create component documentation.

File to create: docs/components/README.md

Requirements:
Document these components:
- Button
- Modal
- AlertBanner
- LoadingSpinner

For each component include:
- Brief description
- Available props (name, type, required, default, description)
- Usage example with code
- Screenshot or ASCII diagram if helpful
- Common use cases
- Accessibility notes

Use tables for props documentation.
Add code examples that can be copy-pasted.
```

### Documentation #3: Setup Guide
```
Update the project setup documentation.

File to update: README.md

Requirements:
Add/update these sections:
1. Prerequisites (Node.js version, npm/yarn)
2. Installation steps (clone, install, configure)
3. Environment variables needed (.env.example)
4. How to run locally (dev server, build, test)
5. Project structure (folder organization)
6. Available scripts (npm run commands)
7. How to contribute (branch naming, PR process)
8. License information

Use clear step-by-step formatting.
Add code blocks for terminal commands.
Include troubleshooting section.
```

**⏱️ Expected time:** 20-30 minutes each  
**✅ Success criteria:** Documentation is clear and complete

---

## Scenario 6: Styling & CSS

**Use when:** Updating styles for different sections

### Styling #1: Responsive Navigation
```
Make the navigation bar responsive.

File to modify: src/styles/navigation.css

Requirements:
- Desktop (>768px):
  * Horizontal menu with items side-by-side
  * Logo on left, menu on right
  * Dropdown menus on hover
- Tablet (768px):
  * Same as desktop but tighter spacing
- Mobile (<768px):
  * Hamburger menu icon (☰)
  * Vertical menu that slides in from left
  * Full-screen overlay when open
  * Close button (✕) in top-right
- Smooth transitions for all animations
- Touch-friendly hit areas (min 44px)

Test on viewports: 375px, 768px, 1024px, 1920px
```

### Styling #2: Card Components
```
Create and style card components.

File to create: src/styles/cards.css

Requirements:
Create three card variants:
1. Basic card (.card)
   - White background
   - Border radius 8px
   - Box shadow subtle
   - Padding 20px
2. Image card (.card-image)
   - Image at top (full width)
   - Content below with padding
   - Hover effect: lift with shadow
3. Interactive card (.card-interactive)
   - Cursor pointer
   - Scale up slightly on hover
   - Border color change on hover
   - Smooth transitions

All cards should be responsive.
Include dark mode styles using .dark class.
```

### Styling #3: Form Elements
```
Style all form elements consistently.

File to create: src/styles/forms.css

Requirements:
Style these elements:
- Input fields (text, email, password)
  * Height 44px, padding 12px
  * Border 2px solid #ddd
  * Focus: blue border, no outline
  * Error state: red border
- Textarea
  * Min height 120px
  * Resizable vertical only
- Select dropdowns
  * Match input styling
  * Custom arrow icon
- Checkboxes and radio buttons
  * Larger touch targets (24px)
  * Custom styling (not default)
- Submit buttons
  * Primary button style
  * Disabled state
  * Loading state

Include validation states (valid, invalid, required).
Add helper text styles (hints, errors).
```

**⏱️ Expected time:** 25-30 minutes each  
**✅ Success criteria:** Styles look consistent and work on all screen sizes

---

## Scenario 7: Configuration Files

**Use when:** Setting up project infrastructure

### Config #1: ESLint Setup
```
Configure ESLint for the project.

File to create: .eslintrc.json

Requirements:
- Extend from: eslint:recommended, plugin:react/recommended
- Parser options: ES2021, sourceType: module
- Environment: browser, es2021, node
- Rules to enforce:
  * No unused variables (error)
  * Consistent quotes (single quotes)
  * Semicolons required
  * Consistent indentation (2 spaces)
  * Max line length: 100
  * No console.log in production
- React specific rules:
  * Prop types required
  * No unused prop types
  * No unescaped entities
- Add scripts to package.json:
  * "lint": "eslint src/**/*.{js,jsx}"
  * "lint:fix": "eslint src/**/*.{js,jsx} --fix"

Create .eslintignore for node_modules, build, dist
```

### Config #2: Prettier Setup
```
Configure Prettier for code formatting.

File to create: .prettierrc.json

Requirements:
Configuration:
- Single quotes: true
- Semicolons: true
- Tab width: 2 spaces
- Trailing commas: es5
- Print width: 100
- Arrow function parentheses: always
- Bracket spacing: true
- JSX single quotes: false

Create .prettierignore:
- node_modules
- build
- dist
- coverage
- *.min.js

Add scripts to package.json:
- "format": "prettier --write \"src/**/*.{js,jsx,json,css,md}\""
- "format:check": "prettier --check \"src/**/*.{js,jsx,json,css,md}\""
```

### Config #3: Jest Setup
```
Configure Jest for testing.

File to create: jest.config.js

Requirements:
Configuration:
- Test environment: jsdom (for React)
- Setup files: setupTests.js
- Module name mapper for CSS/images
- Coverage thresholds:
  * Statements: 80%
  * Branches: 80%
  * Functions: 80%
  * Lines: 80%
- Collect coverage from: src/**/*.{js,jsx}
- Ignore: node_modules, build, dist
- Transform: babel-jest for JS/JSX files

Create setupTests.js:
- Import @testing-library/jest-dom
- Setup global test utilities

Add scripts to package.json:
- "test": "jest"
- "test:watch": "jest --watch"
- "test:coverage": "jest --coverage"
```

**⏱️ Expected time:** 15-20 minutes each  
**✅ Success criteria:** All configs work, linting/formatting/tests run

---

## Scenario 8: Performance Optimization

**Use when:** Optimizing different parts of the app

### Optimization #1: Image Loading
```
Implement lazy loading for images.

File to create: src/components/LazyImage.jsx

Requirements:
- Create LazyImage component
- Use Intersection Observer API
- Load image only when in viewport
- Show placeholder while loading:
  * Gray background with blur
  * Spinner in center
- Smooth fade-in when loaded
- Props: src, alt, className, placeholderSrc (optional)
- Handle loading errors:
  * Show broken image icon
  * Alt text displayed
- Export as default with PropTypes

Also create LazyImage.css for animations.
```

### Optimization #2: Code Splitting
```
Implement route-based code splitting.

File to modify: src/App.jsx

Requirements:
- Import React.lazy and Suspense
- Convert static imports to lazy imports for:
  * Home component
  * Dashboard component  
  * Profile component
  * Settings component
- Wrap routes in Suspense with fallback:
  * Show LoadingSpinner during load
  * Centered on screen
- Preserve all current routing logic
- Handle errors with Error Boundary
- Add comments explaining code splitting

Test that chunks load separately in dev tools.
```

### Optimization #3: Memoization
```
Add memoization to expensive components.

File to modify: src/components/Dashboard.jsx

Requirements:
- Wrap Dashboard in React.memo()
- Custom comparison function for props
- Identify expensive calculations:
  * User statistics calculation
  * Chart data transformation
  * Filtered/sorted lists
- Wrap calculations in useMemo:
  * Recalculate only when dependencies change
- Wrap callbacks in useCallback:
  * Prevent unnecessary re-renders
- Add comments explaining each optimization

Measure re-render performance using React DevTools.
```

**⏱️ Expected time:** 25-35 minutes each  
**✅ Success criteria:** Performance metrics improve, no functionality broken

---

## Scenario 9: Accessibility Improvements

**Use when:** Making the app more accessible

### A11y #1: Keyboard Navigation
```
Add comprehensive keyboard navigation.

File to modify: src/components/Navigation.jsx

Requirements:
- All interactive elements have tab order
- Dropdown menus:
  * Arrow keys navigate items
  * Enter/Space to select
  * Escape to close
- Skip to main content link (Tab first element)
- Focus visible indicators (outline)
- Focus trap in modal when open
- Tab cycles through modal only
- No keyboard traps
- Test with Tab, Shift+Tab, Arrow keys, Enter, Escape

Add tabIndex where needed.
Document keyboard shortcuts in comments.
```

### A11y #2: ARIA Labels
```
Add ARIA labels and roles throughout the app.

File to modify: src/components/TodoList.jsx

Requirements:
- Add role="main" to main content
- Add role="list" to ul
- Add role="listitem" to each li
- Add aria-label to all buttons without text
- Add aria-labelledby for form sections
- Add aria-describedby for help text
- Add aria-live regions for dynamic updates:
  * Task added announcement
  * Task completed announcement
  * Task deleted announcement
- Add aria-busy during loading
- Add aria-invalid for form errors

Test with screen reader (NVDA/JAWS/VoiceOver).
```

### A11y #3: Color Contrast
```
Fix color contrast issues for WCAG AA compliance.

File to modify: src/styles/theme.css

Requirements:
- Audit all text colors against backgrounds
- Ensure minimum contrast ratios:
  * Normal text: 4.5:1
  * Large text (18pt+): 3:1
  * Icons and graphics: 3:1
- Update colors that fail:
  * Make text darker or background lighter
  * Preserve visual design intent
- Focus indicators:
  * 3px outline minimum
  * High contrast color
- Add CSS custom properties for colors:
  * --text-primary
  * --text-secondary
  * --bg-primary
  * --accent-color

Test with browser contrast checker.
Document color palette with ratios.
```

**⏱️ Expected time:** 30-40 minutes each  
**✅ Success criteria:** Passes WCAG AA standards, keyboard navigable

---

## Scenario 10: Database Operations

**Use when:** Working with database schemas/queries

### Database #1: Schema Migration
```
Create database migration for user profiles.

File to create: migrations/001_create_user_profiles.sql

Requirements:
- Create user_profiles table:
  * id (primary key, auto-increment)
  * user_id (foreign key to users.id, unique)
  * bio (text, nullable)
  * avatar_url (varchar 500, nullable)
  * location (varchar 255, nullable)
  * website (varchar 500, nullable)
  * created_at (timestamp, default now)
  * updated_at (timestamp, default now)
- Add indexes:
  * Index on user_id
  * Index on created_at
- Add constraints:
  * user_id unique
  * user_id foreign key with ON DELETE CASCADE
- Include rollback migration (down)

Use PostgreSQL syntax.
Add comments for each section.
```

### Database #2: Seed Data
```
Create seed data for development.

File to create: seeds/001_seed_users.sql

Requirements:
Create sample data:
- 10 users with profiles
- 20 todos (mix of completed/incomplete)
- 5 categories
- Realistic names using various formats
- Mix of priorities
- Varied creation dates (last 30 days)
- Some users with avatars, some without

Include:
- INSERT statements with real-looking data
- Proper foreign key relationships
- Comments explaining each section
- Easy to reset (DELETE FROM before INSERT)

Use PostgreSQL syntax.
```

### Database #3: Query Functions
```
Create optimized database query functions.

File to create: src/db/todoQueries.js

Requirements:
Create these query functions:
1. getTodosByUser(userId)
   - Get all todos for user
   - Include category info (JOIN)
   - Order by created_at DESC
   - Pagination support (limit, offset)
2. searchTodos(userId, searchTerm)
   - Full text search on todo text
   - Filter by user
   - Case insensitive
3. getTodoStats(userId)
   - Count total todos
   - Count completed
   - Count by priority
   - Single query using aggregation

Use parameterized queries (prevent SQL injection).
Add JSDoc comments.
Include error handling.
Export all functions.
```

**⏱️ Expected time:** 20-30 minutes each  
**✅ Success criteria:** Migrations run successfully, queries are optimized

---

## Pro Tips for Using These Prompts

### ✅ DO:
1. **Copy prompts exactly first time**
2. **Modify file paths to match your project**
3. **Start all parallel tasks within 2 minutes**
4. **Review each PR before merging**

### ❌ DON'T:
1. **Don't change requirements drastically**
2. **Don't start tasks that depend on each other**
3. **Don't merge without testing**
4. **Don't run too many tasks (start with 3-4)**

---

## Quick Prompt Template

**Use this template to create your own prompts:**

```
[Action] in [File Path]

Current problem: [What's wrong or missing]

Requirements:
- [Specific requirement 1]
- [Specific requirement 2]
- [Specific requirement 3]
- [Testing requirement]

Only modify [specific files]
```

**Example filled in:**
```
Add email validation in src/components/ContactForm.jsx

Current problem: Form accepts invalid emails

Requirements:
- Use regex: /^[^\s@]+@[^\s@]+\.[^\s@]+$/
- Show error message below input
- Prevent submission if invalid
- Test with valid and invalid emails

Only modify ContactForm.jsx
```

---

## Success Metrics

After using these prompts, track:
- ✅ How many parallel tasks completed successfully
- ✅ Average time per task
- ✅ Number of merge conflicts
- ✅ Features working after merge

**Goal:** 90%+ success rate with minimal conflicts

---

*Library Version: 1.0*  
*Last Updated: November 2025*  
*Copy, Paste, Launch!*
