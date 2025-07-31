# Agentic Orb Test

A comprehensive testing project for the [cci-labs/agentic-cli](https://circleci.com/developer/orbs/orb/cci-labs/agentic-cli) CircleCI orb, demonstrating AI-powered automation workflows for GitHub repositories.

## 🤖 What This Project Demonstrates

This repository showcases how to integrate AI assistance directly into your CI/CD pipeline using the agentic-cli orb, which provides unified access to multiple AI providers:

- **Claude Code CLI** (Anthropic)
- **Gemini CLI** (Google)  
- **Rovo Dev CLI** (Atlassian)

## 📋 Available Workflows

### 1. PR Review Automation (`.circleci/pr-review.yml`)

Automatically reviews pull requests using Claude AI with comprehensive GitHub context:

- **Triggers**: PR opened, synchronized
- **Features**: 
  - Code quality analysis
  - Security vulnerability detection
  - Best practices recommendations
  - Performance optimization suggestions
  - Inline comments on specific code lines
- **Integrations**: GitHub MCP + CircleCI MCP for full context

### 2. Issue Comment Handler (`.circleci/issue_comment.yml`)

Responds intelligently to GitHub issue comments with AI assistance:

- **Trigger**: Comments containing `/agentic-orb` phrase
- **Features**:
  - Context-aware responses
  - Repository analysis
  - CI/CD insights
  - Actionable suggestions
- **User Control**: Permission-based access (OWNER, MEMBER, COLLABORATOR)

## 🚀 Quick Start

### Prerequisites

Set up the following environment variables in your CircleCI context named `agentic`:

```bash
ANTHROPIC_API_KEY=your_claude_api_key
GITHUB_API_TOKEN=your_github_token  
CIRCLECI_TOKEN=your_circleci_token
```

### Usage Examples

#### Test PR Review
1. Open a pull request
2. The AI will automatically analyze your code and provide feedback
3. Review the AI comments and suggestions

#### Test Issue Comments  
1. Create or comment on an issue with: `/agentic-orb help me analyze this bug`
2. The AI will respond with contextual analysis and suggestions
3. Continue the conversation as needed

## ⚙️ Configuration Options

### PR Review Customization

```yaml
- agentic-cli/pr_review_claude:
    context: agentic
    claude_model: sonnet  # or opus, haiku
    allowed_actions: opened,synchronize
    allowed_associations: OWNER,MEMBER,COLLABORATOR
    debug_mode: true
    exclude_draft: false
    # Optional filters:
    # target_branches: main,develop
    # require_label: needs-review
```

### Issue Comment Customization

```yaml
- issue_comment_handler:
    context: agentic
    # Optional overrides:
    # trigger_phrase: "/my-custom-trigger"
    # allowed_users: "user1,user2,user3"
```

## 🔧 Advanced Features

### MCP (Model Context Protocol) Integration

Both workflows leverage MCP servers for enhanced AI context:

- **GitHub MCP**: Full repository access, PR/issue context, user information
- **CircleCI MCP**: Pipeline status, build history, performance insights

### Multi-Model Support

While this project demonstrates Claude integration, the agentic-cli orb supports:

- **Claude**: Best for code review and analysis
- **Gemini**: Excellent for code generation and testing
- **Rovo**: Ideal for documentation and project management integration

## 📊 Orb Version

Currently using `cci-labs/agentic-cli@0.0.4` with latest features:

- Enhanced parameter structure
- Improved webhook handling
- Better permission controls
- Expanded MCP integration

## 🛡️ Security & Permissions

- **User Validation**: Only authorized users can trigger workflows
- **Token Management**: Secure handling of API credentials
- **Permission Scoping**: Granular control over who can interact with AI

## 📚 Learn More

- [Agentic CLI Orb Documentation](https://circleci.com/developer/orbs/orb/cci-labs/agentic-cli)
- [Claude Code CLI](https://github.com/anthropics/claude-code)
- [CircleCI Orbs Guide](https://circleci.com/docs/orb-intro/)

## 🤝 Contributing

This is a test project demonstrating the agentic-cli orb capabilities. Feel free to:

1. Fork and experiment with different AI models
2. Customize prompts and workflows  
3. Add new automation scenarios
4. Share feedback and improvements

---

**Ready to supercharge your development workflow with AI? Give it a try!** 🚀
