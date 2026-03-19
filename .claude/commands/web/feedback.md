---
name: web:feedback
description: Submit feedback, report a bug, or request a feature
---
<objective>
Collect structured feedback about WEB:OS.
</objective>

<process>
1. Display: `<< WEB:OS // FEEDBACK >>`
2. Ask the user to choose:
   - Bug report
   - Feature request
   - General feedback
3. Collect details based on type:
   - **Bug report:** What happened, what was expected, steps to reproduce, which command was involved
   - **Feature request:** What feature, why it's needed, which workflow it improves
   - **General feedback:** Open-ended comments
4. Save to `global/FEEDBACK.md` with timestamp, type, and details
5. Thank the user and confirm the feedback was saved

Format in FEEDBACK.md:
```
## {timestamp} — {type}

**Command:** {command if applicable}
**Details:** {user's description}
**Status:** New
```
</process>
