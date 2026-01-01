# Rails Skills for Claude Code

Auto-activating skills that transform Claude Code into a Rails-savvy pair programmer. These skills provide concentrated best practices, ready-to-use patterns, and comprehensive references for the Rails ecosystem.

## What Are Skills?

Skills are modular knowledge packages for [Claude Code](https://code.claude.com/docs/en/skills). They auto-activate based on context - when you work on specs, the RSpec skill loads; when you write decorators, the Draper skill activates. No manual invocation needed.

## Included Skills

### ActiveRecord

**Triggers:** Writing migrations, defining associations, adding validations, optimizing queries, N+1 prevention

Comprehensive ActiveRecord reference covering:
- CRUD operations, conventions, dirty tracking, type casting
- Migrations, indexes, constraints, safe patterns
- Validations (built-in, custom, contexts) with constraint decision framework
- Callbacks, transaction callbacks, alternatives
- All association types (belongs_to, has_many, :through, polymorphic)
- Query interface, eager loading, scopes, batch processing

**References:** `basics.md`, `migrations.md`, `validations.md`, `callbacks.md`, `associations.md`, `querying.md`
**Examples:** Ready-to-use patterns for each topic area

### RSpec Testing

**Triggers:** Writing `*_spec.rb` files, discussing tests, TDD workflow, fixing failing specs

Comprehensive RSpec and FactoryBot reference covering:
- Test structure, `describe`/`context`/`it` blocks, `let`/`subject`
- All matchers (equality, collections, changes, errors, predicates)
- Test doubles, stubbing, spies, argument matchers
- FactoryBot strategies, traits, sequences, associations
- Rails spec types (model, request, system, job, mailer)
- Best practices and anti-patterns

**References:** `core.md`, `factory_bot.md`, `matchers.md`, `mocks.md`, `rails.md`
**Examples:** Ready-to-use patterns for all matchers, spec types, and FactoryBot features

### Draper Decorators

**Triggers:** Creating decorators, presentation logic, formatting model data for views

Complete guide to the Draper gem:
- Decorator philosophy and structure
- Delegation strategies, accessing helpers
- Association decoration, context passing
- Testing decorators with RSpec
- Common anti-patterns (N+1, fat decorators)

**References:** `patterns.md`, `testing.md`, `anti-patterns.md`
**Examples:** `application_decorator.rb`, `model_decorator.rb`, `decorator_spec.rb`

### MCP Server (Ruby)

**Triggers:** Creating MCP servers, building tools/prompts/resources, implementing Model Context Protocol in Rails

Complete guide to the `mcp` gem (maintained by Anthropic and Shopify):
- Design philosophy: context preservation, domain-aligned vocabulary, tool budget
- Tools, prompts, and resources definition patterns
- Server initialization and configuration
- STDIO and Streamable HTTP transports
- Rails controller integration
- Security considerations (the "lethal trifecta")

**References:** `tools.md`, `prompts.md`, `resources.md`, `server.md`, `transport.md`, `gotchas.md`
**Examples:** `stdio_server.rb`, `http_server.rb`, `rails_integration.rb`, `file_manager_tool.rb`

## Installation

```bash
# Clone to Claude Code skills directory
git clone https://github.com/hoblin/claude-code-rails-skills ~/.claude/skills

# Or add to existing skills
cd ~/.claude/skills
git init
git remote add origin https://github.com/hoblin/claude-code-rails-skills
git pull origin main
```

Skills are discovered automatically. Start Claude Code and work on your Rails project.

## Usage

Skills activate automatically based on what you're doing:

```
# Working on specs → RSpec skill loads
> "Write specs for the User model"
> "Fix this failing test"
> "How do I stub this service?"

# Working on decorators → Draper skill loads
> "Create a decorator for Order"
> "Add presentation logic for prices"
> "Test this decorator"
```

You can also explicitly activate: `activate rspec` or `activate draper-decorators`

## Why Skills?

Claude Code is a general-purpose assistant. It knows Rails, but not at the level of a senior Rails developer who has internalized years of best practices. These skills bridge that gap by providing:

- **Concentrated knowledge** - Best practices distilled, not scattered across docs
- **Ready-to-use patterns** - Copy-paste examples that follow conventions
- **Anti-pattern awareness** - Common mistakes and how to avoid them
- **Progressive disclosure** - Core concepts loaded first, deep references on demand

## Contributing

Found a pattern missing? Have a better example? PRs welcome.

## License

MIT
