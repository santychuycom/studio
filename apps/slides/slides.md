---
theme: ./theme
title: CLI vs MCP. Where MCP Helps and Where the CLI Still Wins
info: |
  CLI vs MCP, context architecture, and preserving useful context longer.
drawings:
  persist: false
themeConfig:
  handle: '@santychuy_dev'
  logo: /branding/logo.png
---

---
class: lead
---

<MediaFigure src="/figures/IMG_2708.JPG" alt="Useful context chart" width="1100px" height="520px" />

---
class: lead
---

<div class="big">The game</div>

---
class: lead
---

<div class="big">The real game is not more tools. The real game is preserving useful context.</div>

---
class: lead
---

> *Cuando accidentalmente le dices “Hola” a Claude y consume el 4% de tu límite de sesión*

<MediaFigure src="/figures/CleanShot 2026-04-13 at 13.37.07.gif" alt="Useful context chart" width="760px" height="320px" />

---

<div class="big">Context is king.</div>

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/CleanShot 2026-04-10 at 16.16.09@2x.png" alt="Useful context chart" width="1100px" height="620px" />

---
class: lead
---

<div class="big">Smart zone / Dumb zone</div>

---

- Early in a session, the model is still sharp
- It can attend, retrieve, and compose well
- Then noise starts to accumulate
- That is how you drift from the smart zone into the dumb zone

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/Pasted image 20260410162644.png" alt="Smart zone diagram" width="900px" height="600px" />

---

- Sessions never start empty
- You already loaded system prompts
- You already loaded tools, rules, docs, references
- The room is partially occupied before the real task even starts

---
class: lead
---

<div class="big">It's the same with humans</div>

---
class: lead
---

<div class="big">LLMs behave similarly when their working context gets crowded.</div>

---

<div class="big">How to play the game?</div>

---

## Real Question

<div class="big">Is Not "CLI or MCP?"</div>

---
class: lead
---

<div class="big">Is: Which one preserves useful context longer, and when?</div>

---

<div class="profile-grid">
  <div class="profile-photo">
    <img src="/figures/me.png" alt="Portrait of Santiago Carrasco">
  </div>
  <div>
    <h2>Santiago Carrasco Campa</h2>
    <p><strong>SWE</strong> @ <strong>The &amp; Company</strong></p>
    <p class="links">
        <strong>X:</strong> <a href="https://x.com/santychuy_dev">@santychuy_dev</a>
        <br>
        <strong>Bluesky:</strong> <a href="https://bsky.app/profile/santychuy.bsky.social">@santychuy_dev</a>
        <br>
        <strong>GitHub:</strong> <a href="https://github.com/santychuy">@santychuy</a>
    </p>
  </div>
</div>

---

## CLI

- A CLI is an operator interface
- It is built for direct execution through the shell
- Agents are already very good at writing and using bash
- In known environments, it is often the shortest path from intent to action

---

## MCP

- MCP is a platform interface for AI systems
- It exposes tools, resources, and prompts in a structured way
- It helps with discovery, reuse, and interoperability
- It gets more compelling when the problem is integration, not just execution

---

## Why Both Exist

<div class="two-col">
  <div class="card">
    <h2>CLI</h2>
    <p>Solves <strong>control of software</strong>.</p>
    <ul>
      <li>Run commands</li>
      <li>Script workflows</li>
      <li>Operate inside a known environment</li>
    </ul>
  </div>
  <div class="card">
    <h2>MCP</h2>
    <p>Solves <strong>standardized connectivity</strong>.</p>
    <ul>
      <li>Expose capabilities cleanly</li>
      <li>Share them across hosts</li>
      <li>Add structure around context</li>
    </ul>
  </div>
</div>

---

## Real Difference

<div class="big">CLI = Execution</div>

<div class="big">MCP = Context architecture</div>

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/Pasted image 20260410163011.png" alt="Execution versus context architecture diagram" width="1000px" height="600px" />

---

## Trade-offs

- <strong>Context cost:</strong> CLI is lighter for direct tasks
- <strong>Discoverability:</strong> MCP has better defaults
- <strong>Trust boundaries:</strong> MCP can constrain capability exposure better
- <strong>Reuse:</strong> MCP scales better across hosts
- <strong>Setup cost:</strong> CLI is usually simpler to adopt

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/Pasted image 20260410163324.png" alt="Trade-offs comparison screenshot" width="1000px" height="600px" />

---
class: lead
---

<div class="big">Benchmark Test: Playwright</div>

- <strong>CLI:</strong> <code>playwright-cli</code>
- <strong>MCP:</strong> Playwright MCP tools

---
class: lead
---

<div class="big">Compare token burn, context exposure, tool calls, and workflow friction</div>

---

- Same workflow
- Same intent
- Being deterministic

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/CleanShot 2026-04-10 at 15.08.32@2x.png" alt="Benchmark screenshot one" width="1300px" height="600px" />

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/CleanShot 2026-04-10 at 15.09.13@2x.png" alt="Benchmark screenshot two" width="1600px" height="400px" />

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/CleanShot 2026-04-10 at 15.10.28@2x.png" alt="Benchmark screenshot three" width="1600px" height="200px" />

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/CleanShot 2026-04-10 at 15.10.57@2x.png" alt="Benchmark screenshot four" width="1100px" height="600px" />

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/CleanShot 2026-04-10 at 15.11.48@2x.png" alt="Benchmark screenshot five" width="1300px" height="600px" />

---

## Why CLI Won Here

- CLI shells out to one subprocess and returns one compact result
- MCP routes each browser action through the model as a tool call
- That means more intermediate state enters context
- More state means more token burn for a fixed scripted workflow

---

## My Position

- I **do not** think MCP is unnecessary
- I **do not** think CLI is always better

---
class: lead
---

<div class="big">But in known environments, I usually lean CLI</div>

---
class: lead
---

<div class="big">I reach for MCP when the integration problem is bigger than the execution problem</div>

---
layout: center
class: media-slide
---

<MediaFigure src="/figures/CleanShot 2026-04-10 at 14.53.31@2x.png" alt="Reference screenshot" width="1200px" height="400px" />

---

<div class="big">Closing</div>

---

<div class="final-line">If the model is the multiplier, your knowledge/experience is still the number that gets multiplied.</div>

---

<div class="final-line">Not delegate the thinking process</div>

---
class: lead
---

<div class="final-line">Be curious, experiment</div>
