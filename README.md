# 🧠 AI Debate Arena

A multi-agent debate system powered by LangGraph. This project simulates structured debates between AI agents (and optionally human participants) on various topics. Each debate is judged round-by-round by an AI judge agent, and agents can perform web research to strengthen their arguments.

---

## 🎯 Project Goals

- Simulate structured debates between AI agents with distinct personas
- Enable web-based research for informed arguments
- Allow human users to join or moderate the debate
- Score debates round-by-round with a judge agent
- Support a fixed round-based structure (Opening → Rebuttal → Conclusion)
- Eventually support unstructured, moderator-led debates

---

## 🏛️ Formal Debate Format (MVP)

The debate consists of three main rounds:
1. **Opening Statements** – Each side presents their primary arguments.
2. **Rebuttals** – Each side responds to and critiques the opponent's opening.
3. **Closing Statements** – Each side summarizes and solidifies their position.

Planned Extension:
- **Cross-Examination** (future): Agents engage in a Q&A-style exchange, alternating questions and answers for deeper analysis and challenge.

After each round:
- The **Judge Agent** evaluates arguments
- Scores and feedback are given, shaping the overall debate outcome

---

## 🤖 Agents

### Debater Agents
- Argue either the **Pro** or **Con** position
- Have access to:
  - The current debate topic
  - Past turns and memory
  - Web tools for research (e.g., search APIs)

### Judge Agent
- Evaluates each round for clarity, logic, and persuasiveness
- Assigns a winner for each round and provides rationale

### (Optional) Human Participant
- Users can join the debate or vote as a judge

### (Future) Moderator Agent
- Keeps the debate on track and maintains flow
- Detects stagnation, suggests subtopics or rephrases questions
- Tracks unanswered or overlooked questions to prompt follow-up

---

## 🧩 LangGraph Architecture

```text
[DebateSetupNode]
     ↓
[OpeningStatements]
     ↓
[Rebuttals]
     ↓
[Conclusions]
     ↓
[FinalScoringNode]
