# gg
**VIDYAVERSE AI** is a futuristic study companion for Class 8 and Class 9 students. Using Dual-Explain AI, it teaches Mathematics, Science, SST, and English Grammar step-by-step in English, Hindi, and Bilingual modes, featuring an interactive translator, adaptive quizzes, and revision tools.
[CHATGPT.HTML](https://github.com/user-attachments/files/35210566/CHATGPT.HTML)
<!DOCTYPE html>
<html lang="en">
<head>
<!-- ===== STEP 1: PASTE YOUR API KEY BETWEEN THE QUOTES ON LINE 6 ===== -->
<script>
const API_KEY = "AQ.Ab8RN6KeK9Li3_ZBGBdM2bKmz4bEM1WzIZBGAb56iYpZnARuWw";
const MODEL = "gemini-3.5-flash-lite";
</script>
<script>
// ===== YOUR CHATBOT'S INSTRUCTIONS (RTCC) =====
const SYSTEM_PROMPT = `
ROLE: You are VIDYAVERSE AI, an expert personal teacher for Class 8 and Class 9 students.
TAGLINE: Your AI Teacher. Your Language. Your Future.

Teach Mathematics, Science, Social Studies (History, Geography and Civics), and English Grammar.

LANGUAGES:
- Simple English: clear explanations using age-appropriate words.
- Easy Hindi: natural Hindi explanations.
- Bilingual Exam Mode: English definitions with Hindi meanings.
- Translate English to Hindi and Hindi to English accurately.
- Preserve important technical terms and explain them in both languages.
- If the user writes in Hindi or Hinglish, reply in the same language.

TEACHING:
- Explain mathematics step by step, showing formulas, substitutions, calculations and final answers.
- Teach Physics, Chemistry and Biology with clear explanations and safe, everyday examples.
- Explain History with causes, events, dates where reliably known, and consequences.
- Teach Geography and Civics with simple examples.
- Teach grammar with rules, examples and corrections.
- Support quizzes, MCQs, fill-in-the-blanks, true/false, short answers, revision notes, flashcards and mock tests.
- Give hints before solutions when requested.
- Check student answers, explain mistakes kindly, and suggest practice.
- Explain WHY and HOW, not just the final answer.
- Provide examples, comparisons and real-life applications.
- Ask guiding questions when the student selects question-led learning.
- Never invent textbook quotations, chapter details or verified facts.
- Ask for the board, textbook or chapter when necessary.
- Use safe, age-appropriate scientific examples.
- Encourage understanding instead of memorisation.

CONTEXT:
The application provides the student's selected class, board, subject, chapter, language and learning mode. Follow these settings consistently.
The five modes are Learn, Solve, Translate, Quiz and Revise.
For Class 8 and Class 9, use an appropriate difficulty level.
For translations, provide the translation directly and preserve subject terminology where useful.
For exam preparation, organise answers with headings, definitions, steps and key points.

Be encouraging, accurate, clear and concise. If a question is ambiguous, ask for clarification.
`;
</script>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#070a17">
<title>VIDYAVERSE AI — Your Personal Study Universe</title>

<style>
:root {
  color-scheme: dark;
  --bg: #070a17;
  --panel: rgba(17, 24, 48, .82);
  --panel2: rgba(22, 31, 59, .82);
  --text: #edf5ff;
  --muted: #96a8c8;
  --cyan: #55f4ff;
  --blue: #6688ff;
  --violet: #b67aff;
  --border: rgba(109, 180, 255, .20);
  --danger: #ff7085;
  --shadow: 0 12px 38px rgba(0,0,0,.25);
}
* { box-sizing: border-box; }
body {
  margin: 0;
  min-height: 100vh;
  color: var(--text);
  background:
    radial-gradient(ellipse at 50% -10%, #172552 0, transparent 46%),
    radial-gradient(ellipse at 100% 60%, #1b1040 0, transparent 35%),
    var(--bg);
  font-family: Inter, "Segoe UI", Arial, sans-serif;
  font-size: 14px;
}
body.light {
  color-scheme: light;
  --bg: #edf3ff;
  --panel: rgba(255,255,255,.92);
  --panel2: rgba(236,243,255,.95);
  --text: #17213c;
  --muted: #586985;
  --border: rgba(65,100,170,.22);
  --shadow: 0 12px 38px rgba(40,60,110,.10);
  background: radial-gradient(ellipse at top, #d9eaff, #edf3ff 65%);
}
button, input, select, textarea { font: inherit; }
button, select { cursor: pointer; }
button:focus-visible, input:focus-visible, select:focus-visible,
textarea:focus-visible { outline: 2px solid var(--cyan); outline-offset: 3px; }
button:disabled { opacity: .5; cursor: not-allowed; }
button {
  color: var(--text);
  background: var(--panel2);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 10px 13px;
  transition: .2s ease;
}
button:hover:not(:disabled) {
  border-color: var(--cyan);
  transform: translateY(-1px);
}
button.primary {
  color: #06101e;
  font-weight: 800;
  border: none;
  background: linear-gradient(110deg, var(--cyan), #9c8aff);
}
button.ghost { background: transparent; }
button.danger { color: var(--danger); }
input, select, textarea {
  width: 100%;
  min-width: 0;
  padding: 11px 12px;
  border: 1px solid var(--border);
  border-radius: 10px;
  background: var(--bg);
  color: var(--text);
}
select option { background: var(--bg); color: var(--text); }
textarea { resize: vertical; }
a { color: var(--cyan); }
.app { min-height: 100vh; }
header {
  position: sticky;
  top: 0;
  z-index: 5;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 14px;
  padding: 13px 22px;
  border-bottom: 1px solid var(--border);
  background: var(--bg);
  box-shadow: var(--shadow);
}
.brand { display: flex; align-items: center; gap: 12px; min-width: 0; }
.brand-icon {
  width: 43px; height: 43px; flex-shrink: 0;
  display: grid; place-items: center;
  border-radius: 14px;
  color: var(--cyan);
  font-size: 22px;
  border: 1px solid var(--border);
  background: linear-gradient(135deg, #102e49, #24153f);
  box-shadow: 0 0 25px #40dfff20;
}
.brand h1 { font-size: 17px; letter-spacing: 1.6px; margin: 0; }
.brand p { font-size: 11px; margin: 4px 0 0; color: var(--muted); }
.header-actions { display: flex; gap: 7px; align-items: center; }
.header-actions button { white-space: nowrap; }
.layout {
  display: grid;
  grid-template-columns: 205px minmax(0,1fr);
  max-width: 1600px;
  margin: auto;
  min-height: calc(100vh - 70px);
}
.sidebar {
  padding: 18px 12px;
  border-right: 1px solid var(--border);
  background: rgba(8,13,31,.25);
}
body.light .sidebar { background: rgba(255,255,255,.35); }
.side-label {
  margin: 12px 10px 8px;
  color: var(--muted);
  font-size: 10px;
  letter-spacing: 1.8px;
  text-transform: uppercase;
}
.nav-btn {
  width: 100%; text-align: left; margin: 3px 0;
  border-color: transparent; background: transparent;
  color: var(--muted);
}
.nav-btn.active {
  color: var(--cyan);
  background: linear-gradient(90deg, #32dfff16, #9371ff12);
  border-color: var(--border);
}
.side-note {
  margin-top: 25px; padding: 13px;
  border: 1px solid var(--border);
  border-radius: 12px;
  color: var(--muted); font-size: 11px; line-height: 1.7;
}
main { padding: 22px; min-width: 0; }
.page { display: none; }
.page.active { display: block; }
.welcome {
  display: grid;
  grid-template-columns: minmax(0,1fr) 210px;
  align-items: center;
  gap: 20px;
  padding: 23px;
  border: 1px solid var(--border);
  border-radius: 20px;
  background: linear-gradient(120deg, #101d39cc, #191332aa);
  box-shadow: var(--shadow);
}
body.light .welcome { background: linear-gradient(120deg,#fff,#e6eaff); }
.eyebrow { color: var(--cyan); letter-spacing: 2px; font-size: 10px; font-weight: 800; }
h2 { font-size: clamp(22px,3vw,32px); line-height: 1.2; margin: 10px 0; }
h3 { font-size: 15px; margin: 0 0 12px; }
p { line-height: 1.65; }
.muted { color: var(--muted); }
.welcome p { max-width: 600px; margin-bottom: 16px; }
.core-wrap {
  position: relative;
  display: grid;
  place-items: center;
  min-height: 190px;
}
.core {
  position: relative;
  width: 125px; height: 125px;
  display: grid; place-items: center;
  border-radius: 50%;
  color: #eaffff;
  font-size: 30px;
  background: radial-gradient(circle, #8fffff 0%, #397fff 13%, #341a70 43%, #071023 70%);
  box-shadow: 0 0 25px #50efff66, 0 0 75px #7562ff55, inset 0 0 28px #9bf8ff80;
  animation: pulse 4s ease-in-out infinite;
}
.core::before, .core::after {
  content: ""; position: absolute; inset: -16px;
  border: 1px solid #58eaff8c; border-radius: 50%;
  transform: rotateX(65deg);
  animation: spin 12s linear infinite;
}
.core::after {
  inset: -27px; border-color: #a67aff80;
  transform: rotateY(65deg);
  animation-direction: reverse; animation-duration: 17s;
}
.core-orbit {
  position: absolute; width: 175px; height: 175px;
  border: 1px dashed #54eaff40; border-radius: 50%;
  animation: spin 25s linear infinite;
}
@keyframes spin { to { transform: rotate(360deg); } }
@keyframes pulse { 50% { filter: brightness(1.25); box-shadow: 0 0 45px #50efff80, 0 0 90px #7562ff55; } }
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation: none !important; transition: none !important; scroll-behavior: auto !important; }
}
.section-head {
  display: flex; justify-content: space-between; align-items: center;
  gap: 12px; margin: 25px 0 13px;
}
.section-head h3 { margin: 0; }
.grid-4 { display: grid; grid-template-columns: repeat(4,minmax(0,1fr)); gap: 12px; }
.subject-card {
  text-align: left; min-height: 135px; padding: 16px;
  border: 1px solid var(--border);
  border-radius: 15px;
  background: var(--panel);
  box-shadow: var(--shadow);
}
.subject-card .emoji { font-size: 24px; display: block; margin-bottom: 13px; }
.subject-card strong { display: block; font-size: 13px; }
.subject-card small { display: block; color: var(--muted); margin-top: 7px; line-height: 1.5; }
.controls {
  display: grid; grid-template-columns: repeat(4,minmax(0,1fr)); gap: 12px;
  padding: 16px; border: 1px solid var(--border);
  border-radius: 15px; background: var(--panel);
}
.field label { display: block; color: var(--muted); font-size: 11px; margin-bottom: 7px; }
.field select, .field input { font-size: 12px; }
.chat-layout { margin-top: 20px; }
.chat-top {
  display: flex; justify-content: space-between; align-items: center;
  gap: 10px; flex-wrap: wrap; margin-bottom: 12px;
}
.chat-top h3 { margin: 0; }
.chat-status { font-size: 11px; color: var(--muted); }
.chat-status::before {
  content: ""; display: inline-block; width: 7px; height: 7px;
  margin-right: 6px; border-radius: 50%; background: #4ce6a6;
}
.messages {
  height: min(48vh,520px); min-height: 300px;
  overflow-y: auto; padding: 15px;
  border: 1px solid var(--border);
  border-radius: 16px;
  background: rgba(5,9,24,.38);
  scroll-behavior: smooth;
}
body.light .messages { background: rgba(255,255,255,.65); }
.message { display: flex; gap: 9px; margin: 13px 0; align-items: flex-start; }
.message.user { flex-direction: row-reverse; }
.avatar {
  width: 33px; height: 33px; flex-shrink: 0;
  display: grid; place-items: center;
  border-radius: 50%; background: var(--panel2);
  border: 1px solid var(--border); font-size: 17px;
}
.bubble {
  max-width: min(86%,800px); min-width: 0;
  padding: 12px 14px; border: 1px solid var(--border);
  border-radius: 13px; background: var(--panel);
  overflow-wrap: anywhere; line-height: 1.7;
}
.user .bubble { background: linear-gradient(135deg,#15364a,#252044); }
body.light .user .bubble { background: #dfeeff; }
.bubble p { margin: 0 0 9px; }
.bubble p:last-child { margin-bottom: 0; }
.bubble pre { white-space: pre-wrap; overflow-wrap: anywhere; }
.bubble code { background: #7d8db622; border-radius: 4px; padding: 2px 4px; }
.bubble ul, .bubble ol { padding-left: 22px; }
.bubble table { border-collapse: collapse; width: 100%; display: block; overflow-x: auto; }
.bubble th, .bubble td { border: 1px solid var(--border); padding: 7px; }
.message-tools { display: flex; gap: 5px; flex-wrap: wrap; margin-top: 9px; }
.message-tools button { font-size: 10px; padding: 5px 8px; }
.starters { display: flex; gap: 8px; flex-wrap: wrap; margin: 12px 0; }
.starters button { border-radius: 20px; font-size: 11px; }
.composer {
  display: flex; gap: 8px; align-items: flex-end;
  padding: 10px; margin-top: 12px;
  border: 1px solid var(--border); border-radius: 15px;
  background: var(--panel);
}
.composer textarea {
  min-height: 45px; max-height: 150px;
  border: none; background: transparent; padding: 12px;
  resize: none;
}
.composer button { flex-shrink: 0; }
.hint { font-size: 10px; color: var(--muted); margin: 8px 4px; }
.typing { display: flex; gap: 5px; padding: 5px; }
.typing span {
  width: 7px; height: 7px; border-radius: 50%;
  background: var(--cyan); animation: bounce .8s infinite alternate;
}
.typing span:nth-child(2) { animation-delay: .2s; }
.typing span:nth-child(3) { animation-delay: .4s; }
@keyframes bounce { to { opacity: .25; transform: translateY(-5px); } }
.panel {
  padding: 18px; border: 1px solid var(--border);
  border-radius: 15px; background: var(--panel); margin-top: 14px;
}
.form-grid { display: grid; grid-template-columns: repeat(2,minmax(0,1fr)); gap: 13px; }
.form-grid .full { grid-column: 1/-1; }
.action-row { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 13px; }
.stat-grid { display: grid; grid-template-columns: repeat(3,minmax(0,1fr)); gap: 12px; margin-top: 15px; }
.stat { padding: 18px; border: 1px solid var(--border); border-radius: 13px; background: var(--panel); }
.stat strong { display: block; font-size: 24px; color: var(--cyan); margin-bottom: 7px; }
.task { display: flex; gap: 10px; align-items: center; padding: 10px 0; border-bottom: 1px solid var(--border); }
.task input { width: auto; }
footer { color: var(--muted); font-size: 10px; text-align: center; padding: 20px; }
.toast { color: var(--muted); font-size: 11px; margin-top: 10px; }
.error { color: var(--danger); }
.hidden { display: none !important; }

@media (max-width: 1050px) {
  .grid-4 { grid-template-columns: repeat(2,minmax(0,1fr)); }
  .layout { grid-template-columns: 165px minmax(0,1fr); }
  main { padding: 16px; }
}
@media (max-width: 680px) {
  header { padding: 10px; align-items: flex-start; }
  .brand h1 { font-size: 14px; }
  .brand p { font-size: 10px; }
  .header-actions { flex-wrap: wrap; justify-content: flex-end; }
  .header-actions button { padding: 8px; font-size: 11px; }
  .layout { display: block; }
  .sidebar {
    position: static; display: flex; gap: 5px; overflow-x: auto;
    padding: 8px; border-right: 0; border-bottom: 1px solid var(--border);
  }
  .side-label, .side-note { display: none; }
  .nav-btn { width: auto; white-space: nowrap; padding: 9px 12px; }
  main { padding: 12px; }
  .welcome { grid-template-columns: minmax(0,1fr); padding: 17px; }
  .core-wrap { min-height: 155px; }
  .controls { grid-template-columns: repeat(2,minmax(0,1fr)); padding: 12px; }
  .grid-4 { gap: 8px; }
  .subject-card { padding: 12px; min-height: 125px; }
  .messages { height: 48vh; min-height: 260px; padding: 9px; }
  .bubble { max-width: 90%; padding: 10px; }
  .form-grid, .stat-grid { grid-template-columns: minmax(0,1fr); }
  .form-grid .full { grid-column: auto; }
}
</style>
</head>

<body>
<div class="app">
<header>
  <div class="brand">
    <div class="brand-icon" aria-hidden="true">✧</div>
    <div>
      <h1>VIDYAVERSE <span style="color:var(--cyan)">AI</span></h1>
      <p>Your AI Teacher. Your Language. Your Future.</p>
    </div>
  </div>
  <div class="header-actions">
    <button id="newChatBtn" title="Start a new conversation">＋ New Chat</button>
    <button id="clearBtn" class="danger" title="Clear saved conversation">Clear Chat</button>
    <button id="themeBtn" title="Toggle light and dark mode" aria-label="Toggle theme">☀️</button>
  </div>
</header>

<div class="layout">
<aside class="sidebar" aria-label="Main navigation">
  <div class="side-label">Workspace</div>
  <button class="nav-btn active" data-page="home">⌂ &nbsp; Dashboard</button>
  <button class="nav-btn" data-page="chat">◉ &nbsp; AI Tutor</button>
  <button class="nav-btn" data-page="translate">⇄ &nbsp; Translate</button>
  <button class="nav-btn" data-page="quiz">✎ &nbsp; Quiz Studio</button>
  <button class="nav-btn" data-page="revise">◈ &nbsp; Quick Revision</button>
  <button class="nav-btn" data-page="planner">▦ &nbsp; Study Planner</button>
  <button class="nav-btn" data-page="progress">◷ &nbsp; Progress</button>
  <div class="side-note">
    <strong style="color:var(--cyan)">YOUR STUDY UNIVERSE</strong><br>
    Learn at your pace. Ask questions. Understand the WHY.
  </div>
</aside>

<main>
<section class="page active" id="page-home">
  <div class="welcome">
    <div>
      <div class="eyebrow">✦ YOUR PERSONAL AI LEARNING LAB</div>
      <h2>Welcome to your<br><span style="color:var(--cyan)">Study Universe.</span></h2>
      <p class="muted">Explore every subject, understand difficult concepts, switch between Hindi and English, and prepare for exams with your personal AI tutor.</p>
      <div class="action-row">
        <button class="primary" id="startLearningBtn">Start Learning →</button>
        <button id="welcomeQuizBtn">Practice a Quiz</button>
      </div>
    </div>
    <div class="core-wrap" aria-label="Animated holographic AI core">
      <div class="core-orbit"></div>
      <div class="core">✧</div>
    </div>
  </div>

  <div class="section-head">
    <h3>Choose Your Subject Expert</h3>
    <span class="muted">4 learning modules</span>
  </div>
  <div class="grid-4">
    <button class="subject-card" data-subject="Mathematics">
      <span class="emoji">∑</span><strong>Maths Master</strong>
      <small>Step-by-step solutions, formulas and reasoning.</small>
    </button>
    <button class="subject-card" data-subject="Science">
      <span class="emoji">⚗️</span><strong>Science Lab</strong>
      <small>Physics, Chemistry, Biology and everyday science.</small>
    </button>
    <button class="subject-card" data-subject="Social Studies">
      <span class="emoji">🌍</span><strong>SST Explorer</strong>
      <small>History, Geography, Civics and revision notes.</small>
    </button>
    <button class="subject-card" data-subject="English Grammar">
      <span class="emoji">📘</span><strong>Grammar Lab</strong>
      <small>Grammar, vocabulary, writing and practice.</small>
    </button>
  </div>

  <div class="section-head"><h3>Personalise Your Learning</h3></div>
  <div class="controls">
    <div class="field">
      <label for="classSelect">YOUR CLASS</label>
      <select id="classSelect"><option>Class 8</option><option>Class 9</option></select>
    </div>
    <div class="field">
      <label for="boardSelect">EDUCATIONAL BOARD</label>
      <select id="boardSelect">
        <option>CBSE</option><option>ICSE</option>
        <option>Punjab State Board</option><option>Other State Board</option>
        <option>Not specified</option>
      </select>
    </div>
    <div class="field">
      <label for="languageSelect">LEARNING LANGUAGE</label>
      <select id="languageSelect">
        <option value="English">English</option>
        <option value="Hindi">Hindi</option>
        <option value="Hindi + English">Hindi + English</option>
      </select>
    </div>
    <div class="field">
      <label for="subjectSelect">SUBJECT</label>
      <select id="subjectSelect">
        <option>Mathematics</option><option>Science</option>
        <option>Social Studies</option><option>English Grammar</option>
      </select>
    </div>
    <div class="field">
      <label for="chapterInput">CHAPTER / TOPIC</label>
      <input id="chapterInput" placeholder="e.g. Linear equations">
    </div>
    <div class="field">
      <label for="modeSelect">LEARNING MODE</label>
      <select id="modeSelect">
        <option>Learn</option><option>Solve</option><option>Translate</option>
        <option>Quiz</option><option>Revise</option>
      </select>
    </div>
    <div class="field">
      <label for="goalSelect">LEARNING GOAL</label>
      <select id="goalSelect">
        <option>Understand concepts</option><option>Prepare for exams</option>
        <option>Practise questions</option><option>Improve weak topics</option>
      </select>
    </div>
    <div class="field">
      <label for="textbookInput">TEXTBOOK (OPTIONAL)</label>
      <input id="textbookInput" placeholder="Book name or edition">
    </div>
  </div>

  <div class="chat-layout">
    <div class="chat-top">
      <h3>✧ Your AI Teacher</h3>
      <span class="chat-status" id="statusText">Ready to learn</span>
    </div>
    <div class="messages" id="messages" aria-live="polite" aria-label="Conversation"></div>
    <div class="starters" id="starterChips">
      <button data-prompt="Explain linear equations step by step with a simple example.">∑ Explain a maths concept</button>
      <button data-prompt="Explain photosynthesis in simple language and give an example.">⚗️ Explore science</button>
      <button data-prompt="Create short revision notes with key points for my current topic.">◈ Make revision notes</button>
    </div>
    <div class="composer">
      <textarea id="messageInput" rows="1" aria-label="Your question" placeholder="Ask anything about your studies..."></textarea>
      <button id="micBtn" class="hidden" title="Speak your question" aria-label="Use microphone">🎙️</button>
      <button id="sendBtn" class="primary">Send ↑</button>
    </div>
    <div class="hint">Enter to send · Shift + Enter for a new line · Your selected class and subject guide the AI.</div>
  </div>
</section>

<section class="page" id="page-chat">
  <div class="section-head"><h2>AI Tutor</h2></div>
  <p class="muted">Ask follow-up questions and explore difficult concepts with your selected learning settings.</p>
  <button class="primary" id="backToChatBtn">Go to conversation ↓</button>
</section>

<section class="page" id="page-translate">
  <div class="section-head"><h2>Dual-Explain Translator</h2></div>
  <p class="muted">Translate academic content between English and Hindi while preserving important subject terminology.</p>
  <div class="panel">
    <div class="form-grid">
      <div class="field">
        <label for="sourceLang">FROM</label>
        <select id="sourceLang"><option>English</option><option>Hindi</option><option>Auto-detect</option></select>
      </div>
      <div class="field">
        <label for="targetLang">TO</label>
        <select id="targetLang"><option>Hindi</option><option>English</option><option>Hindi + English</option></select>
      </div>
      <div class="field full">
        <label for="translationInput">TEXT TO TRANSLATE</label>
        <textarea id="translationInput" rows="6" placeholder="Enter your sentence, question, definition or textbook paragraph..."></textarea>
      </div>
    </div>
    <div class="action-row">
      <button class="primary" id="translateBtn">Translate with AI</button>
      <button id="clearTranslationBtn">Clear</button>
    </div>
    <div id="translationOutput" class="panel hidden" aria-live="polite"></div>
    <button id="copyTranslationBtn" class="hidden">Copy Translation</button>
  </div>
</section>

<section class="page" id="page-quiz">
  <div class="section-head"><h2>Quiz Studio</h2></div>
  <p class="muted">Generate questions, attempt them, and ask your AI tutor to explain your answers.</p>
  <div class="panel">
    <div class="form-grid">
      <div class="field">
        <label for="quizTopic">TOPIC</label>
        <input id="quizTopic" placeholder="e.g. Algebra, cells, democracy">
      </div>
      <div class="field">
        <label for="quizType">QUESTION TYPE</label>
        <select id="quizType">
          <option>Multiple-choice questions</option>
          <option>Fill in the blanks</option>
          <option>True or false</option>
          <option>Short-answer questions</option>
          <option>Mixed quiz</option>
        </select>
      </div>
      <div class="field">
        <label for="quizCount">NUMBER OF QUESTIONS</label>
        <select id="quizCount"><option>5</option><option>10</option><option>15</option></select>
      </div>
    </div>
    <div class="action-row">
      <button class="primary" id="generateQuizBtn">Generate Quiz</button>
      <button id="checkQuizBtn">Check My Answers</button>
    </div>
    <div class="field" style="margin-top:15px">
      <label for="quizAnswers">YOUR ANSWERS / ATTEMPT</label>
      <textarea id="quizAnswers" rows="7" placeholder="Write your answers here, for example: 1. B, 2. True, 3. ..."></textarea>
    </div>
    <div id="quizResult" class="panel hidden" aria-live="polite"></div>
  </div>
</section>

<section class="page" id="page-revise">
  <div class="section-head"><h2>Quick Revision</h2></div>
  <p class="muted">Create concise, exam-focused revision notes for a chapter or topic.</p>
  <div class="panel">
    <div class="field">
      <label for="revisionTopic">CHAPTER OR TOPIC</label>
      <input id="revisionTopic" placeholder="Enter a chapter or topic">
    </div>
    <div class="field" style="margin-top:12px">
      <label for="revisionStyle">REVISION FORMAT</label>
      <select id="revisionStyle">
        <option>Quick revision notes</option>
        <option>Important definitions and formulas</option>
        <option>Flashcards with answers</option>
        <option>Important exam questions</option>
        <option>Chapter summary and key dates</option>
        <option>Compare two concepts</option>
        <option>Teach me like a beginner</option>
        <option>Explain why and how</option>
        <option>Teach me through questions</option>
        <option>Real-life applications</option>
        <option>Give me a hint</option>
      </select>
    </div>
    <div class="action-row">
      <button id="makeRevisionBtn" class="primary">Create Revision Material</button>
      <button id="simpleExplainBtn">Explain Simply</button>
      <button id="exampleBtn">Give an Example</button>
    </div>
  </div>
</section>

<section class="page" id="page-planner">
  <div class="section-head"><h2>Daily Study Planner</h2></div>
  <p class="muted">Create your own study tasks. Your checklist is saved locally in this browser.</p>
  <div class="panel">
    <div class="form-grid">
      <div class="field">
        <label for="taskInput">STUDY GOAL</label>
        <input id="taskInput" placeholder="e.g. Revise algebra formulas">
      </div>
      <div class="field">
        <label for="taskMinutes">PLANNED MINUTES</label>
        <select id="taskMinutes"><option>15</option><option>25</option><option>30</option><option>45</option><option>60</option></select>
      </div>
    </div>
    <div class="action-row"><button class="primary" id="addTaskBtn">Add Study Goal</button></div>
    <div id="taskList"></div>
    <div class="action-row"><button id="clearTasksBtn" class="danger">Clear Planner</button></div>
  </div>
</section>

<section class="page" id="page-progress">
  <div class="section-head"><h2>Learning Progress</h2></div>
  <p class="muted">A local summary of your activity in this browser. It is not an official grade or an assessment of mastery.</p>
  <div class="stat-grid">
    <div class="stat"><strong id="statMessages">0</strong>Messages sent</div>
    <div class="stat"><strong id="statTopics">0</strong>Topics explored</div>
    <div class="stat"><strong id="statQuizzes">0</strong>Quiz requests</div>
  </div>
  <div class="panel">
    <h3>Learning History</h3>
    <div id="topicHistory" class="muted">Your activity will appear here after you begin studying.</div>
    <div class="action-row"><button id="resetProgressBtn" class="danger">Reset Local Progress</button></div>
  </div>
</section>

<footer>
  VIDYAVERSE AI · Learn with curiosity · Built for Class 8 and Class 9
  <p>Prototype notice: a browser-based API key is visible to users. Do not publish a personal API key in a public website.</p>
</footer>
</main>
</div>
</div>

<script>
// ===== GEMINI API CONNECTION =====
// The API key and model are configured in the first script at the top of this file.
async function callAI(history) {
  // history = [{ role: "user" | "assistant", text: "..." }, ...]
  const url = "https://generativelanguage.googleapis.com/v1beta/models/" + MODEL + ":generateContent";
  const res = await fetch(url, {
    method: "POST",
    headers: { "Content-Type": "application/json", "x-goog-api-key": API_KEY.trim() },
    body: JSON.stringify({
      system_instruction: { parts: [{ text: SYSTEM_PROMPT }] },
      contents: history.map(m => ({
        role: m.role === "assistant" ? "model" : "user",
        parts: [{ text: m.text }]
      }))
    })
  });
  const data = await res.json().catch(() => ({}));
  if (!res.ok) throw new Error("Error " + res.status + ": " + ((data.error && data.error.message) || "Request failed"));
  const parts = (data.candidates && data.candidates[0] && data.candidates[0].content && data.candidates[0].content.parts) || [];
  const text = parts.filter(p => p.text && !p.thought).map(p => p.text).join("");
  if (!text) throw new Error("The AI sent an empty reply. Try asking again.");
  return text;
}

// ===== APP STATE =====
const $ = id => document.getElementById(id);
const STORAGE_KEY = "vidyaverse_chat_v1";
const PREF_KEY = "vidyaverse_prefs_v1";
const TASK_KEY = "vidyaverse_tasks_v1";
const PROGRESS_KEY = "vidyaverse_progress_v1";
let history = [];
let busy = false;
let lastQuestion = "";
let lastAIAnswer = "";
let messagesSent = 0;
let topics = [];
let quizRequests = 0;
let tasks = [];
let recognition = null;

function safeLoad(key, fallback) {
  try {
    const value = localStorage.getItem(key);
    return value ? JSON.parse(value) : fallback;
  } catch (e) { return fallback; }
}
function saveChat() {
  try { localStorage.setItem(STORAGE_KEY, JSON.stringify(history)); }
  catch (e) { setStatus("Chat could not be saved in this browser."); }
}
function setStatus(text, error = false) {
  $("statusText").textContent = text;
  $("statusText").classList.toggle("error", error);
}
function escapeHTML(text) {
  return String(text).replace(/[&<>"']/g, ch => ({
    "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;"
  })[ch]);
}

// Lightweight safe Markdown rendering. Raw HTML is escaped before formatting.
function renderMarkdown(text) {
  let s = escapeHTML(text);
  s = s.replace(/```([\s\S]*?)```/g, (_, code) => "<pre><code>" + code + "</code></pre>");
  s = s.replace(/`([^`\n]+)`/g, "<code>$1</code>");
  s = s.replace(/\*\*(.+?)\*\*/g, "<strong>$1</strong>");
  s = s.replace(/(^|[^*])\*([^*\n]+)\*/g, "$1<em>$2</em>");
  const lines = s.split("\n");
  let html = "", list = "";
  function closeList() { if (list) { html += "</" + list + ">"; list = ""; } }
  for (const line of lines) {
    const ul = line.match(/^\s*[-*]\s+(.+)$/);
    const ol = line.match(/^\s*\d+[.)]\s+(.+)$/);
    if (ul || ol) {
      const type = ul ? "ul" : "ol";
      if (list !== type) { closeList(); list = type; html += "<" + type + ">"; }
      html += "<li>" + (ul ? ul[1] : ol[1]) + "</li>";
    } else {
      closeList();
      if (/^###\s+/.test(line)) html += "<h4>" + line.replace(/^###\s+/, "") + "</h4>";
      else if (/^##\s+/.test(line)) html += "<h3>" + line.replace(/^##\s+/, "") + "</h3>";
      else if (/^#\s+/.test(line)) html += "<h3>" + line.replace(/^#\s+/, "") + "</h3>";
      else if (line.trim()) html += "<p>" + line + "</p>";
    }
  }
  closeList();
  return html;
}

function persistProgress() {
  try {
    localStorage.setItem(PROGRESS_KEY, JSON.stringify({
      messagesSent, topics, quizRequests
    }));
  } catch (e) {}
  updateProgress();
}
function updateProgress() {
  $("statMessages").textContent = messagesSent;
  $("statTopics").textContent = topics.length;
  $("statQuizzes").textContent = quizRequests;
  $("topicHistory").innerHTML = topics.length
    ? topics.slice(-12).reverse().map(t => "<p>✧ " + escapeHTML(t) + "</p>").join("")
    : "Your activity will appear here after you begin studying.";
}

function getSettings() {
  return {
    className: $("classSelect").value,
    board: $("boardSelect").value,
    language: $("languageSelect").value,
    subject: $("subjectSelect").value,
    chapter: $("chapterInput").value.trim(),
    mode: $("modeSelect").value,
    goal: $("goalSelect").value,
    textbook: $("textbookInput").value.trim()
  };
}
function savePrefs() {
  try { localStorage.setItem(PREF_KEY, JSON.stringify(getSettings())); }
  catch (e) {}
}
function loadPrefs() {
  const p = safeLoad(PREF_KEY, {});
  for (const [id, value] of Object.entries({
    classSelect:p.className, boardSelect:p.board, languageSelect:p.language,
    subjectSelect:p.subject, chapterInput:p.chapter, modeSelect:p.mode,
    goalSelect:p.goal, textbookInput:p.textbook
  })) {
    if (value !== undefined && $(id)) $(id).value = value;
  }
}
function makeContext(question) {
  const s = getSettings();
  return `\n\n[STUDENT SETTINGS]
Class: ${s.className}
Board: ${s.board}
Subject: ${s.subject}
Chapter/topic: ${s.chapter || "Not specified"}
Preferred language: ${s.language}
Learning mode: ${s.mode}
Goal: ${s.goal}
Textbook: ${s.textbook || "Not specified"}
Current request: ${question}
Use these settings in your response.`;
}

function addMessage(role, text, options = {}) {
  const welcome = options.welcome || false;
  const row = document.createElement("div");
  row.className = "message " + (role === "user" ? "user" : "assistant");
  const avatar = document.createElement("div");
  avatar.className = "avatar";
  avatar.textContent = role === "user" ? "🙂" : "✧";
  const bubble = document.createElement("div");
  bubble.className = "bubble";
  const content = document.createElement("div");
  content.className = "message-content";
  content.innerHTML = renderMarkdown(text);
  bubble.appendChild(content);

  if (role === "assistant" && !welcome) {
    const tools = document.createElement("div");
    tools.className = "message-tools";
    const copy = document.createElement("button");
    copy.textContent = "▣ Copy";
    copy.title = "Copy this answer";
    copy.addEventListener("click", () => copyText(text, copy));
    const speak = document.createElement("button");
    speak.textContent = "🔊 Read";
    speak.title = "Read this answer aloud";
    speak.addEventListener("click", () => speakText(text));
    const simpler = document.createElement("button");
    simpler.textContent = "Explain simply";
    simpler.addEventListener("click", () => sendPrompt("Please explain your previous answer in simpler language with an everyday example."));
    const why = document.createElement("button");
    why.textContent = "Why and how?";
    why.addEventListener("click", () => sendPrompt("Explain why and how the previous answer works, step by step."));
    tools.append(copy, speak, simpler, why);
    bubble.appendChild(tools);
  }
  row.append(avatar, bubble);
  $("messages").appendChild(row);
  $("messages").scrollTop = $("messages").scrollHeight;
  return row;
}
function copyText(text, button) {
  if (navigator.clipboard && window.isSecureContext) {
    navigator.clipboard.writeText(text).then(() => {
      button.textContent = "Copied!";
      setTimeout(() => button.textContent = "▣ Copy", 1300);
    }).catch(() => fallbackCopy(text));
  } else fallbackCopy(text);
}
function fallbackCopy(text) {
  const area = document.createElement("textarea");
  area.value = text;
  area.style.position = "fixed";
  area.style.opacity = "0";
  document.body.appendChild(area);
  area.select();
  try { document.execCommand("copy"); setStatus("Text copied."); }
  catch (e) { setStatus("Copy failed. Please select and copy the text manually.", true); }
  area.remove();
}
function speakText(text) {
  if (!("speechSynthesis" in window)) {
    setStatus("Speech playback is not supported in this browser.", true);
    return;
  }
  window.speechSynthesis.cancel();
  const utterance = new SpeechSynthesisUtterance(text);
  utterance.lang = $("languageSelect").value === "Hindi" ? "hi-IN" : "en-IN";
  window.speechSynthesis.speak(utterance);
}
function showTyping() {
  const row = document.createElement("div");
  row.className = "message assistant";
  row.id = "typingRow";
  row.innerHTML = '<div class="avatar">✧</div><div class="bubble"><div class="typing" aria-label="AI is thinking"><span></span><span></span><span></span></div><div class="muted">Thinking...</div></div>';
  $("messages").appendChild(row);
  $("messages").scrollTop = $("messages").scrollHeight;
}
function removeTyping() { const el = $("typingRow"); if (el) el.remove(); }
function renderHistory() {
  $("messages").innerHTML = "";
  if (!history.length) {
    addMessage("assistant",
      "Welcome to **VIDYAVERSE AI**! ✨\n\nI am your personal study companion for Mathematics, Science, Social Studies and English Grammar.\n\nChoose your class, board, language and subject above, then ask me anything. I can explain concepts step by step, translate, create practice questions and help you revise.",
      { welcome: true });
  } else {
    history.forEach(m => addMessage(m.role === "assistant" ? "assistant" : "user", m.text));
  }
  $("messages").scrollTop = $("messages").scrollHeight;
}

async function sendPrompt(raw) {
  const question = String(raw || "").trim();
  if (!question || busy) return;
  if (!API_KEY.trim() || API_KEY.trim() === "PASTE_YOUR_API_KEY_HERE") {
    addMessage("assistant", "⚠️ **API key not configured.** Paste your Gemini API key into the `API_KEY` line near the top of `index.html`, save the file, and refresh the page.");
    setStatus("API key required", true);
    return;
  }

  savePrefs();
  const contextualQuestion = question + makeContext(question);
  history.push({ role: "user", text: contextualQuestion });
  // Only send the user's original question to the visible chat.
  addMessage("user", question);
  lastQuestion = question;
  saveChat();

  busy = true;
  $("sendBtn").disabled = true;
  $("sendBtn").textContent = "Thinking…";
  setStatus("AI is thinking");
  showTyping();

  try {
    // Gemini conversation contents must start with a user message.
    const reply = await callAI(history);
    history.push({ role: "assistant", text: reply });
    lastAIAnswer = reply;
    messagesSent++;
    const s = getSettings();
    const topic = s.chapter || s.subject;
    if (topic && !topics.includes(topic)) topics.push(topic);
    saveChat();
    persistProgress();
    removeTyping();
    addMessage("assistant", reply);
    setStatus("Response received");
  } catch (err) {
    removeTyping();
    const errorText = String(err && err.message ? err.message : err);
    addMessage("assistant", "⚠️ **Gemini API error**\n\n" + errorText + "\n\nCheck your API key, internet connection, model availability and Google AI API access. This is a real request error; no answer has been fabricated.");
    setStatus("API request failed", true);
  } finally {
    busy = false;
    $("sendBtn").disabled = false;
    $("sendBtn").textContent = "Send ↑";
    $("messageInput").focus();
  }
}

function goPage(name) {
  document.querySelectorAll(".page").forEach(p => p.classList.toggle("active", p.id === "page-" + name));
  document.querySelectorAll(".nav-btn").forEach(b => b.classList.toggle("active", b.dataset.page === name));
  if (name === "chat") {
    $("page-home").classList.remove("active");
    $("page-home").style.display = "none";
    $("page-chat").classList.add("active");
    $("page-chat").style.display = "block";
    $("page-chat").innerHTML = "";
    const heading = document.createElement("div");
    heading.className = "section-head";
    heading.innerHTML = "<h2>AI Tutor</h2>";
    const note = document.createElement("p");
    note.className = "muted";
    note.textContent = "Your ongoing conversation is available on the Dashboard.";
    const button = document.createElement("button");
    button.className = "primary";
    button.textContent = "Open conversation";
    button.onclick = () => goPage("home");
    $("page-chat").append(heading, note, button);
  } else {
    $("page-home").style.display = "";
    $("page-chat").style.display = "";
  }
  if (name === "planner") renderTasks();
  if (name === "progress") updateProgress();
}

function startNewChat() {
  if (busy) { setStatus("Wait for the current response before starting a new chat."); return; }
  history = [];
  lastQuestion = "";
  lastAIAnswer = "";
  saveChat();
  renderHistory();
  goPage("home");
  setStatus("New chat ready");
}
function clearChat() {
  if (busy) { setStatus("Wait for the current response before clearing the chat."); return; }
  history = [];
  lastQuestion = "";
  lastAIAnswer = "";
  saveChat();
  renderHistory();
  setStatus("Chat cleared");
}
function prepareAndSend(prompt) {
  if (prompt) {
    goPage("home");
    $("messageInput").value = prompt;
    sendPrompt(prompt);
  }
}

// ===== CHAT EVENTS =====
$("sendBtn").addEventListener("click", () => {
  const value = $("messageInput").value;
  if (!value.trim()) return;
  $("messageInput").value = "";
  $("messageInput").style.height = "auto";
  sendPrompt(value);
});
$("messageInput").addEventListener("keydown", e => {
  if (e.key === "Enter" && !e.shiftKey && !e.isComposing) {
    e.preventDefault();
    $("sendBtn").click();
  }
});
$("messageInput").addEventListener("input", () => {
  const el = $("messageInput");
  el.style.height = "auto";
  el.style.height = Math.min(el.scrollHeight, 150) + "px";
});
$("clearBtn").addEventListener("click", clearChat);
$("newChatBtn").addEventListener("click", startNewChat);
$("starterChips").addEventListener("click", e => {
  const button = e.target.closest("button[data-prompt]");
  if (button) prepareAndSend(button.dataset.prompt);
});
document.querySelectorAll("[data-subject]").forEach(button => {
  button.addEventListener("click", () => {
    $("subjectSelect").value = button.dataset.subject;
    savePrefs();
    goPage("home");
    $("messageInput").value = "Help me learn " + button.dataset.subject + " for " + $("classSelect").value + ". Start with an important topic and explain it step by step.";
    $("messageInput").focus();
  });
});
document.querySelectorAll(".nav-btn").forEach(button => {
  button.addEventListener("click", () => goPage(button.dataset.page));
});
$("startLearningBtn").addEventListener("click", () => {
  goPage("home");
  $("messageInput").focus();
});
$("welcomeQuizBtn").addEventListener("click", () => goPage("quiz"));
$("backToChatBtn").addEventListener("click", () => goPage("home"));

["classSelect","boardSelect","languageSelect","subjectSelect","chapterInput",
 "modeSelect","goalSelect","textbookInput"].forEach(id => {
  $(id).addEventListener("change", savePrefs);
});

// ===== TRANSLATION WORKSPACE =====
$("translateBtn").addEventListener("click", async () => {
  const source = $("translationInput").value.trim();
  if (!source) { setStatus("Enter some text to translate.", true); return; }
  const prompt = `Translate the following text from ${$("sourceLang").value} to ${$("targetLang").value}.
Preserve its meaning and important academic terminology. If the target is Hindi + English, show a clear bilingual version.
Text to translate:
${source}`;
  $("translationOutput").classList.remove("hidden");
  $("translationOutput").textContent = "Translating...";
  $("translateBtn").disabled = true;
  try {
    const reply = await requestOneShot(prompt);
    $("translationOutput").innerHTML = renderMarkdown(reply);
    $("copyTranslationBtn").classList.remove("hidden");
  } catch (e) {
    $("translationOutput").textContent = "Translation failed: " + e.message;
  } finally { $("translateBtn").disabled = false; }
});
$("clearTranslationBtn").addEventListener("click", () => {
  $("translationInput").value = "";
  $("translationOutput").textContent = "";
  $("translationOutput").classList.add("hidden");
  $("copyTranslationBtn").classList.add("hidden");
});
$("copyTranslationBtn").addEventListener("click", () => {
  copyText($("translationOutput").innerText, $("copyTranslationBtn"));
});

// One-shot tasks use the same Gemini API and error handling.
async function requestOneShot(prompt) {
  if (!API_KEY.trim() || API_KEY.trim() === "PASTE_YOUR_API_KEY_HERE") {
    throw new Error("Paste your Gemini API key into the API_KEY line at the top of index.html.");
  }
  const s = getSettings();
  const enriched = prompt + makeContext(prompt);
  return await callAI([{ role: "user", text: enriched }]);
}

// ===== QUIZ STUDIO =====
$("generateQuizBtn").addEventListener("click", async () => {
  const topic = $("quizTopic").value.trim() || getSettings().chapter || getSettings().subject;
  const count = $("quizCount").value;
  const type = $("quizType").value;
  $("quizResult").classList.remove("hidden");
  $("quizResult").textContent = "Creating your quiz...";
  $("generateQuizBtn").disabled = true;
  try {
    const reply = await requestOneShot(
      `Create ${count} ${type} for ${topic} at ${getSettings().className} level.
Subject: ${getSettings().subject}. Language: ${getSettings().language}.
Number each question clearly. For MCQs include four options. Do NOT reveal the answer key yet.
After the questions, invite the student to write answers numbered in order.`
    );
    $("quizResult").innerHTML = renderMarkdown(reply);
    quizRequests++;
    persistProgress();
    topics = [...new Set([...topics, topic])];
    persistProgress();
  } catch (e) {
    $("quizResult").textContent = "Quiz generation failed: " + e.message;
  } finally { $("generateQuizBtn").disabled = false; }
});
$("checkQuizBtn").addEventListener("click", async () => {
  const answers = $("quizAnswers").value.trim();
  if (!answers) { $("quizResult").classList.remove("hidden"); $("quizResult").textContent = "Write your attempted answers first."; return; }
  const topic = $("quizTopic").value.trim() || getSettings().chapter || getSettings().subject;
  $("quizResult").classList.remove("hidden");
  $("quizResult").textContent = "Checking your answers...";
  $("checkQuizBtn").disabled = true;
  try {
    const reply = await requestOneShot(
      `Check this student's quiz attempt for ${topic}. Questions may be in the Quiz Studio above, but if their exact text is unavailable, clearly say so and ask them to paste the questions too. Answers submitted:\n${answers}\nExplain each correction kindly. Only give a score when the questions and correct answers are available. Recommend topics to revise.`
    );
    $("quizResult").innerHTML = renderMarkdown(reply);
  } catch (e) {
    $("quizResult").textContent = "Answer checking failed: " + e.message;
  } finally { $("checkQuizBtn").disabled = false; }
});

// ===== REVISION AND TEACHING TOOLS =====
async function makeRevision(kind) {
  const topic = $("revisionTopic").value.trim() || getSettings().chapter;
  if (!topic) { setStatus("Enter a chapter or topic for revision.", true); $("revisionTopic").focus(); return; }
  const style = kind || $("revisionStyle").value;
  goPage("home");
  await sendPrompt("Create study material for: " + topic + ". Requested format: " + style + ". Use " + getSettings().language + ". Keep it appropriate for " + getSettings().className + ". If exact textbook information is uncertain, say so.");
}
$("makeRevisionBtn").addEventListener("click", () => makeRevision());
$("simpleExplainBtn").addEventListener("click", () => makeRevision("Teach me like a beginner, using simple words and an everyday example"));
$("exampleBtn").addEventListener("click", () => makeRevision("Explain with a worked example and step-by-step reasoning"));

// ===== STUDY PLANNER =====
function saveTasks() {
  try { localStorage.setItem(TASK_KEY, JSON.stringify(tasks)); } catch (e) {}
  renderTasks();
}
function renderTasks() {
  const container = $("taskList");
  container.innerHTML = "";
  if (!tasks.length) {
    container.textContent = "No study goals yet. Add one above to begin.";
    container.className = "muted";
    return;
  }
  container.className = "";
  tasks.forEach((task, index) => {
    const row = document.createElement("div");
    row.className = "task";
    const checkbox = document.createElement("input");
    checkbox.type = "checkbox";
    checkbox.checked = !!task.done;
    checkbox.setAttribute("aria-label", "Mark task complete");
    checkbox.addEventListener("change", () => {
      tasks[index].done = checkbox.checked;
      saveTasks();
    });
    const label = document.createElement("span");
    label.style.flex = "1";
    label.style.textDecoration = task.done ? "line-through" : "none";
    label.textContent = task.title + " · " + task.minutes + " min";
    const remove = document.createElement("button");
    remove.textContent = "×";
    remove.title = "Remove task";
    remove.addEventListener("click", () => { tasks.splice(index, 1); saveTasks(); });
    row.append(checkbox, label, remove);
    container.appendChild(row);
  });
}
$("addTaskBtn").addEventListener("click", () => {
  const title = $("taskInput").value.trim();
  if (!title) { $("taskInput").focus(); return; }
  tasks.push({ title, minutes: $("taskMinutes").value, done: false });
  $("taskInput").value = "";
  saveTasks();
});
$("taskInput").addEventListener("keydown", e => {
  if (e.key === "Enter") { e.preventDefault(); $("addTaskBtn").click(); }
});
$("clearTasksBtn").addEventListener("click", () => {
  tasks = [];
  saveTasks();
});

// ===== LOCAL PROGRESS =====
$("resetProgressBtn").addEventListener("click", () => {
  messagesSent = 0;
  topics = [];
  quizRequests = 0;
  persistProgress();
});
$("themeBtn").addEventListener("click", () => {
  document.body.classList.toggle("light");
  const light = document.body.classList.contains("light");
  $("themeBtn").textContent = light ? "🌙" : "☀️";
  try { localStorage.setItem("vidyaverse_theme", light ? "light" : "dark"); } catch (e) {}
});

// ===== SPEECH INPUT =====
(function setupSpeech() {
  const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
  if (!SpeechRecognition) return;
  $("micBtn").classList.remove("hidden");
  recognition = new SpeechRecognition();
  recognition.lang = "en-IN";
  recognition.interimResults = false;
  recognition.maxAlternatives = 1;
  $("micBtn").addEventListener("click", () => {
    try {
      recognition.lang = $("languageSelect").value === "Hindi" ? "hi-IN" : "en-IN";
      recognition.start();
      setStatus("Listening...");
    } catch (e) { setStatus("Microphone is already active or unavailable.", true); }
  });
  recognition.onresult = event => {
    const transcript = event.results[0][0].transcript;
    $("messageInput").value = ($("messageInput").value + " " + transcript).trim();
    $("messageInput").focus();
    setStatus("Speech captured. Press Send when ready.");
  };
  recognition.onerror = event => setStatus("Speech input error: " + event.error, true);
  recognition.onend = () => {
    if (!busy) setStatus("Ready to learn");
  };
})();

// ===== THEME, STARTUP AND RESTORE =====
loadPrefs();
const savedTheme = safeLoad("vidyaverse_theme", "dark");
if (savedTheme === "light") {
  document.body.classList.add("light");
  $("themeBtn").textContent = "🌙";
}
const savedHistory = safeLoad(STORAGE_KEY, []);
history = Array.isArray(savedHistory)
  ? savedHistory.filter(m => m && (m.role === "user" || m.role === "assistant") && typeof m.text === "string")
  : [];
const progress = safeLoad(PROGRESS_KEY, {});
messagesSent = Number(progress.messagesSent) || 0;
topics = Array.isArray(progress.topics) ? progress.topics.filter(t => typeof t === "string") : [];
quizRequests = Number(progress.quizRequests) || 0;
tasks = safeLoad(TASK_KEY, []);
if (!Array.isArray(tasks)) tasks = [];
renderHistory();
renderTasks();
updateProgress();
</script>
</body>
</html>
