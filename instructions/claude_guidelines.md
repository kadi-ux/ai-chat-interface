# AI Chat Interface - VS Code Claude Development Instructions

## Project Context & Assignment Requirements

**Student**: Nikolas Daniel Vincenti  
**Course**: DLBCSPJWD01 - Project Java and Web Development  
**Phase**: 2 (Development & Implementation)  
**Due**: Complete working application + 10-slide presentation

### Critical Assignment Requirements (MUST IMPLEMENT)
✅ **Frontend-backend communication** (REST API)  
✅ **Two dynamic aspects**: (1) Real-time chat interface, (2) Settings management  
✅ **Responsive design** (Tailwind CSS, mobile-first)  
✅ **Functioning application** (not mockups - must actually work)  
✅ **Demo mode** (tutors can evaluate without OpenAI API keys)  
✅ **GitHub repository** with complete documentation  

## Application Architecture Overview

**Concept**: Privacy-first ChatGPT-like interface where users provide their own OpenAI API keys
- **Frontend**: React 18 + Vite + Tailwind CSS (responsive, modern UI)
- **Backend**: Node.js + Express (secure API proxy, never exposes API keys to frontend)
- **Security**: API keys handled backend-only, session-based, never stored permanently
- **Integration**: OpenAI SDK for GPT-3.5-turbo and GPT-4 model selection

## Project Structure
```
ai-chat-interface/
├── frontend/                 # React + Vite + Tailwind
│   ├── src/
│   │   ├── components/       # React components
│   │   ├── hooks/           # Custom React hooks
│   │   ├── utils/           # Utility functions
│   │   ├── App.jsx          # Root component
│   │   └── main.jsx         # Vite entry point
├── backend/                 # Express API server
│   ├── routes/              # API route definitions
│   ├── middleware/          # Express middleware
│   ├── utils/               # Backend utilities
│   ├── server.js            # Main server file
└── docs/                    # Documentation
```

## Development Priority & Implementation Order

### PHASE 1: Frontend Foundation (Build these first)
**Focus**: Create working UI with mock data, responsive design

#### 1.1 Component Architecture
```
src/components/
├── ChatInterface.jsx        # Main container (orchestrates everything)
├── MessageList.jsx          # Displays conversation history
├── MessageInput.jsx         # User input with submit handling
└── SettingsPanel.jsx        # API key input, model selection, demo toggle
```

#### 1.2 Required Frontend Features
- **ChatInterface.jsx**: Main layout, responsive grid, state coordination
- **MessageList.jsx**: Message bubbles (user/assistant), markdown rendering, auto-scroll
- **MessageInput.jsx**: Textarea with submit button, character limit, loading states
- **SettingsPanel.jsx**: API key input field, model dropdown (GPT-3.5/GPT-4), demo mode toggle

#### 1.3 Responsive Design Requirements (Tailwind CSS)
- **Mobile-first approach**: `sm:`, `md:`, `lg:` breakpoints
- **Chat interface**: Stack vertically on mobile, side-by-side on desktop
- **Settings panel**: Slide-out drawer on mobile, sidebar on desktop
- **Message bubbles**: Proper spacing and readability on all screens

### PHASE 2: State Management & Hooks
**Focus**: React state management without external dependencies

#### 2.1 Custom Hook: useChat.js
```javascript
// Must implement:
const useChat = () => {
  // Conversation history state
  // Loading states for API calls
  // Error handling state
  // Settings state (API key, model, demo mode)
  // Functions: sendMessage, clearChat, toggleDemo
};
```

#### 2.2 State Requirements
- **Messages array**: `[{id, content, role: 'user'|'assistant', timestamp}]`
- **Settings object**: `{apiKey, model: 'gpt-3.5-turbo'|'gpt-4', demoMode: boolean}`
- **UI states**: `{isLoading, error, settingsOpen}`

### PHASE 3: Backend API Implementation
**Focus**: Express server with OpenAI integration, security middleware

#### 3.1 Server Setup (server.js)
```javascript
// Required middleware:
// - CORS (allow frontend origin)
// - Rate limiting (prevent abuse)
// - Helmet (security headers)
// - Express.json() (parse JSON bodies)
// - Input validation middleware
```

#### 3.2 API Endpoints Required
```
POST /api/chat          # Send message, get AI response
POST /api/validate-key  # Validate OpenAI API key
GET /api/models         # Return available models
GET /api/demo          # Get demo responses
```

#### 3.3 Security Implementation
- **API Key Handling**: Never store permanently, session-only
- **Input Validation**: Sanitize all user inputs
- **Rate Limiting**: Prevent spam/abuse
- **Error Handling**: Never expose internal errors to frontend

### PHASE 4: OpenAI Integration
**Focus**: Secure API communication, model selection, error handling

#### 4.1 OpenAI Integration Requirements
```javascript
// Backend only - use OpenAI SDK
// Handle both GPT-3.5-turbo and GPT-4
// Proper error handling for:
// - Invalid API keys
// - Rate limiting
// - Network issues
// - Model availability
```

#### 4.2 Demo Mode Implementation (CRITICAL for evaluation)
```javascript
// Create realistic demo responses that simulate:
// - Coding assistance
// - General questions
// - Error scenarios
// - Different conversation flows
// Demo mode must be easily toggleable
```

## Technical Implementation Guidelines

### Frontend Development Rules
1. **Use only functional components** with React hooks
2. **Tailwind CSS only** - no custom CSS files
3. **Mobile-first responsive design** - test on mobile viewport
4. **No external state management** - use React built-in state only
5. **Axios for API calls** - handle loading states and errors
6. **Component documentation** - JSDoc comments for each component

