<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>SOEN 357 Mini-Project — Health Companion App</title>
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet" />
  <style>
    :root {
      --ink: #0f0f0f;
      --ink-light: #444;
      --ink-muted: #888;
      --paper: #faf9f7;
      --paper-card: #f3f1ed;
      --accent: #004B87;
      --accent-warm: #8a3a00;
      --green: #006837;
      --red: #B30000;
      --rule: #d8d4cc;
      --max: 820px;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--paper);
      color: var(--ink);
      font-size: 17px;
      line-height: 1.75;
      -webkit-font-smoothing: antialiased;
    }

    /* ─── HEADER ─── */
    header {
      border-bottom: 2px solid var(--ink);
      padding: 3.5rem 2rem 2.5rem;
      max-width: var(--max);
      margin: 0 auto;
    }
    .eyebrow {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.72rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--ink-muted);
      margin-bottom: 1rem;
    }
    header h1 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(2.2rem, 6vw, 3.6rem);
      line-height: 1.1;
      letter-spacing: -0.02em;
      margin-bottom: 1.2rem;
    }
    header h1 em {
      font-style: italic;
      color: var(--accent);
    }
    .meta {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
      font-size: 0.82rem;
      color: var(--ink-muted);
      font-family: 'JetBrains Mono', monospace;
    }
    .meta span b { color: var(--ink); }

    /* ─── MAIN LAYOUT ─── */
    main {
      max-width: var(--max);
      margin: 0 auto;
      padding: 0 2rem 6rem;
    }

    /* ─── TABLE OF CONTENTS ─── */
    .toc {
      margin: 3rem 0;
      padding: 2rem;
      background: var(--paper-card);
      border-left: 3px solid var(--accent);
    }
    .toc h2 {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.72rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--ink-muted);
      margin-bottom: 1rem;
    }
    .toc ol {
      list-style: decimal;
      padding-left: 1.4rem;
      display: grid;
      gap: 0.35rem;
    }
    .toc a {
      color: var(--accent);
      text-decoration: none;
      font-size: 0.92rem;
      font-weight: 500;
    }
    .toc a:hover { text-decoration: underline; }

    /* ─── SECTIONS ─── */
    section {
      margin-top: 5rem;
      padding-top: 0.5rem;
      border-top: 1px solid var(--rule);
    }
    section:first-of-type { border-top: none; }

    h2.section-title {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(1.7rem, 4vw, 2.4rem);
      letter-spacing: -0.02em;
      margin-bottom: 0.4rem;
      line-height: 1.15;
    }
    .section-num {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.7rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--ink-muted);
      display: block;
      margin-bottom: 0.5rem;
    }

    h3.subsection {
      font-family: 'DM Serif Display', serif;
      font-size: 1.35rem;
      margin: 2.5rem 0 0.7rem;
      color: var(--ink);
    }
    h4.subsubsection {
      font-size: 0.95rem;
      font-weight: 600;
      letter-spacing: 0.04em;
      text-transform: uppercase;
      color: var(--ink-muted);
      margin: 2rem 0 0.6rem;
    }

    p { margin-bottom: 1.1rem; color: var(--ink-light); }
    p:last-child { margin-bottom: 0; }

    /* ─── PULL QUOTE ─── */
    blockquote {
      border-left: 3px solid var(--accent);
      margin: 2rem 0;
      padding: 0.8rem 1.5rem;
      background: var(--paper-card);
      font-family: 'DM Serif Display', serif;
      font-style: italic;
      font-size: 1.05rem;
      color: var(--ink);
    }
    blockquote cite {
      display: block;
      margin-top: 0.6rem;
      font-size: 0.78rem;
      font-style: normal;
      font-family: 'JetBrains Mono', monospace;
      color: var(--ink-muted);
    }

    /* ─── INTERVIEW QUOTES ─── */
    .interview-block {
      display: grid;
      gap: 1rem;
      margin: 1.5rem 0;
    }
    .interview-q {
      background: var(--paper-card);
      border-radius: 2px;
      padding: 1rem 1.2rem;
      font-size: 0.88rem;
      border-left: 2px solid var(--rule);
      color: var(--ink);
      font-style: italic;
    }
    .interview-q b {
      display: block;
      font-style: normal;
      font-size: 0.72rem;
      font-family: 'JetBrains Mono', monospace;
      letter-spacing: 0.1em;
      color: var(--accent);
      margin-bottom: 0.3rem;
    }

    /* ─── PERSONA CARDS ─── */
    .persona-card {
      display: grid;
      grid-template-columns: 1fr;
      gap: 1.5rem;
      border: 1px solid var(--rule);
      padding: 2rem;
      margin: 2rem 0;
      background: var(--paper-card);
    }
    .persona-card img {
      width: 100%;
      max-height: 340px;
      object-fit: cover;
      border: 1px solid var(--rule);
    }
    .persona-card h4 {
      font-family: 'DM Serif Display', serif;
      font-size: 1.4rem;
      margin-bottom: 0.3rem;
    }
    .persona-tag {
      display: inline-block;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.68rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      padding: 0.2rem 0.6rem;
      border: 1px solid var(--accent);
      color: var(--accent);
      margin-bottom: 0.8rem;
    }

    /* ─── INSIGHT CARDS ─── */
    .insight-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 1px;
      border: 1px solid var(--rule);
      margin: 2rem 0;
    }
    .insight-item {
      padding: 1.4rem;
      background: var(--paper);
    }
    .insight-item:nth-child(even) { background: var(--paper-card); }
    .insight-item strong {
      display: block;
      font-size: 0.8rem;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      margin-bottom: 0.4rem;
      color: var(--ink);
    }
    .insight-item p { font-size: 0.88rem; margin: 0; }

    /* ─── IMAGES ─── */
    figure {
      margin: 2.5rem 0;
    }
    figure img {
      width: 100%;
      border: 1px solid var(--rule);
      display: block;
    }
    figcaption {
      margin-top: 0.5rem;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.7rem;
      letter-spacing: 0.08em;
      color: var(--ink-muted);
      text-align: center;
    }
    .img-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
      margin: 2rem 0;
    }
    .img-grid figure { margin: 0; }
    .img-grid-3 {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      gap: 1rem;
      margin: 2rem 0;
    }
    .img-grid-3 figure { margin: 0; }

    /* ─── COLOR TABLE ─── */
    .color-table {
      width: 100%;
      border-collapse: collapse;
      margin: 2rem 0;
      font-size: 0.85rem;
    }
    .color-table th {
      background: var(--ink);
      color: #fff;
      padding: 0.6rem 0.8rem;
      text-align: left;
      font-weight: 500;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.72rem;
      letter-spacing: 0.08em;
    }
    .color-table td {
      padding: 0.55rem 0.8rem;
      border-bottom: 1px solid var(--rule);
      color: var(--ink-light);
      vertical-align: middle;
    }
    .color-table tr:last-child td { border-bottom: none; }
    .color-table tr:hover td { background: var(--paper-card); }
    .color-swatch {
      display: inline-block;
      width: 18px;
      height: 18px;
      border-radius: 2px;
      border: 1px solid var(--rule);
      vertical-align: middle;
      margin-right: 6px;
    }

    /* ─── FEATURE LIST ─── */
    .feature-list {
      list-style: none;
      margin: 1.2rem 0;
      display: grid;
      gap: 0.7rem;
    }
    .feature-list li {
      padding: 0.8rem 1rem 0.8rem 2.2rem;
      position: relative;
      background: var(--paper-card);
      font-size: 0.93rem;
      color: var(--ink-light);
      border-left: 2px solid var(--paper-card);
      transition: border-color 0.2s;
    }
    .feature-list li:hover { border-left-color: var(--accent); }
    .feature-list li::before {
      content: '→';
      position: absolute;
      left: 0.7rem;
      color: var(--accent);
      font-weight: 700;
    }

    /* ─── PLACEHOLDER ─── */
    .placeholder {
      background: repeating-linear-gradient(
        45deg,
        var(--paper-card),
        var(--paper-card) 10px,
        var(--paper) 10px,
        var(--paper) 20px
      );
      border: 1.5px dashed var(--rule);
      padding: 3rem 2rem;
      text-align: center;
      color: var(--ink-muted);
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.78rem;
      letter-spacing: 0.12em;
      margin: 2rem 0;
    }
    .placeholder strong { display: block; margin-bottom: 0.3rem; color: var(--ink); }

    /* ─── Q GROUPS ─── */
    .q-group {
      margin: 1.5rem 0;
      padding: 1.2rem 1.5rem;
      background: var(--paper-card);
    }
    .q-group h5 {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.7rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 0.8rem;
    }
    .q-group ul {
      list-style: none;
      display: grid;
      gap: 0.4rem;
    }
    .q-group li {
      padding-left: 1.2rem;
      position: relative;
      font-size: 0.9rem;
      color: var(--ink-light);
      font-style: italic;
    }
    .q-group li::before {
      content: '"';
      position: absolute;
      left: 0;
      color: var(--ink-muted);
      font-style: normal;
    }

    /* ─── FOOTER ─── */
    footer {
      border-top: 2px solid var(--ink);
      max-width: var(--max);
      margin: 0 auto;
      padding: 2rem;
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 0.5rem;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.72rem;
      color: var(--ink-muted);
    }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 600px) {
      .img-grid, .img-grid-3 { grid-template-columns: 1fr; }
      .insight-grid { grid-template-columns: 1fr; }
    }

    /* ─── SCROLL REVEAL ─── */
    .reveal {
      opacity: 0;
      transform: translateY(18px);
      transition: opacity 0.55s ease, transform 0.55s ease;
    }
    .reveal.visible {
      opacity: 1;
      transform: none;
    }
  </style>
