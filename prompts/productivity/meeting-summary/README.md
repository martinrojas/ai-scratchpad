# Meeting Summary

Generates structured, actionable meeting summaries from transcripts or notes.

## Overview

This prompt transforms raw meeting transcripts, audio transcriptions, or rough notes into polished, actionable summaries with clear decisions, action items, and follow-up tasks.

## Use Cases

- **Team Meetings**: Standup summaries, planning sessions, retrospectives
- **Client Calls**: Requirements gathering, project updates, stakeholder meetings
- **Technical Discussions**: Architecture reviews, design sessions, problem-solving meetings
- **1-on-1s**: Manager check-ins, performance discussions, feedback sessions

## Quick Start

### Using with ChatGPT

1. Go to ChatGPT > Explore GPTs > Create
2. Copy the contents of [prompt.md](prompt.md) into the Instructions field
3. Start a conversation and paste your meeting transcript

### Using with Claude

1. Start a new conversation
2. Paste the prompt from [prompt.md](prompt.md) followed by your meeting transcript
3. Ask for a structured summary

### Example Usage

```
[Paste the meeting summary prompt]

Here's the transcript from our planning meeting:

[Paste your meeting transcript or notes]

Please create a summary with action items.
```

## Output Format

The assistant generates summaries with:

### 1. Meeting Metadata
- Date and participants
- Meeting type and duration
- Overall context

### 2. Key Discussion Points
- Main topics covered
- Important context and background
- Decisions made

### 3. Action Items
Clear, assignable tasks with:
- Owner
- Due date (if mentioned)
- Priority level
- Dependencies

### 4. Follow-up Questions
- Open questions requiring answers
- Clarifications needed
- Information gaps

### 5. Next Steps
- Immediate priorities
- Future meeting needs
- Documentation requirements

## Key Features

### Intelligent Parsing
- Extracts signal from noise
- Identifies key decisions
- Surfaces action items automatically

### Structured Output
- Consistent formatting
- Scannable sections
- Easy to share and archive

### Action-Oriented
- Clear ownership assignments
- Explicit next steps
- Trackable outcomes

### Context Preservation
- Links decisions to discussion
- Captures rationale
- Maintains important details

## Customization

### Adding Company Context

Edit [prompt.md](prompt.md) to include:
- Team member names and roles
- Project names and acronyms
- Company-specific terminology
- Standard meeting formats

### Custom Output Format

Modify the prompt to match your:
- Meeting summary template
- Project management tool format
- Team documentation standards

### Integration with Tools

Adapt output for:
- JIRA/Linear (action items as tickets)
- Notion/Confluence (formatted docs)
- Slack/Teams (digest format)
- Email (structured updates)

## Tips for Best Results

1. **Clean Transcripts**: Remove filler words and cross-talk for clarity
2. **Add Context**: Include meeting title and participants if not in transcript
3. **Specify Format**: Request specific output format if needed
4. **Highlight Priorities**: Ask to emphasize critical items
5. **Request Clarification**: Follow up on ambiguous action items

## Example Input/Output

### Input
```
Team Planning Meeting - Nov 20, 2025
Attendees: Sarah (PM), Mike (Eng), Lisa (Design)

Sarah: OK let's talk about the new user dashboard. We need to ship by end of Q1.
Mike: I think we should use React for this, but we need to decide on state management.
Lisa: I can have designs ready by next week if we finalize requirements today.
Sarah: Great. Mike, can you research Redux vs Zustand and let us know by Friday?
Mike: Sure, I'll put together a comparison doc.
Sarah: Perfect. Lisa, let's sync Monday to review your designs.
```

### Output
```
# Team Planning Meeting Summary

**Date**: November 20, 2025
**Participants**: Sarah (PM), Mike (Engineering), Lisa (Design)
**Topic**: New User Dashboard Planning

## Key Decisions
- Project deadline: End of Q1 2025
- Technology: React (confirmed)
- State management: TBD pending research

## Action Items

**High Priority**
- [ ] **Mike**: Research Redux vs Zustand, create comparison doc (Due: Friday, Nov 24)
- [ ] **Lisa**: Finalize designs based on requirements (Due: Next week)

**Follow-up Meetings**
- [ ] **Sarah + Lisa**: Design review sync (Scheduled: Monday)

## Discussion Points
- User dashboard project kicked off
- State management solution needs decision
- Design timeline aligned with development needs

## Next Steps
1. Mike completes state management research
2. Sarah and Lisa review designs Monday
3. Team reconvenes with state management decision and approved designs
```

## Platform Notes

Works on any AI platform that accepts system prompts. No special knowledge documents required.

## Contributing

Have improvements or variant formats? See [CONTRIBUTING.md](../../../CONTRIBUTING.md).

## Related Prompts

- [Documentation Maintenance](../../development/documentation-maintenance/) - For maintaining meeting notes over time

---

**Last Updated**: 2025-11-20
