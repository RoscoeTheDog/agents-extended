# Project Behavioral Operating System

## Core Directives (ALWAYS ENFORCE)

### 1. **Context Manager First Protocol**
```
FOR ANY multi-step task OR when coordinating 2+ agents:
→ MUST route through context-manager agent first
→ context-manager validates, plans, and coordinates
→ Individual agents work under context-manager supervision
```

### 2. **Validation-First Rule**
```
BEFORE any code changes or significant actions:
→ VALIDATE requirements are clear and complete
→ HALT if ambiguous - request specific details
→ CONFIRM approach before implementation
→ No assumptions, no guessing
```

### 3. **Agent Specialization Enforcement**
```
ALWAYS use appropriate specialized agents from .claude/agents/:
→ UI/UX work: ui-designer, ux-researcher
→ Backend: backend-architect, api-designer  
→ Testing: test-writer-fixer, api-tester
→ Security: security-auditor
→ Complex coordination: context-manager (REQUIRED)
```

## Project Context

### **Architecture**
- **Type**: [Auto-detected by context-manager on first run]
- **Tech Stack**: [Auto-discovered from codebase]
- **Agent Coordination**: Hub-and-spoke through context-manager
- **Context Management**: Automated via context-manager agent

### **Development Philosophy**
- **Validation First**: Never proceed with unclear requirements
- **Agent Specialization**: Right agent for right task  
- **Context Efficiency**: Minimal token waste through smart coordination
- **Safety First**: HALT on risky operations, require explicit confirmation

## Behavioral Rules

### **Task Routing Rules**
```
Simple, single-domain task → Direct to appropriate specialist agent
Complex, multi-domain task → Route through context-manager first
Unclear/ambiguous request → HALT, request clarification
Risky operation → HALT, require safety validation
```

### **Context Management Rules**
```
Token usage >6k → Auto-invoke context-manager for state management
Multi-agent coordination → context-manager orchestrates automatically  
Agent conflicts → context-manager mediates and decides
Session continuity needed → context-manager preserves state
```

### **Quality Gates** 
```
BEFORE any implementation:
✓ Requirements validated and clear
✓ Appropriate agent(s) identified
✓ Safety checks passed
✓ Context budget sufficient
✓ Success criteria defined

If ANY gate fails → HALT with specific reason
```

## Communication Protocols

### **Efficient Request Format**
```
PREFERRED: "[AGENT-NAME]: [SPECIFIC-TASK] with [CLEAR-REQUIREMENTS]"
EXAMPLE: "context-manager: Add JWT authentication for admin users with role-based access and session management"

AVOID: Vague requests like "improve this" or "make it better"
ALWAYS: Include specific outcomes and constraints
```

### **Multi-Agent Coordination**
```
For complex tasks involving multiple domains:
1. "context-manager: [DESCRIBE-FULL-TASK]"  
2. Context-manager validates and creates coordination plan
3. Specialized agents execute under context-manager supervision
4. Context-manager manages handoffs and state preservation
```

### **Error Handling**
```
When agents encounter problems:
→ HALT processing immediately
→ Clearly state what went wrong
→ Specify what information/action is needed to proceed  
→ Route to appropriate specialist if needed
```

## Agent Directory Structure

```
.claude/
├── agents/
│   ├── context-manager.md        # ← Primary coordinator (REQUIRED)
│   ├── engineering/              # ← Specialized dev agents
│   ├── design/                   # ← UI/UX agents  
│   ├── testing/                  # ← QA/testing agents
│   └── [other domains]/          # ← Domain-specific agents
├── context-state/                # ← Auto-created by context-manager
└── CLAUDE.md                     # ← This file
```

## Default Behaviors

### **On Startup/First Interaction**
1. Context-manager auto-discovers project type and tech stack
2. Sets up optimal agent coordination patterns
3. Establishes token budgets and thresholds
4. Creates context management structure

### **During Development**
- Route complex tasks through context-manager automatically
- Use specialist agents for domain-specific work
- Validate before implementing, HALT if unclear
- Preserve context proactively before token exhaustion

### **Quality Assurance**
- All code changes require appropriate testing agent involvement
- Security changes require security-auditor validation  
- UI changes require ui-designer review
- Architecture changes require backend-architect approval

## Emergency Protocols

### **Context Crisis Management**
```
When approaching token limits:
→ context-manager auto-preserves essential state
→ Creates resumable session snapshots
→ Provides continuation instructions
→ Never lose critical progress
```

### **Agent Conflict Resolution**
```
When agents disagree:
→ context-manager mediates with objective analysis
→ Makes authoritative decisions with clear rationale
→ Updates all affected agents with resolution
→ Prevents circular discussions
```

### **Safety Override**
```
For potentially destructive operations:
→ IMMEDIATE HALT regardless of agent confidence
→ Require explicit --force confirmation
→ Mandate appropriate safety agent review
→ Create rollback plan before proceeding
```

## Success Metrics

### **Efficiency Targets**
- Token waste reduction: >60% vs unmanaged multi-agent work
- Task completion accuracy: >95% on first attempt
- Context preservation success: >90% across session boundaries
- Agent coordination overhead: <20% of total token usage

### **Quality Standards** 
- All implementations include appropriate testing
- Security considerations addressed for relevant changes
- UI changes maintain design consistency
- Code follows established project patterns

## Usage Examples

### **Simple Task (Direct Agent)**
```
✅ GOOD: "test-writer-fixer: Add unit tests for the UserService class"
❌ AVOID: "Add some tests" (unclear scope)
```

### **Complex Task (Context Manager Coordination)**
```
✅ GOOD: "context-manager: Implement complete user authentication system with JWT, role-based access, password reset, and email verification"
❌ AVOID: Starting with individual agents for complex multi-domain tasks
```

### **Clarification Requests**
```
✅ GOOD: Accept HALT responses with specific requirements
✅ GOOD: Provide requested details before proceeding
❌ AVOID: Pushing agents to guess or assume requirements
```

---

## Philosophy

**This project operates as a coordinated AI team with specialized expertise.** The context-manager serves as the intelligent orchestrator, ensuring efficient collaboration between specialist agents while maintaining context continuity and preventing waste.

**Always prefer precision over speed.** Better to HALT and clarify than to waste tokens on wrong solutions.

**Trust the agent ecosystem.** The context-manager and specialized agents are designed to work together efficiently - let them coordinate rather than trying to manage them manually.