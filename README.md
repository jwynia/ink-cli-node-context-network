# Ink CLI Context Network Template
This project is a starter template specifically designed for Ink CLI projects with built-in LLM management and navigation capabilities (more info at https://jwynia.github.io/context-networks/). It provides a structured approach to managing the complex web of decisions, designs, and domain knowledge that underlies React-based command-line application development.

Unlike generic context networks, this template is tailored to address the unique knowledge management challenges of Ink CLI development: React component architecture for terminals, user interaction design patterns, input handling strategies, terminal compatibility considerations, and the gap between "how we designed the CLI experience" and "what we built" creates dangerous knowledge silos in the evolving terminal UI ecosystem.

## Project Structure

This template uses a clear separation between planning and implementation:

```
project-root/
├── .context-network.md          # Discovery file
├── README.md                    # This file
├── .gitignore                   # Root-level git ignores
├── .devcontainer/               # Development container config
├── context-network/             # All planning & architecture docs
└── app/                         # Your Ink CLI project goes here
```

The `app/` directory is where your actual Ink CLI project will live - everything that would normally be in an Ink project root. This keeps the context network and development tooling separate from your CLI application code.

## Getting Started

To use this Ink CLI context network template:

1. **Clone this template** for your new Ink CLI project
2. **Connect with an LLM agent** that has file access to all files in the project folder (via IDE coding tools like Cursor or VSCode with Cline)
3. **Set up the prompts** (see below) to ensure the agent understands context networks
4. **Initialize your Ink project** in the `app/` directory using your preferred method:
   - `cd app && npx create-ink-app@latest .` for a new Ink CLI app
   - `cd app && npm init && npm install ink react` for a manual setup
   - `cd app && npx create-ink-app@latest --typescript .` for TypeScript
   - Or any other Ink CLI framework initialization
5. **Start a planning conversation** describing your CLI goals, user interactions, and terminal UI design
6. **Let the agent enhance the context network** with your project-specific information
7. **Begin development tasks** with clear separation between planning (context network) and implementation (app/)

This template maintains a clear boundary between knowledge artifacts (context network) and implementation artifacts (app/), allowing your team to document "why" and "how" separately from the Ink CLI code that represents "what is."

## Cost
Because context networks are a relatively cutting-edge approach to collaboration with LLM AI agents, these tools do cost money and some of the best of them can cost more money than you may be expecting. The costs on such things are dropping and much of what we're doing with context networks is figuring out the ways to work that will be more widespread next year and beyond, when these costs drop. If these tools are too expensive for your budget, that probably means you need to wait a bit.

## Tools
Cursor (https://www.cursor.com/) is an all-in-one that comes with LLM chat and an agent that can act on the files.

Cursor is built on VSCode (https://code.visualstudio.com/), which is a more generic code/text editor that can have plugins added. One we use a lot with context networks is Cline (https://cline.bot/). Cline's agent can be pointed at a wide range of LLM APIs that you use your own keys/billing for or their own management of that. A popular solution is to use OpenRouter (https://openrouter.ai/) which lets you use most of the LLM models available today.

## Patterns
### Prompts
For whatever agent you use, you need to include instructions in the system prompt or custom instructions that tell it about context networks and how to navigate them. The prompt in /inbox/custom-instructions-prompt.md is the one a lot of people are using for Cline with Claude Sonnet as the model.

Add it in either your agent's configuration screen or via its file-based prompt management system.

### Ink CLI Specific Documentation Patterns
This template includes specialized patterns for Ink CLI documentation:

1. **Component Architecture Decision Records** - Document Ink component choices and terminal UI patterns
2. **CLI Design Decisions** - Document command structure, argument parsing, and user interaction flows
3. **Input Handling Guidelines** - Keyboard shortcuts, focus management, and user input validation patterns
4. **Terminal Compatibility Strategy** - Document cross-platform terminal support and rendering considerations
5. **Testing Strategy** - ink-testing-library configuration and CLI interaction testing patterns
6. **User Experience Design** - CLI usability patterns, progressive disclosure, and error handling
7. **Technical Debt Registry** - Track Ink ecosystem updates and React component migration needs

### Plan/Act and Specific Scope
Cline and many other agents have multiple modes, usually offering one that lets you have a conversation with it separate from it taking action on files. In Cline, that's "Plan". In that mode, it won't make any changes to your files.

Use that mode aggressively to get to a specific plan for what will happen when you toggle to act. That plan should have a clear definition of what "done" will look like, should be as close to a single action as possible.

That often means that the action is to detail out a list of tasks that you'll actually have the agent do separately, one at a time. The "do one thing" can mean break the existing scope down another level to get to a more detailed plan. 

Basically, the more specific the action that Act mode or its equivalent is given, the better job it will do at managing token budget, at not volunteering to do a bunch of extra things,  and the more likely it does something you've already had a chance to approve.

### Monitor and Interrupt
The more you actually read and monitor what your agent is doing for anything that you disagree with or sounds incorrect and step in to interrupt, the better your context network will mature. Like hiring a new assistant, where for the first few weeks, you have to tell them your preferences and ways you want things done, it pays off over the long haul.

Interrupt, flip to Plan mode, and ask things like:

* How can we document into the context network a way of working so we don't repeat (the problem/misunderstanding above)?
* I'd really prefer we always write out a plan with tasks before doing things ad hoc. How can we clarify what's in the context network to make that our process going forward?


### Retrospective
At the end of tasks and periodically AS a new task, ask how things could be improved. For task end, "What from this conversation and task should be documented in the context network?" For periodic retrospectives, "What have we learned in this project that could be used to improve the context network for our efforts going forward?"

## Ink CLI Project Success Metrics

This context network template helps measure success through:

- **Time to first meaningful contribution** for new CLI developers
- **Component architecture decision speed** and confidence
- **Terminal UI consistency** across team members and platforms
- **Frequency of "archaeology" requests** (digging for lost CLI design knowledge)
- **Documentation coverage** of components, user interactions, and terminal interfaces
- **Decision traceability** for CLI design and component architecture choices
- **Documentation update frequency** relative to component changes and user feedback
- **Developer confidence** in making CLI user experience improvements
- **User understanding** of CLI functionality and interaction patterns
- **Reduction in repeated terminal compatibility mistakes**
- **User experience consistency** across different terminal environments
- **CLI performance and responsiveness** understanding and optimization

By maintaining a well-structured context network alongside your Ink CLI codebase, your team builds a shared brain that enables faster onboarding, better user experience decisions, and more confident evolution of complex terminal applications in the evolving CLI ecosystem.
