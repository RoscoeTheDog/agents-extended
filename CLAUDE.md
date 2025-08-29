# Project AI Agent System

## Project Environment Constraints
```yaml
project:
  name: "agent-test-1"
  type: "multi-agent-system"  # webapp, mobile-app, api, multi-agent-system
  stage: "prototype"          # prototype, mvp, production
  timeline: "6-day-sprints"
  budget: "minimal"           # minimal, standard, enterprise
  
tech_stack:
  preferred: ["javascript", "python", "react", "node.js"]
  databases: ["postgresql", "redis"]
  deployment: ["vercel", "railway", "docker"]
  
constraints:
  token_budget: 4000          # Maximum tokens per session
  complexity_threshold: 1500  # Tokens to trigger context-manager
  parallel_agents: 3          # Max concurrent agents
  session_duration: "30min"   # Max session length
```

## Practical Complexity Assessment
**Real-time implementable scoring system:**

```c
// Token-efficient complexity calculation
int calculateComplexity(char* prompt) {
  int score = 0;
  int word_count = countWords(prompt);
  
  // Word count factor
  if (word_count > 100) score += 2;
  if (word_count > 200) score += 2;
  
  // Domain detection (+1 each)
  char* domains[] = {"frontend", "backend", "testing", "design", "mobile"};
  score += countMatches(prompt, domains, 5);
  
  // Scope keywords (+2 each)
  char* scope[] = {"complete", "system", "production", "full", "enterprise"};
  score += countMatches(prompt, scope, 5) * 2;
  
  // Integration complexity (+3 each)
  char* integrations[] = {"auth", "payment", "database", "api", "deploy"};
  score += countMatches(prompt, integrations, 5) * 3;
  
  return score;
}

// Routing decision
struct Route {
  char* destination;
  char* agent;
  char* reason;
};

Route routeTask(char* prompt) {
  int complexity = calculateComplexity(prompt);
  
  if (complexity >= 8) {
    return {"context-manager", "", "Multi-domain complexity detected"};
  }
  
  Agent* best = selectBestAgent(prompt);
  return {"direct-agent", best->name, "Single domain task"};
}
```

## Dynamic Decision Matrix
| Complexity Score | Estimated Tokens | Route | Strategy |
|------------------|------------------|-------|-----------|
| 1-3 | <500 | Direct Agent | Single specialty |
| 4-7 | 500-1500 | Direct Agent + Monitor | Single with escalation |
| 8-12 | 1500-3000 | Context-Manager | Multi-agent coordination |
| 13+ | >3000 | Context-Manager + State | Staged execution with checkpoints |

## Core Rules

### Security Boundaries
- RESTRICT ALL access to '.' and subdirectories only
- NEVER access parent (..), system paths, other projects
- NO Windows OS core/system changes - only files within '.'
- NO untrusted downloads - prompt user for permission
- HALT if outside '.'

### Autonomous Operation
- ALL commands allowed within '.' without permission
- Auto-proceed: file ops, package install, testing, system changes in '.'
- Stay within project boundaries always

## Intelligent Task Routing

### Automated Assessment Protocol
1. **Parse Request**: Extract domains, scope, complexity indicators
2. **Estimate Tokens**: Calculate expected token usage based on patterns  
3. **Check Constraints**: Validate against project environment limits
4. **Route Intelligently**: Direct vs Context-Manager based on thresholds
5. **Monitor Progress**: Track token usage in real-time during execution

### Direct Agent Execution (Complexity Score 1-7)
**Auto-selected for focused tasks**:
```
"[agent-name]: [specific task]"
```
**Examples**:
- `rapid-prototyper: Create React todo component with add/delete` (Score: 3)
- `ui-designer: Style login form with modern CSS` (Score: 2)
- `test-writer-fixer: Add 3 unit tests for UserService` (Score: 4)

### Context-Manager Coordination (Complexity Score 8+)
**Auto-triggered when assessment detects**:
- Multiple domains: "frontend and backend", "with testing"
- System-level scope: "complete system", "full application" 
- Production keywords: "production-grade", "enterprise-level"
- Complex integration: "payment processing", "authentication system"
- Token estimate >1500