### Backend Development Rules
1. **Express middleware pattern** - modular, reusable middleware functions
2. **RESTful API design** - proper HTTP methods and status codes
3. **Comprehensive error handling** - user-friendly error messages
4. **Security first** - never expose sensitive data
5. **OpenAI SDK usage** - official library, not manual HTTP requests

### Code Quality Standards
1. **Clean, readable code** - descriptive variable names, logical structure
2. **Consistent formatting** - use Prettier if available
3. **Comprehensive comments** - explain complex logic and decisions
4. **Error boundaries** - React error boundaries for stability
5. **Input validation** - both frontend and backend validation

## Specific Implementation Tasks

### Task 1: Create ChatInterface.jsx
```javascript
// Requirements:
// - Responsive layout (mobile: stack, desktop: sidebar)
// - State management for messages, settings, UI states
// - Integration points for all child components
// - Proper loading states and error displays
// - Demo mode toggle functionality
```

### Task 2: Create MessageList.jsx
```javascript
// Requirements:
// - Display message array as chat bubbles
// - Different styling for user vs assistant messages
// - Auto-scroll to latest message
// - Proper spacing and typography
// - Handle empty state (no messages yet)
```

### Task 3: Create MessageInput.jsx
```javascript
// Requirements:
// - Textarea with submit button
// - Handle Enter key submission (with Shift+Enter for new line)
// - Character/token limit display
// - Disable during loading states
// - Clear input after successful submission
```

### Task 4: Create SettingsPanel.jsx
```javascript
// Requirements:
// - API key input (password type, validation feedback)
// - Model selection dropdown (GPT-3.5-turbo, GPT-4)
// - Demo mode toggle switch
// - Responsive: drawer on mobile, sidebar on desktop
// - Real-time validation feedback
```

### Task 5: Implement useChat Hook
```javascript
// Requirements:
// - Manage conversation state
// - Handle API communication
// - Implement demo mode logic
// - Error handling and recovery
// - Loading state management
```

### Task 6: Backend Server Setup
```javascript
// Requirements:
// - Express server with security middleware
// - CORS configuration for frontend
// - Rate limiting implementation
// - Input validation middleware
// - Comprehensive error handling
```

### Task 7: API Endpoints Implementation
```javascript
// Requirements:
// - POST /api/chat (main chat endpoint)
// - POST /api/validate-key (API key validation)
// - GET /api/demo (demo responses)
// - Proper HTTP status codes
// - Structured JSON responses
```

### Task 8: OpenAI Integration
```javascript
// Requirements:
// - Secure API key handling
// - Model selection support
// - Streaming responses (if time permits)
// - Comprehensive error handling
// - Rate limiting compliance
```

## Development Workflow

### Step-by-Step Implementation Order
1. **Start with ChatInterface.jsx** - basic layout and structure
2. **Implement MessageList.jsx** - with mock data for testing
3. **Create MessageInput.jsx** - functional input handling
4. **Build SettingsPanel.jsx** - complete settings management
5. **Implement useChat hook** - connect everything together
6. **Setup Express server** - basic server with middleware
7. **Create API endpoints** - start with demo mode
8. **Integrate OpenAI API** - real AI functionality
9. **Test and polish** - responsive design, error handling

### Testing Strategy
- **Component testing**: Test each component with mock data
- **API testing**: Use demo mode to verify frontend-backend communication
- **Responsive testing**: Test on mobile viewport in browser dev tools
- **Error handling**: Test invalid inputs, network failures, API errors
- **Demo mode**: Ensure tutors can evaluate without API keys

## Critical Success Factors

### Assignment Evaluation Criteria (40% of grade = Implementation Quality)
1. **Functioning application** - must actually work, not just look good
2. **Clean code quality** - readable, documented, organized
3. **Responsive design** - works on mobile and desktop
4. **Security implementation** - proper API key handling
5. **Demo mode functionality** - evaluators can test without API keys

### Common Pitfalls to Avoid
1. **Don't expose API keys to frontend** - backend proxy only
2. **Don't skip responsive design** - test mobile viewport constantly
3. **Don't forget demo mode** - critical for evaluation
4. **Don't skip error handling** - graceful failures required
5. **Don't rush documentation** - code comments are part of grade

## File Creation Priority

### Create in this exact order:
1. `frontend/src/components/ChatInterface.jsx`
2. `frontend/src/components/MessageList.jsx`
3. `frontend/src/components/MessageInput.jsx`
4. `frontend/src/components/SettingsPanel.jsx`
5. `frontend/src/hooks/useChat.js`
6. `frontend/src/utils/api.js`
7. `backend/server.js`
8. `backend/routes/chat.js`
9. `backend/middleware/` files
10. Documentation and README updates

## Questions to Ask During Development

### When implementing each component:
1. "Is this component responsive on mobile?"
2. "Does this handle loading and error states?"
3. "Is the code well-documented?"
4. "Does this work in demo mode?"
5. "Is this secure (no API key exposure)?"

### Before completing each phase:
1. "Does the application actually function?"
2. "Can a tutor evaluate this without API keys?"
3. "Is the GitHub repository properly organized?"
4. "Are installation instructions clear?"

## Immediate Next Steps

1. **Configure Tailwind CSS** in the frontend project
2. **Create basic project structure** (folders and initial files)
3. **Implement ChatInterface.jsx** with basic responsive layout
4. **Add MessageList.jsx** with mock message data
5. **Test responsive design** in browser dev tools

Remember: The goal is a **functioning application**, not just a visual mockup. Every feature you implement must actually work when tested.