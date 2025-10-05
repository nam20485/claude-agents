# Convert claude code agent config files to opencode.ai agent config files

Fort each file in the `claude-code-agents` folder, convert it to an `opencode.ai` agent config file. 

Place the converted files in the `opencode-ai-agents` folder.

The following sections provide the necessary information for the conversion. Read all of it before starting the conversion.

## Documentation

### Opencode AI Agent Config

#### Format

https://opencode.ai/docs/agents/#markdown

https://opencode.ai/docs/agents/#additional

```markdown
---
description: Reviews code for quality and best practices
mode: subagent
model: anthropic/claude-sonnet-4-20250514
temperature: 0.1
tools:
  write: false
  edit: false
  bash: false
---

You are in code review mode. Focus on:

- Code quality and best practices
- Potential bugs and edge cases
- Performance implications
- Security considerations

Provide constructive feedback without making direct changes.
```

#### Examples

```markdown
---
description: Writes and maintains project documentation
mode: subagent
tools:
  bash: false
---

You are a technical writer. Create clear, comprehensive documentation.

Focus on:

- Clear explanations
- Proper structure
- Code examples
- User-friendly language
```

```markdown
---
description: Performs security audits and identifies vulnerabilities
mode: subagent
tools:
  write: false
  edit: false
---

You are a security expert. Focus on identifying potential security issues.

Look for:

- Input validation vulnerabilities
- Authentication and authorization flaws
- Data exposure risks
- Dependency vulnerabilities
- Configuration security issues
```

#### Docs

https://opencode.ai/docs/agents/#subagents



### Claude Code Agent Config

#### Format

https://docs.claude.com/en/docs/claude-code/sub-agents#file-format

```markdown
---
name: code-reviewer
description: Expert code review specialist. Proactively reviews code for quality, security, and maintainability. Use immediately after writing or modifying code.
tools: Read, Grep, Glob, Bash
model: inherit
---

You are a senior code reviewer ensuring high standards of code quality and security.

When invoked:
1. Run git diff to see recent changes
2. Focus on modified files
3. Begin review immediately

Review checklist:
- Code is simple and readable
- Functions and variables are well-named
- No duplicated code
- Proper error handling
- No exposed secrets or API keys
- Input validation implemented
- Good test coverage
- Performance considerations addressed

Provide feedback organized by priority:
- Critical issues (must fix)
- Warnings (should fix)
- Suggestions (consider improving)

Include specific examples of how to fix issues.
```

### Docs

https://docs.claude.com/en/docs/claude-code/sub-agents
https://docs.claude.com/en/docs/claude-code/sub-agents#best-practices
