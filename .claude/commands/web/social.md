---
name: web:social
description: Create social media content
argument-hint: "<workspace-name> [--channel linkedin|twitter|instagram] [--type post|carousel|thread|story]"
---
<objective>
Create social media content optimized for the target platform.

Workspace and channel: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/channel-specs.md
@./.claude/webos/references/writing-skill.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // SOCIAL >>`
2. Load workspace: BRAND.md, AUDIENCE.md, TOV.md, CHANNELS.md, PILLARS.md, LEARNINGS.md
3. Ask if not specified:
   - Channel (LinkedIn, Twitter/X, Instagram, TikTok)
   - Content type (text post, carousel, thread, story, reel script)
   - Topic or message
   - Goal (engagement, traffic, awareness, leads)

4. Load channel specs for the platform
5. Apply LEARNINGS.md channel insights
6. Generate web:
   - Match platform's native format
   - Apply TOV.md channel-specific adjustments
   - Include platform-specific elements (hashtags, hooks, CTAs)
   - Optimize for the algorithm (engagement signals)

7. Display with platform preview format
8. Suggest optimal posting time (from CHANNELS.md or LEARNINGS.md)
9. Ask: "Schedule? Add to calendar? Create variations?"
10. Save to content/approved/ and update CALENDAR.md
</process>