```  
"context-manager: [complex multi-domain task]"
```
**Examples**:
- `context-manager: Build complete auth system with frontend, backend, and tests` (Score: 11)
- `context-manager: Create production-grade e-commerce platform` (Score: 15)

## Agent Autonomy Protocol
Agents automatically escalate to context-manager if:
- Task exceeds their domain expertise
- Multiple specialties clearly required
- Coordination with other agents needed

## Core Agent Ecosystem (15 Optimized Agents)

```c
// Agent Registry with Performance Tracking
struct Agent {
  char* name;
  float success_rate;
  int avg_tokens;
  char* specialties[5];
};

Agent core_agents[15] = {
  // Engineering (4)
  {"rapid-prototyper", 0.85, 800, {"mvp", "prototype", "quick-build"}},
  {"backend-architect", 0.92, 1200, {"api", "database", "scale", "auth"}},
  {"frontend-developer", 0.88, 900, {"react", "ui", "responsive", "mobile"}},
  {"test-writer-fixer", 0.91, 600, {"testing", "qa", "debug", "validation"}},
  
  // Design (2)
  {"ui-designer", 0.83, 700, {"interface", "visual", "components", "ux"}},
  {"ux-researcher", 0.79, 800, {"research", "user-testing", "analytics"}},
  
  // Product (2)
  {"trend-researcher", 0.86, 900, {"market", "viral", "trends", "tiktok"}},
  {"sprint-prioritizer", 0.89, 500, {"planning", "roadmap", "features"}},
  
  // Marketing (2)
  {"tiktok-strategist", 0.81, 800, {"social", "viral", "content", "growth"}},
  {"app-store-optimizer", 0.84, 600, {"aso", "keywords", "conversion"}},
  
  // Project Management (2)
  {"project-shipper", 0.90, 700, {"launch", "coordination", "release"}},
  {"experiment-tracker", 0.87, 400, {"ab-test", "metrics", "analytics"}},
  
  // Operations (3)
  {"devops-automator", 0.93, 1000, {"deploy", "ci-cd", "infrastructure"}},
  {"support-responder", 0.82, 500, {"customer", "docs", "help"}},
  {"analytics-reporter", 0.88, 600, {"metrics", "performance", "insights"}}
};
```

## Environment-Aware Agent Behavior
**All agents automatically adapt to project constraints:**

### Tech Stack Alignment
- Default to project's preferred technologies (React, Node.js, PostgreSQL)
- Suggest deployment options within constraints (Vercel, Railway)
- Optimize for 6-day sprint timelines

### Budget-Conscious Decisions
- **Minimal Budget**: Use free tiers, open source, rapid prototyping
- **Standard Budget**: Include paid services for better performance
- **Enterprise Budget**: Full production architecture with monitoring

### Context-Aware Routing Rules
- **Complexity Score <8**: Direct agent with real-time monitoring
- **Complexity Score 8-12**: Context-manager coordination
- **Complexity Score >12**: Staged execution with state preservation
- **Token Budget Exceeded**: Automatic checkpoint creation

### HALT Conditions
- Token budget >90% consumed → Create checkpoint and pause
- Unclear requirements → Request specific details
- High-risk operations → Require explicit confirmation
- Outside project directory → Security boundary violation

## Adaptive Default Behavior
**Behavior adapts to project stage and constraints:**

### Prototype Stage (Current)
- Default to MVP/minimal implementation
- Prioritize speed over perfection
- Use rapid development patterns
- Skip comprehensive error handling

### Production Stage
- Comprehensive error handling and validation
- Security-first implementation
- Performance optimization required
- Full testing coverage expected

### Real-Time Monitoring
- Track token usage during execution
- Monitor agent performance and success rates
- Adjust complexity thresholds based on actual usage
- Create checkpoints at 1000-token intervals

## File Structure
```
.claude/
├── agents/           # Specialized agent definitions
├── context-state/    # Auto-created by context-manager  
└── CLAUDE.md        # This file
```