</head>
<body>

  <header>
    <p class="eyebrow">SOEN 357 — Mini-Project &nbsp;·&nbsp; Section V &nbsp;·&nbsp; February 2026</p>
    <h1>Designing a <em>Health Companion</em> App<br>Through User-Centred Research</h1>
    <div class="meta">
      <span><b>Author</b> — Massimo Paolini</span>
      <span><b>ID</b> — 40280323</span>
      <span><b>Course</b> — SOEN 357</span>
    </div>
  </header>

  <main>

    <nav class="toc reveal">
      <h2>Contents</h2>
      <ol>
        <li><a href="#research">User Research &amp; Persona Creation</a></li>
        <li><a href="#journey">User Journey Mapping</a></li>
        <li><a href="#storyboard">Storyboard</a></li>
        <li><a href="#design">Sketching, Wireframing &amp; Prototype</a></li>
        <li><a href="#usability">Usability Testing</a></li>
        <li><a href="#reflection">Reflection</a></li>
      </ol>
    </nav>

    <!-- ═══════════════════════════════════════════════
         SECTION 1 — USER RESEARCH
    ════════════════════════════════════════════════ -->
    <section id="research" class="reveal">
      <span class="section-num">01 / 06</span>
      <h2 class="section-title">User Research &amp;<br>Persona Creation</h2>

      <h3 class="subsection">Possible Methods</h3>
      <p>Understanding user needs and behaviors requires the use of multiple research methods, each with its own strengths and constraints.</p>

      <div class="insight-grid">
        <div class="insight-item">
          <strong>Surveys</strong>
          <p>Common in-app feedback loops. Scalable but shallow — responses are often surface-level and lack the depth needed to uncover real pain points.</p>
        </div>
        <div class="insight-item">
          <strong>Interviews</strong>
          <p>One-on-one sessions with representative users. Rich, qualitative data — the gold standard for uncovering motivations, frustrations, and mental models.</p>
        </div>
        <div class="insight-item">
          <strong>Secondary Research</strong>
          <p>Analysis of existing forums, reviews, and competitor products. Efficient and broad — no participant recruitment needed, but insights may be indirect.</p>
        </div>
      </div>

      <h3 class="subsection">Interviews</h3>
      <p>Six real people, each managing some form of chronic condition, were interviewed. Their ages spanned three distinct generations — Gen Z, Millennial/Gen X, and Boomer — intentionally chosen to surface how health-tech needs differ across life stages.</p>
      <p>Questions were organised into four thematic groups:</p>

      <div class="q-group">
        <h5>Group 1 — Demographics &amp; Context</h5>
        <ul>
          <li>Can you describe a typical day when you have to manage your health or medications?</li>
          <li>What are the three apps you use most on your phone? What do you like about them?</li>
          <li>How comfortable do you feel using your phone for important tasks compared to pen and paper?</li>
        </ul>
      </div>

      <div class="q-group">
        <h5>Group 2 — Pain Points &amp; Challenges</h5>
        <ul>
          <li>Have you ever forgotten a dose or an appointment? What happened, and how did you feel?</li>
          <li>When you need to talk to your doctor, what is the most annoying part of that process?</li>
          <li>Where do you currently keep track of your health info? (e.g., physical folder, notes app, calendar)</li>
        </ul>
      </div>

      <div class="q-group">
        <h5>Group 3 — Needs &amp; Feature Validation</h5>
        <ul>
          <li>If an app sent you a notification to take medication, what information would you need to see immediately?</li>
          <li>What information do you want to have ready right before you walk into a doctor's office?</li>
          <li>If you were feeling unwell, how would you expect an app like this to help you in that moment?</li>
        </ul>
      </div>

      <div class="q-group">
        <h5>Group 4 — Generation-Specific</h5>
        <ul>
          <li>Gen Z: How would you want this to fit into your social/work life without being intrusive?</li>
          <li>Millennials/Gen X: How can this app save you time rather than add a chore?</li>
          <li>Gen X/Boomers: What makes a screen hard for you to read or interact with? How do you feel about sharing health data digitally?</li>
        </ul>
      </div>

      <h4 class="subsubsection">Key Interview Responses</h4>

      <p style="margin-bottom:0.5rem; font-size:0.85rem; color:var(--ink-muted);">Group 1 — Demographics &amp; Context</p>
      <div class="interview-block">
        <div class="interview-q">
          <b>Participant, Age 23</b>
          "A typical day is a series of 'remind me later' taps. I use Instagram and Notion the most because they are visual and flexible… I feel 100% comfortable with my phone for tasks…"
        </div>
        <div class="interview-q">
          <b>Participant, Age 45</b>
          "I check my own vitals… text my dad to see if he took his medications. I mainly use Outlook and Teams for work… I use my phone for 'important' things because of the sync. I need everything connected."
        </div>
        <div class="interview-q">
          <b>Participant, Age 75</b>
          "My health management is all physical reminders: the pillbox in the kitchen, the calendar on the desk… I use WhatsApp for family, but for health, I prefer my pen and paper…"
        </div>
      </div>

      <p style="margin-bottom:0.5rem; font-size:0.85rem; color:var(--ink-muted);">Group 2 — Pain Points &amp; Challenges</p>
      <div class="interview-block">
        <div class="interview-q">
          <b>Participant, Age 17</b>
          "The most annoying part of seeing a doctor is having to communicate with them constantly by phone. Oftentimes I have to wait for a receptionist to call me back during class…"
        </div>
        <div class="interview-q">
          <b>Participant, Age 45</b>
          "The 'Mental Load' is the killer. I'm managing two sets of appointments. The most annoying part is the lack of transparency… I have to call the doctor just to find out if a prescription refill is ready."
        </div>
        <div class="interview-q">
          <b>Participant, Age 73</b>
          "I've forgotten appointments because I wrote them on a scrap of paper that got thrown away. It makes me feel unreliable… When I talk to the doctor, I feel rushed… I can't remember everything."
        </div>
      </div>

      <p style="margin-bottom:0.5rem; font-size:0.85rem; color:var(--ink-muted);">Group 3 — Needs &amp; Feature Validation</p>
      <div class="interview-block">
        <div class="interview-q">
          <b>Participant, Age 22</b>
          "If I'm feeling unwell, I don't want to type a journal entry. I just want icons for 'Nausea' or 'Fatigue.' On my lock screen, I need the notification to be high-context."
        </div>
        <div class="interview-q">
          <b>Participant, Age 45</b>
          "A report that summarizes trends of my health would be perfect… I don't want a simple list; I want to show them a graph that says, 'Blood pressure spiked on Tuesdays.'"
        </div>
        <div class="interview-q">
          <b>Participant, Age 75</b>
          "I need to see a photo of the medication on the screen. Names like 'Lisinopril' mean nothing to me, but I know the 'round pink pill.' If I'm unwell, I expect the app to have a clear emergency contact button."
        </div>
      </div>

      <p style="margin-bottom:0.5rem; font-size:0.85rem; color:var(--ink-muted);">Group 4 — Generation-Specific</p>
      <div class="interview-block">
        <div class="interview-q">
          <b>Gen Z (17–23)</b>
          "It needs to look like a 'lifestyle' app, not a 'sick person' app… If my phone is on the table during a meeting or date, the notification shouldn't broadcast something embarrassing…"
        </div>
        <div class="interview-q">
          <b>Millennials / Gen X (45)</b>
          "Save me time by automating the boring stuff. If the app can track my pharmacy refills and tell me before I run out, that's one less thing on my mental to-do list…"
        </div>
        <div class="interview-q">
          <b>Boomers (70+)</b>
          "Stop using thin, light-grey fonts on white backgrounds. I need high contrast and large tap targets… I'm fine sharing data with my doctor, but I don't want it 'shared' with advertisers."
        </div>
      </div>

      <h3 class="subsection">Secondary Research</h3>
      <p>Reddit served as the primary secondary source, drawing from subreddits like <code>r/ChronicIllness</code>, <code>r/adhdwomen</code>, and <code>r/UXDesign</code>. Five key themes emerged:</p>

      <div class="insight-grid">
        <div class="insight-item">
          <strong>Subscription Fatigue</strong>
          <p>Users resent premium paywalls on critical features like refill reminders. A free, core-feature-complete experience is table stakes.</p>
        </div>
        <div class="insight-item">
          <strong>Mental Load of Scheduling</strong>
          <p>Asynchronous scheduling is a critical unmet need — phone-only booking is a barrier, especially for those with ADHD or chronic fatigue.</p>
        </div>
        <div class="insight-item">
          <strong>Notification Desensitization</strong>
          <p>Standard reminders get ignored. Snooze functionality and smarter, context-aware notifications are needed.</p>
        </div>
        <div class="insight-item">
          <strong>Privacy &amp; The Paper Backup</strong>
          <p>A significant segment — especially seniors and privacy-conscious Gen Z — distrust cloud-syncing for medical data. Offline/printable options matter.</p>
        </div>
        <div class="insight-item">
          <strong>The Caregiver Persona</strong>
          <p>Many users manage not just their own health, but a relative's. Multi-profile support and shared access are essential features.</p>
        </div>
      </div>

      <h3 class="subsection">User Personas</h3>
      <p>Three primary personas were developed to translate collected research into actionable design decisions.</p>

      <div class="persona-card reveal">
        <div>
          <span class="persona-tag">Gen Z</span>
          <h4>Jennifer Smith</h4>
          <p>Jennifer represents the Gen Z demographic — phone-native, visually driven, and deeply social. She relies entirely on her phone for management but hates making actual phone calls. Overwhelmed by notifications, she needs a health app that looks and feels like a lifestyle app — not a medical device. Discretion, speed, and aesthetic coherence are her top priorities.</p>
        </div>
        <figure>
          <img src="image1.png" alt="Jennifer Smith Persona Card" />
          <figcaption>Fig. 1 — Jennifer Smith persona</figcaption>
        </figure>
      </div>

      <div class="persona-card reveal">
        <div>
          <span class="persona-tag">Millennial / Gen X</span>
          <h4>David Lee</h4>
          <p>David is at the height of his career and family life, managing appointments and medications for both himself and aging parents. He wants tools that reduce mental load, not add to it. Automation, smart reminders about refills, and synced calendars are critical. He needs the app to work quietly in the background and surface the right information at the right time.</p>
        </div>
        <figure>
          <img src="image2.png" alt="David Lee Persona Card" />
          <figcaption>Fig. 2 — David Lee persona</figcaption>
        </figure>
      </div>

      <div class="persona-card reveal">
        <div>
          <span class="persona-tag">Boomer</span>
          <h4>Elena Pucci</h4>
          <p>Elena represents the most medically dependent demographic. Less experienced with mobile UX, she needs an interface that is immediately intuitive with no assumed prior knowledge. High-contrast text, large tap targets, visual medication identification (photos of pills), and a prominent emergency contact button are non-negotiable. Printable summaries are also critical for her doctor visits.</p>
        </div>
        <figure>
          <img src="image3.png" alt="Elena Pucci Persona Card" />
          <figcaption>Fig. 3 — Elena Pucci persona</figcaption>
        </figure>
      </div>
    </section>

    <!-- ═══════════════════════════════════════════════
         SECTION 2 — USER JOURNEY MAPPING
    ════════════════════════════════════════════════ -->
    <section id="journey" class="reveal">
      <span class="section-num">02 / 06</span>
      <h2 class="section-title">User Journey Mapping</h2>
      <p>To connect user feedback into actionable UI/UX design decisions, each persona was mapped through a user journey — tracing their emotional state, actions, touchpoints, and pain points as they interact with the health management process end-to-end.</p>

      <div class="img-grid">
        <figure>
          <img src="image4.png" alt="User Journey Map 1" />
          <figcaption>Fig. 4 — Journey map (Persona 1)</figcaption>
        </figure>
        <figure>
          <img src="image5.png" alt="User Journey Map 2" />
          <figcaption>Fig. 5 — Journey map (Persona 2)</figcaption>
        </figure>
      </div>

      <blockquote>
        User journey maps are not just documentation — they are empathy tools that force the designer to feel the friction their user experiences at every step.
      </blockquote>
    </section>

    <!-- ═══════════════════════════════════════════════
         SECTION 3 — STORYBOARD
    ════════════════════════════════════════════════ -->
    <section id="storyboard" class="reveal">
      <span class="section-num">03 / 06</span>
      <h2 class="section-title">Storyboard</h2>
      <p>The storyboard illustrates a realistic scenario of how a target user would interact with the app in context — grounding the design in a real-world narrative rather than abstract UI states.</p>

      <figure>
        <img src="image6.png" alt="Storyboard" />
        <figcaption>Fig. 6 — Storyboard scenario</figcaption>
      </figure>
    </section>

    <!-- ═══════════════════════════════════════════════
         SECTION 4 — SKETCHING, WIREFRAMING & PROTOTYPE
    ════════════════════════════════════════════════ -->
    <section id="design" class="reveal">
      <span class="section-num">04 / 06</span>
      <h2 class="section-title">Sketching, Wireframing<br>&amp; Prototype Design</h2>

      <h3 class="subsection">Sketching</h3>
      <p>Rough sketches were drawn first to rapidly explore layout ideas. Low fidelity by design — the goal here is breadth, not polish. They give immediate visual feedback and establish the structural logic of the app before any digital tool is opened.</p>

      <div class="img-grid-3">
        <figure>
          <img src="image7.jpeg" alt="Sketch 1" />
          <figcaption>Fig. 7 — Sketch</figcaption>
        </figure>
        <figure>
          <img src="image8.jpeg" alt="Sketch 2" />
          <figcaption>Fig. 8 — Sketch</figcaption>
        </figure>
        <figure>
          <img src="image9.jpeg" alt="Sketch 3" />
          <figcaption>Fig. 9 — Sketch</figcaption>
        </figure>
      </div>

      <h3 class="subsection">Wireframes</h3>
      <p>Building on the sketches, wireframes flesh out a more complete picture of the app's flow and interface structure. The focus here is UX and functionality — no colours, no branding — just information hierarchy, interaction patterns, and navigation logic.</p>

      <figure>
        <img src="image10.png" alt="Wireframe overview" />
        <figcaption>Fig. 10 — Wireframe overview</figcaption>
      </figure>

      <div class="img-grid">
        <figure>
          <img src="image11.png" alt="Wireframe screen detail" />
          <figcaption>Fig. 11 — Wireframe detail</figcaption>
        </figure>
        <figure>
          <img src="image12.png" alt="Wireframe screen detail 2" />
          <figcaption>Fig. 12 — Wireframe detail</figcaption>
        </figure>
      </div>

      <h3 class="subsection">Prototype</h3>
      <p>A clickable prototype was built with user needs at the centre. While not exhaustive, the 14-screen implementation covers the main app flow and demonstrates how the key UX decisions translate into an actual interface. Navigation is centralised through a persistent menu to improve navigability without duplicating screens.</p>

      <blockquote>
        The prototype is accessible via the link below — password: <code>Soen357_prototype</code>
        <cite>→ <a href="#" style="color:var(--accent);">[Add Figma / prototype link here]</a></cite>
      </blockquote>

      <div class="img-grid-3">
        <figure>
          <img src="image13.png" alt="Prototype screen 1" />
          <figcaption>Fig. 13 — Prototype screen</figcaption>
        </figure>
        <figure>
          <img src="image14.png" alt="Prototype screen 2" />
          <figcaption>Fig. 14 — Prototype screen</figcaption>
        </figure>
        <figure>
          <img src="image15.png" alt="Prototype screen 3" />
          <figcaption>Fig. 15 — Prototype screen</figcaption>
        </figure>
      </div>

      <h4 class="subsubsection">Design Decisions</h4>
      <ul class="feature-list">
        <li><strong>AAA Colour Scheme</strong> — High-contrast colours throughout for maximum accessibility, especially for elderly users. All combinations meet WCAG AAA standards.</li>
        <li><strong>Multi-Profile / Caregiver Mode</strong> — A menu option allows switching between user accounts so caregivers can manage a dependent's health from the same device.</li>
        <li><strong>Streak Counter</strong> — Gamification element targeting Gen Z users to stay consistent with medication schedules and build loyalty to the app.</li>
        <li><strong>Analytics Page</strong> — Trend graphs and logged metrics for Gen X/Boomer users, including dependent data — directly addressing the "I want to show them a graph" feedback.</li>
        <li><strong>Card-Based Layout</strong> — Visually clean for Gen Z, functionally dense for Millennials/Gen X, and far more accessible than text-dense layouts for Boomers.</li>
        <li><strong>Sign in with Apple</strong> — Reduces onboarding friction — particularly for Gen Z — by eliminating the need to create yet another password.</li>
        <li><strong>18pt+ Font &amp; High Contrast Buttons</strong> — Baseline accessibility commitment targeting Boomer users, ensuring text is readable without assistive technology.</li>
      </ul>

      <h4 class="subsubsection">Colour System</h4>
      <table class="color-table">
        <thead>
          <tr>
            <th>Element</th>
            <th>Name</th>
            <th>Hex</th>
            <th>Usage</th>
            <th>vs. White</th>
            <th>vs. Cloud Gray</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>App Background</td>
            <td>Pure White</td>
            <td><span class="color-swatch" style="background:#FFFFFF;"></span>#FFFFFF</td>
            <td>Main page canvas</td>
            <td>N/A</td>
            <td>N/A</td>
          </tr>
          <tr>
            <td>Card Background</td>
            <td>Cloud Gray</td>
            <td><span class="color-swatch" style="background:#F0F2F5; border-color:#bbb;"></span>#F0F2F5</td>
            <td>Containers / Sections</td>
            <td>1.1:1</td>
            <td>N/A</td>
          </tr>
          <tr>
            <td>Primary Text</td>
            <td>Near Black</td>
            <td><span class="color-swatch" style="background:#1A1A1B;"></span>#1A1A1B</td>
            <td>Headers &amp; Body</td>
            <td>18.7:1 (AAA)</td>
            <td>16.6:1 (AAA)</td>
          </tr>
          <tr>
            <td>Action / Secondary</td>
            <td>Deep Sea Blue</td>
            <td><span class="color-swatch" style="background:#004B87;"></span>#004B87</td>
            <td>Buttons &amp; Highlights</td>
            <td>8.7:1 (AAA)</td>
            <td>7.7:1 (AAA)</td>
          </tr>
          <tr>
            <td>Success</td>
            <td>Forest Green</td>
            <td><span class="color-swatch" style="background:#006837;"></span>#006837</td>
            <td>Plus-sign buttons</td>
            <td>7.5:1 (AAA)</td>
            <td>6.7:1 (AA)</td>
          </tr>
          <tr>
            <td>Warning</td>
            <td>Ruby Red</td>
            <td><span class="color-swatch" style="background:#B30000;"></span>#B30000</td>
            <td>Delete buttons</td>
            <td>7.1:1 (AAA)</td>
            <td>6.3:1 (AA)</td>
          </tr>
          <tr>
            <td>Card Border</td>
            <td>Medium Gray</td>
            <td><span class="color-swatch" style="background:#595959;"></span>#595959</td>
            <td>Card borders</td>
            <td>7.1:1 (AAA)</td>
            <td>6.3:1 (AA)</td>
          </tr>
        </tbody>
      </table>
    </section>

    <!-- ═══════════════════════════════════════════════
         SECTION 5 — USABILITY TESTING
    ════════════════════════════════════════════════ -->
    <section id="usability" class="reveal">
      <span class="section-num">05 / 06</span>
      <h2 class="section-title">Usability Testing</h2>

      <div class="placeholder">
        <strong>[ PLACEHOLDER — Usability Testing ]</strong>
        Add your usability testing methodology, tasks, participants, findings, and any iteration notes here.
      </div>
    </section>

    <!-- ═══════════════════════════════════════════════
         SECTION 6 — REFLECTION
    ════════════════════════════════════════════════ -->
    <section id="reflection" class="reveal">
      <span class="section-num">06 / 06</span>
      <h2 class="section-title">Reflection</h2>

      <div class="placeholder">
        <strong>[ PLACEHOLDER — Reflection ]</strong>
        Add your personal reflection on the project process, what you learned, what you would do differently, and any broader takeaways here.
      </div>
    </section>

  </main>

  <footer>
    <span>SOEN 357 — Mini-Project · Massimo Paolini · 40280323</span>
    <span>Section V · February 2026</span>
  </footer>

  <script>
    // Scroll reveal
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(e => {
        if (e.isIntersecting) {
          e.target.classList.add('visible');
          observer.unobserve(e.target);
        }
      });
    }, { threshold: 0.08 });

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
  </script>

</body>
</html>
