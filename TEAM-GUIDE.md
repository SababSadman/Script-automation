# AurixScript Skill — Team Guide

> For all AurixLab team members who use Claude Code or Claude to write Reel and Ad scripts.
> Keep this guide in the same folder as the skill.

---

## What Is This Skill?

AurixScript is a custom AI skill that turns a pain point or topic into a complete, brand-aligned Reel or Ad script. It runs four distinct modes depending on what you need:

| Mode | What it does |
|---|---|
| **Standard** | One polished script assembled from the libraries |
| **Performance Analysis** | Analyzes past scripts first, salvages the strongest lines, writes a new script with a full breakdown and "Why This Works" section |
| **Variations** | Three complete script versions in one run — Emotional, Outcome/Result, and Negative/Risk angles |
| **Topic Planning** | No topic yet? Builds a scored, ranked list of 10–15 script ideas before writing anything |

---

## Before Anyone Uses It — Fill the Reference Files

**The skill is only as good as what's in the reference files.**

The `references/` folder is the brain of the skill. Keep all files updated.

| File | What to fill in | Who fills it | Priority |
|---|---|---|---|
| `references/brand-identity.md` | Numbered brand identity profiles — positioning, audience, tone, offers, visual style, content rules | Brand lead / account manager | **Critical — skill cannot run without at least one numbered profile** |
| `references/customer-profile.md` | Customer personas, emotional states, what they fear and want, Script Audience framing per brand | Brand lead / strategist | High |
| `references/creative-ads-guide.md` | Winning ad structures, hook patterns, body patterns, emotional angles, CTA patterns, what to avoid | Creative strategist | High |
| `references/visual-hook-library.md` | Actual visual hook ideas that work for this brand, with notes on what topics they suit | Content team / videographer | High |
| `references/voice-hook-library.md` | Real spoken opening lines that have worked, with hook type and context | Copywriter / Zarif | High |
| `references/cta-library.md` | CTA performance log — PROVEN templates, WEAK patterns, AVOID/NEVER REPEAT entries | Anyone with analytics access | High |
| `references/previous-scripts-analytics.md` | Past scripts + real analytics (views, retention, engagement, conversions) + learnings | Anyone with analytics access | Medium — skill supplements with research if empty, but real data always wins |
| `references/platform-guide.md` | Instagram, TikTok, Facebook hook windows, format constraints, tone rules, algorithm behavior, CTA patterns | Creative strategist | Medium — update when platform algorithms change |

**Rule: Never leave `brand-identity.md` empty.** Every other file can start thin — the skill supplements with research — but brand identity cannot be guessed.

---

## How to Install the Skill

### Option A — Claude Code (VSCode Extension or CLI)

This is the recommended method for the team.

**Step 1 — Copy the skill folder to your Claude skills directory**

On Windows:
```
C:\Users\[YourUsername]\.claude\skills\Aurixscript-skill\
```

The folder must look like this after copying:
```
Aurixscript-skill\
  SKILL.md
  TEAM-GUIDE.md
  feedback.md
  references\
    brand-identity.md
    customer-profile.md
    creative-ads-guide.md
    previous-scripts-analytics.md
    visual-hook-library.md
    voice-hook-library.md
    cta-library.md
    platform-guide.md
```

**Step 2 — Restart Claude Code** (close and reopen the VSCode extension or CLI)

**Step 3 — Verify it loaded**

In any Claude Code conversation, type `/` and you should see `sss-script` in the slash command list.

---

### Option B — Claude.ai Web (Projects)

Use this if a team member does not have Claude Code installed.

