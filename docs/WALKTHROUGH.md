# Job Hunt Stack: Session Lifecycle Walkthrough
### How the System Flows Together

---

## Why Sessions Matter

AI assistants don't remember previous conversations by default. Every time you start a new chat, the AI starts from zero. The Job Hunt Stack solves this with a session lifecycle: a repeatable process that loads your context at the start, captures new knowledge during the session, and archives everything at the end so the next session picks up where you left off.

---

## The Five Pillars

| Pillar | File | Purpose |
|--------|------|--------|
| **Rules** | `Rules/Global Instructions.md` | Hard rules the AI must follow every session |
| **Primer** | `Cold Start Primer.md` | The session boot sequence. Updated at every session close. |
| **Identity** | `Identity/[User] Profile.md` | Your professional source of truth |
| **Lessons** | `Master Lessons Learned.md` | A living log of insights from every session |
| **Archive** | `Archive Protocol.md` | The session close checklist |

---

## A Session from Start to Finish

### Step 1: Open a New Chat
Start a new conversation with your AI assistant. The AI knows nothing yet.

### Step 2: Load Global Instructions
If your AI platform supports system-level instructions (Claude Cowork, custom GPTs, etc.), your Global Instructions are already loaded automatically. If not, paste the contents of `Rules/Global Instructions.md` at the start of the conversation.

### Step 3: Load the Cold Start Primer
Give the AI the `Cold Start Primer.md` file. This tells the AI who you are, what agents are available, what happened last session, and what needs to happen next.

### Step 4: Load the Right Agent

| If you need to... | Load this agent |
|-------------------|----------------|
| Search for new job leads | `Agents/TSA J Search.md` |
| Triage and evaluate leads | `Agents/TSA J Leads.md` |
| Write cover letters or tailor resumes | `Agents/TSA Port.md` |
| Plan your schedule or coordinate tasks | `Agents/TSA Flo.md` |

### Step 5: Do the Work
With context loaded, the AI is fully operational. Work with it as a collaborator.

### Step 6: Capture Lessons Learned
Before closing, review what happened and add insights to `Master Lessons Learned.md`.

### Step 7: Run the Archive Protocol
Follow the checklist in `Archive Protocol.md`: write a session summary, update Cold Start Primer Section 3, and save to `06_ARCHIVE/`.

### Step 8: Done
Close the chat. The next session boots up right where you left off.

---

## How the Pieces Connect

```
SESSION START
|
├── Global Instructions (always active)
|   └── Sets: rules, naming, values, formatting
|
├── Cold Start Primer
|   ├── Points to: Identity Profile
|   ├── Points to: Agent files
|   ├── Contains: Last session status (Section 3)
|   └── Contains: Startup checklist
|
├── Agent File (loaded per task)
|   ├── References: Identity Profile (for user data)
|   ├── References: Tracker (for pipeline state)
|   └── Follows: Global Instructions rules
|
├── THE WORK HAPPENS HERE
|   ├── Produces: Cover letters, resumes, LeadCards
|   ├── Updates: Tracker spreadsheet
|   └── Generates: New insights
|
├── Lessons Learned (captured during/after work)
|   └── Feeds into: Future sessions via Cold Start Primer
|
└── Archive Protocol (session close)
    ├── Writes: Session summary to 06_ARCHIVE/
    ├── Updates: Cold Start Primer Section 3
    └── Carries forward: Everything the next session needs

SESSION END
```

---

## The DUPE and delete.me System

Over time, you'll accumulate duplicate files and retired files. Don't delete anything immediately.

- **DUPE/**: Put duplicate or superseded files here. Note which file is canonical.
- **delete.me/**: Put retired files here. Things you're confident you don't need anymore.

Both folders have a README. Periodically review and permanently delete what you're sure about. This two-stage system prevents accidental loss.

---

## Common Questions

**Q: Do I need to load everything every session?**
A: Global Instructions and Cold Start Primer, yes. Agent files, only the one(s) you need.

**Q: What if I forget to run the Archive Protocol?**
A: Your next session won't have up-to-date status info. It's worth the 5 minutes.

**Q: Can I use multiple agents in one session?**
A: Yes. Start with the primary agent, then load others as needed.

**Q: How does this compare to just using an AI without the system?**
A: Without the system, every session starts from scratch. With it, every session builds on every previous session. The compounding knowledge makes a massive difference.

---

*Job Hunt Stack v2.0 | Walkthrough Guide*
*"Every session builds on the last. That's the whole point."*
