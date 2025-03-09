# Claude Code Project Management Framework

## Overview
This repository contains a framework for effectively managing projects with Claude Code, providing structure for tracking progress, organizing features, and maintaining consistent documentation. This framework emphasizes writing high-quality code the first time ("Write Once" methodology) to maximize efficiency and reduce errors.

## Key Files Structure
This project management approach uses several key files to maintain organization:

- **README.md** (this file): Main documentation and overview
- **CLAUDE.md**: Project status and current framework details for Claude to reference
- **LESSONS.md**: Collection of lessons learned to save time and money
- **TASKLOG.md**: Detailed log of progress and current status
- **UNITESTS.md**: Testing framework documentation and lessons learned

## Project Management Template
The following template should be updated in your CLAUDE.md file:

### Project Overview
- Project name: [PROJECT_NAME]
- Current objective: [CURRENT_OBJECTIVE]
- Primary languages/frameworks: [LANGUAGES/FRAMEWORKS]
- Repository location: [REPO_LOCATION]

### Project Status Tracking
- Current milestone: [MILESTONE_NUMBER] - [MILESTONE_DESCRIPTION]
- Previous session accomplishments: [PREVIOUS_ACCOMPLISHMENTS]
- Known issues/blockers: [KNOWN_ISSUES]
- Next priorities: [NEXT_PRIORITIES]

### Feature Management
```json
[
  {
    "id": "F001",
    "name": "Feature Name",
    "status": "in-progress|completed|planned|blocked",
    "description": "Brief description of feature",
    "priority": "high|medium|low",
    "dependencies": ["F002", "F003"],
    "tasks": [
      {"id": "T001", "description": "Task description", "status": "complete|in-progress|planned"}
    ]
  }
]
```

## Working Methodology

### "Write Once" Methodology
1. First, identify the specific task or feature we're working on in this session
2. Review the current state of the codebase related to this task
3. Break down the work into small, testable chunks
4. For each chunk:
   - Plan the implementation thoroughly before writing any code
   - Confirm approach matches user requirements exactly before implementation
   - Write the complete code implementation correctly the first time
   - Write comprehensive tests for the implementation
   - Write clear documentation for the implementation
   - Only proceed to the next chunk when current one is fully complete
5. Document changes in the project status tracking section
6. Update the feature management JSON with progress

### Token Efficiency and Error Prevention Guidelines
- Use symbols like "+" to indicate additions and "-" for deletions rather than verbose descriptions
- Reference existing code by line numbers or function names rather than repeating full blocks
- Use file paths relative to project root (e.g., `src/components/Button.js`)
- For complex algorithms, design the complete approach before implementation to confirm direction
- Use shorthand where appropriate: fn (function), arr (array), obj (object), etc.
- When showing output, truncate with ellipses (...) for large responses
- **CRITICAL**: Do NOT write partial or incorrect implementations that need to be rewritten
- Implement code correctly the first time through careful planning and consideration
- Never deviate from the user's specified requirements or instruction set
- When in doubt about requirements, ask clarifying questions before implementation
- Prefer accuracy over speed - take time to get it right the first time

### Session Structure - Complete-As-You-Go Approach
1. **Initial Assessment**: Analyze current state and confirm session goals
2. **Planning**: Break down work into manageable chunks and explicitly confirm with user
3. **For each chunk**:
   - **Design**: Create detailed design before implementation
   - **Implementation**: Write complete, correct code the first time
   - **Testing**: Write comprehensive tests with multiple test cases
   - **Documentation**: Create user and technical documentation
   - **Review**: Confirm implementation meets requirements exactly
4. **Integration**: Ensure all components work together seamlessly
5. **Project Tracking**: Update feature management and tracking information
6. **Summary**: Provide concise summary of progress and next steps

## Command Shorthand
- `/status` - Show current project status
- `/feature [ID]` - Show details for specific feature
- `/next` - Suggest next logical task
- `/plan` - Generate plan for current session
- `/summary` - Generate session summary
- `/compact` - Run when context is at 25% to preserve work and prevent losing progress

## Context Management Best Practices

### Managing Context Window Effectively
- Run `/compact` when you reach approximately 25% of context window remaining
- This prevents Claude from running out of context and losing progress
- Always leave enough context to update LESSONS.md, TASKLOG.md, and UNITESTS.md

### After Compacting Context
Use the following prompt to get Claude back up to speed:

```
Please read your CLAUDE.md file, LESSONS.md, TASKLOG.md, and UNITESTS.md to get up to speed on this project. I need you to continue where you left off in performing [SPECIFIC_TASK].
```

For example:
```
Please read your CLAUDE.md file, TEST_COVERAGE_LOG.md, and UNITTESTS.md to get up to speed on this project. I need you to continue where you left off in writing the unit tests.
```

## File Maintenance

### Lessons Learned (LESSONS.md)
- Regularly update with failures and lessons learned to avoid repeating mistakes
- Include tips for saving time and money
- Structure entries with clear headings and actionable advice
- CLAUDE.md should include instructions to read this file upon every initialization

### Task Logging (TASKLOG.md)
- Update with progress after each meaningful chunk of work
- Document exactly where you are in the current task
- Include any blockers or issues encountered
- Note decisions made and their rationales

### Testing Documentation (UNITESTS.md)
- Document testing framework and approach
- Update with lessons learned specific to testing
- Only update when there are actual changes needed
- Keep focused on testing-specific information

## Testing Framework
- Write tests BEFORE or ALONGSIDE code implementation, following test-driven development principles
- Include unit tests for individual functions and components
- Include integration tests for feature interactions
- Test edge cases and error conditions explicitly
- Maintain a minimum test coverage of 80%
- Document test cases and expected results

## Documentation Standards
- Each function/method must have:
  - Purpose description
  - Parameter descriptions with types
  - Return value description with type
  - Usage examples
  - Edge cases or limitations
- Each module/file must have:
  - Overall purpose
  - Public API description
  - Dependencies
  - Configuration options
- Project-level documentation must include:
  - Installation instructions
  - Configuration guide
  - Usage examples
  - Troubleshooting section

## End of Session Template
```markdown
### Session Summary ([DATE])
- Time spent: [HOURS] hours
- Features worked on: [FEATURE_IDS]
- Completed tasks: [TASK_IDS]
- Progress summary: [BRIEF_SUMMARY]
- Next session priorities: [PRIORITIES]
- Updated project status: [STATUS_UPDATE]
```

## Long-term Tracking
- Keep a cumulative log of all session summaries in a separate file
- Update the feature management JSON at the end of each session
- Maintain a changelog of major version changes
- Document architectural decisions in a separate ADR file

## Lessons Learned

### File Organization
- Don't throw everything into one large file - it confuses Claude Code
- Create separate files for different aspects of the project
- Keep each file focused on its specific purpose

### Context Management
- Monitor context usage and run `/compact` at 25% remaining
- Always leave enough context to update tracking files
- Use file references to maintain continuity between sessions

### Implementation Approach
- Break tasks into small, manageable chunks
- Plan thoroughly before implementation
- Prioritize accuracy over speed
- Document as you go rather than at the end
