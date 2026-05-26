# Instagram Video Transcripts — AI Agents, Claude Code, Agentic Workflows
## 2026-05-26

---

## Transcription Status

**APIFY BLOCKED — No transcripts available for this run.**

All Apify Actor calls returned `Unexpected error: Host not in allowlist`. This is a network policy restriction in the current execution environment — outbound calls to `api.apify.com` are blocked.

**Impact on scripts:** All 10 scripts in `2026-05-26_scripts.md` used caption-derived structural fallback per the skill's failure handling rules. The source structure breakdown in each script notes this explicitly. The structural patterns (hook framing device, body delivery sequence, close mechanism) were derived from:

1. Known creator behavior patterns from `references/tracked-accounts.md`
2. Documented post performance signals (e.g., @sabrina_ramonov's 17K+ comment post)
3. Established content formats for each creator (e.g., @nocode.joshua's recap-and-distill format, @nick_saraev's build-along sequencing)

**To get real transcripts on the next run:** Ensure the execution environment has outbound access to `api.apify.com`. The `transcribe_post.py` tool caches results at `.tmp/instagram-trends/transcripts/<shortcode>.json` — once a video is transcribed, re-running is free.

---

## Expected transcript format (for reference)

When Apify is available, each entry in this file would follow this structure:

```
### Transcript: @handle — [shortcode]

**URL:** https://www.instagram.com/reel/[shortcode]/
**Handle:** @handle
**Caption:** [post caption text]
**Duration:** [seconds]
**Likes:** [count]  |  **Comments:** [count]  |  **Views:** [count]
**Timestamp:** [ISO date]
**Language:** en (probability: 0.99)

**Full transcript:**
[full spoken text]

**Timestamped segments:**

| Start | End | Text |
| --- | --- | --- |
| 0.00 | 2.80 | [Hook line spoken text] |
| 2.80 | 5.60 | [Hold line spoken text] |
| ... | ... | ... |

**Structural breakdown:**
- Hook (0:00–0:03): [Framing device used — claim / question / contrast / urgency]
- Hold line (0:03–0:06): [How tension or curiosity is extended]
- Body (0:06–0:45): [Delivery sequence — named tools, ordered beats, examples]
- Close (0:45–0:55): [Landing line and CTA mechanism]
```

---

## Source video references (no transcripts available)

The following posts were identified as source material for scripts 1–10. When Apify becomes available, run `python tools/instagram/transcribe_post.py <url>` for each to capture real transcripts.

| Script | Source account | Post reference | Priority |
| --- | --- | --- | --- |
| Script 1 | @sabrina_ramonov | Claude Cowork marketing department post (17K+ comments) | HIGH — highest engagement signal in tracked set |
| Script 2 | @nick_saraev | n8n + Claude Code agent stack build-along reel | HIGH — best revenue-framing example |
| Script 3 | @advicewithjean | Sub-agents and persistent memory reel | HIGH — sub-agent architecture angle is rising |
| Script 4 | @itsmariahbrunner | Claude Skills comment-to-DM funnel demo | HIGH — comment-trigger mechanics benchmark |
| Script 5 | @nocode.joshua | Claude Cowork 15 free plugins recap | MEDIUM — recap format benchmark |
| Script 6 | @nocode.joshua | ChatGPT vs Claude for content workflows | MEDIUM — comparison framing benchmark |
| Script 7 | @itsmariahbrunner | Claude Cowork workflow demo post | HIGH — operator mindset framing |
| Script 8 | @advicewithjean | Claude Code morning routine reel | MEDIUM — lifestyle framing benchmark |
| Script 9 | @treysmith | AI agent grew IG to 60K in a week | MEDIUM — viral claim + honest breakdown |
| Script 10 | @theaiagents | Claude Skills for creators list post | LOW — list format, moderate engagement |

---

## Cache directory

When transcripts are available, they are stored at:

```
.tmp/instagram-trends/transcripts/
├── <shortcode_1>.json
├── <shortcode_2>.json
└── ...
```

The cache is checked before any Apify call — re-running `transcribe_post.py` on a previously transcribed post returns the cached result instantly and uses no Apify credits.