1. Go to [claude.ai](https://claude.ai) and open or create a **Project** for AurixLab
2. In the Project settings, paste the full contents of `SKILL.md` as the **System Prompt**
3. Upload all files from the `references/` folder into the Project's **knowledge base**
4. From that point, any conversation inside the Project will follow the AurixScript pipeline automatically — no slash command needed

---

## How to Use the Skill Day-to-Day

### Claude Code (slash command)

```
/sss-script [your topic or pain point here]
```

**Examples:**
```
/sss-script businesses wasting money on branded merch that looks cheap
/sss-script sports teams with no visual identity on the field
/sss-script event organizers scrambling for gear at the last minute
```

You can also invoke it with no argument and let Claude ask you:
```
/sss-script
```

---

## What Happens After You Invoke It

### Step 1 — Brand Identity
Claude reads `references/brand-identity.md` and shows the available numbered brand names. Pick a number. Claude loads only that profile.

### Step 2 — Library Update Check
Claude asks if you have anything to add to the libraries (new hooks, analytics, brand updates) before starting. Say **no** or **skip** to move on immediately.

### Step 3 — Three Setup Questions

Claude asks these three questions in order:

**Q1: Content type**
- **Ad Creative** — for paid promotion (Meta Ads, TikTok Ads, etc.)
- **Social Content** — for organic posts (feed, Reels, TikTok, Stories — no paid spend)

**Q2: Format**
- **Static** — single image, graphic, or carousel
- **Video** — Reel, short-form video, or video ad
- **Both** — two separate fully complete versions, one Static and one Video

**Q3: Platform**
- **Instagram** — applies Reels format rules, first-frame hook, saves/shares CTA logic
- **TikTok** — applies 1–2 second hook window, under-30s constraint, native tone
- **Facebook** — applies community tone, discussion CTA, no external link rule

### Step 4 — Script Mode
Claude asks which mode:

1. **Standard** — one script, fast, fully assembled from the libraries
2. **Performance Analysis** — analyzes past scripts first, then writes with full breakdown
3. **Variations** — three angles in one run (Emotional / Outcome / Negative)
4. **Topic Planning** — build a scored topic list first, then pick one to script

---

## The Four Script Modes Explained

### Mode 1 — Standard
The default. Claude selects the best visual hook, voice hook, body structure, and CTA from the libraries for your topic, assembles a full script, humanizes it, and delivers a Script Scorecard at the end.

**Output:**
- Full labeled script (`[VISUAL HOOK]`, `[VOICE HOOK]`, `[BODY]`, `[B-ROLL SUGGESTIONS]` for video, `[CTA]`)
- Script Scorecard (Hook Strength, Body Clarity, CTA Sharpness, Brand Alignment, Predicted Tier)

---

### Mode 2 — Performance Analysis
Best when you want to understand what's working before writing. Claude analyzes all saved scripts and analytics, surfaces the strongest salvageable lines, then writes a new script with a full performance breakdown.

**Output (in order):**
1. **Performance Insight Summary** — what's working, what's failing, and why
2. **Salvaged Lines** — labeled REUSE / REWRITE / ADAPT
3. **Full script** with dual hook options (Main + Alternative)
4. **Why This Script Works** — hook rationale, body structure, B-roll logic, CTA reasoning, one flag for review

---

### Mode 3 — Variations
Best when you want to test multiple angles before committing to one. Claude writes three complete, humanized scripts in one run — same topic, same libraries, different persuasion frame.

**Three angles:**
- **Variation 1 — Emotional:** leads with the feeling the customer wants (relief, confidence, pride)
- **Variation 2 — Outcome/Result:** leads with what measurably changes after working with the brand
- **Variation 3 — Negative/Risk:** leads with what the customer loses by not acting

**Output:** Three full scripts, each with a Scorecard, plus a one-line Recommendation.

---

### Mode 4 — Topic Planning
Best when you don't have a topic yet or want to plan ahead. Claude mines the reference files and (optionally) competitor research to build a scored, ranked topic list.

**Output (in order):**
1. **Pillar Map** — 3–5 content pillars for the brand (confirm or adjust before continuing)
2. **Pain Point Sourcing** — 10–15 raw topic ideas with source notes
3. **Buyer Stage Tags** — each topic tagged Awareness / Consideration / Decision, with recommended content type
4. **Ranked Topic Table** — scored by Customer Impact (40%), Brand/Offer Fit (30%), Hook Potential (20%), Library Support (10%)
5. **Pick and Write** — choose a number from the list, then select writing mode 1, 2, or 3

---

## Reading the Script Output

Every video script uses this structure:

```
[VISUAL HOOK]
What the camera shows in the first 1–3 seconds.
No words spoken — this is pure visual direction for the camera operator.

[VOICE HOOK]
The first spoken line. Delivered within the platform's hook window.
Creates curiosity, tension, or immediate relevance.

[BODY]
The main content. Addresses the pain point directly.
Delivers value, tells a story, or demonstrates the solution.
Connects back to the brand's offer naturally.

[B-ROLL SUGGESTIONS]  ← Video scripts only
Specific visual ideas that reinforce or replace spoken lines.
3–5 suggestions. Pass these to the videographer alongside the script.

[CTA]
The closing line. One clear platform-appropriate action for the viewer.
```

Static scripts use: `[HEADLINE]`, `[VISUAL CONCEPT]`, `[BODY COPY]`, `[CTA]`.

Performance Analysis Mode also outputs a dual hook: `[VOICE HOOK — MAIN]` and `[VOICE HOOK — ALTERNATIVE]`.

---

## Script Scorecard

Every Standard or Variations script ends with a Scorecard:

```
SCRIPT SCORECARD
─────────────────────────────────────────
Hook Strength        [ /10 ]
Body Clarity         [ /10 ]
CTA Sharpness        [ /10 ]
Brand Alignment      [ Pass / Flag ]
Predicted Tier       [ Top / Mid / Risk ]
─────────────────────────────────────────
Notes: [weakest element + what reviewer should check]
```

**Predicted Tier** is based on patterns in `references/previous-scripts-analytics.md`:
- **Top** — matches proven high-performing patterns
- **Mid** — solid structure but untested angle
- **Risk** — uses a pattern flagged as weak or hook type is untested

---

## Human Review Is Always the Final Step

Claude's output is a **draft**. Review it before filming or publishing.

- [ ] Brand tone feels right — does this sound like us?
- [ ] The offer in the CTA is current and accurate
- [ ] No content rules from `brand-identity.md` were violated
- [ ] Script fits the target length for the selected platform
- [ ] Visual hook is filmable with your current setup
- [ ] Voice hook feels natural when said out loud — read it aloud before approving
- [ ] B-roll suggestions are achievable with available footage or shoot plan
- [ ] Platform rules are respected (TikTok: under 30s; Instagram: first-frame quality; Facebook: no external link CTA on organic)
- [ ] If Claude noted "supplemented with research" — verify the researched content fits the brand

---

## Keeping the Reference Files Updated

The skill improves only if the team keeps the reference files current.

| Situation | File to update |
|---|---|
| New visual opening stopped the scroll | `references/visual-hook-library.md` |
| A spoken hook line performed well | `references/voice-hook-library.md` |
| Analytics back on a script | `references/previous-scripts-analytics.md` |
| New ad structure or creative pattern working | `references/creative-ads-guide.md` |
| CTA performed well or bombed | `references/cta-library.md` |
| Brand launched new offer, changed tone, or updated audience | `references/brand-identity.md` |
| New customer segment or pain point shift identified | `references/customer-profile.md` |
| Platform algorithm changed | `references/platform-guide.md` |

### How to ask Claude to update a file

```
"Add this visual hook to the visual hook library: [describe it]"
"Update the analytics file with last month's script — here's the data: [paste it]"
"The brand is now targeting [new segment] — update brand identity."
"Mark this CTA as PROVEN in the CTA library — it converted at 4%"
```

Claude writes the update to the correct file and confirms what was added.

### Zarif's Hook Updates

`references/voice-hook-library.md` has a dedicated section called **Zarif's Rotating Hook Updates**. Zarif updates this every two weeks with new hooks based on current trends and platform performance. Use the format already in the file with the date added.

---

## Troubleshooting

### "Claude asked me to fill in the brand identity file before continuing"
`references/brand-identity.md` is empty or has no usable numbered profile. Add or update a numbered brand identity before running the skill again. This is the one file the skill cannot work around.

### "Claude said it supplemented with web research"
One or more reference files were too thin for the topic. Claude used web research to fill the gap. Expected behavior — check the note at the end of the script to see what was researched and verify it fits the brand.

### "The script doesn't sound like our brand"
Most common cause: incomplete or vague profile in `brand-identity.md`. Add more specific entries for tone of voice, phrases the brand uses, and phrases the brand never uses. The more specific the profile, the more on-brand the output.

### "The Scorecard says Risk — should I still use it?"
A Risk score means Claude flagged an untested angle or a pattern that underperformed historically. Read the Notes line — it tells you exactly what to check. The script can still be strong; Risk just means the human reviewer should pay extra attention before approving.

### "The skill doesn't appear in my slash command list"
- Confirm the folder is at `C:\Users\[YourUsername]\.claude\skills\Aurixscript-skill\`
- Confirm `SKILL.md` is directly inside that folder (not in a subfolder)
- Restart Claude Code fully after copying the folder

### "I'm using Claude.ai web and the skill isn't following the pipeline"
- Confirm the full contents of `SKILL.md` are pasted as the Project's System Prompt
- Confirm all reference files from the `references/` folder are uploaded to the Project's knowledge base
- If the knowledge base is empty, Claude has no brand or creative context to work from

---

## Quick Reference Card

| Task | What to do |
|---|---|
| Write one script fast | `/sss-script [topic]` → choose **Standard** |
| Analyze past scripts + write new one | `/sss-script` → choose **Performance Analysis** |
| Get three angle options in one run | `/sss-script` → choose **Variations** |
| Don't have a topic yet | `/sss-script` → choose **Topic Planning** |
| Update a reference file | Ask Claude in conversation: "Add X to [file name]" |
| Brand info changed | Edit the numbered profile in `references/brand-identity.md` |
| New analytics available | Paste into `references/previous-scripts-analytics.md` |
| New CTA result | Ask Claude to log it in `references/cta-library.md` as PROVEN or WEAK |

---

## File Map

```
Aurixscript-skill\
  SKILL.md                          — Skill definition (pipeline, all modes, all rules)
  TEAM-GUIDE.md                     — This guide
  feedback.md                       — Auto-logged script feedback from team sessions
  content-strategy.md               — Standalone content strategy skill (separate from script pipeline)
  references\
    brand-identity.md               — FILL THIS FIRST — numbered brand profiles
    customer-profile.md             — Customer personas and Script Audience framing
    creative-ads-guide.md           — Ad structures, hook patterns, creative strategies
    previous-scripts-analytics.md  — Past scripts + performance data + learnings
    visual-hook-library.md          — Opening visual ideas
    voice-hook-library.md           — Opening spoken lines (includes Zarif's rotating updates)
    cta-library.md                  — CTA log: PROVEN / WEAK / AVOID / NEVER REPEAT
    platform-guide.md               — Instagram / TikTok / Facebook rules and algorithm behavior
```

---

> Last updated: May 2026
> Maintained by: AurixLab team
