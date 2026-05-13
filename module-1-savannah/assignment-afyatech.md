# Assignment — The Precision Prompting Challenge
### AfyaTech Maternal Health SMS Assistant
**By Naomi Meseret | Module 1 — The Savannah Adventure**

---

## INTRODUCTION

In maternal health, a wrong AI response is not just unhelpful — it can delay urgent care, increase medical risk, and put both the mother and baby in danger. Precision prompting matters because the quality, safety, and relevance of an AI response depend heavily on the clarity of the instructions and context provided. In rural Kenya and Uganda, generic AI advice fails because healthcare access, transportation, language, cultural practices, and resource availability differ greatly from the assumptions built into many global AI systems.

---

## PROMPT A — Nutrition Advice

**Original prompt:** *"Give nutrition tips for pregnant women."*

**Problem:** Generates Western-centric advice assuming supermarket access, refrigeration, and purchasing power irrelevant to rural East African realities.

---

**REWRITTEN PROMPT — AIM Framework:**

- **A — Actor:** You are a maternal nutrition specialist with 10 years experience serving rural communities in Kenya and Uganda

- **I — Input:** Target users are pregnant women in rural Western Kenya and Eastern Uganda. Primary food staples are matooke, ugali, sweet potatoes, and beans. Average daily income is under $2. 70% have no refrigeration. Iron deficiency anaemia affects 45% of rural pregnant women in Uganda per WHO 2023 data

- **M — Mission:** Generate trimester-specific nutrition advice using only locally available, affordable foods. For each trimester provide 3 practical meal suggestions, flag dangerous food combinations common in this region, and keep language SMS-friendly — under 160 characters per tip

---

**MAP Framework:**

- **M — Memory:** User is in second trimester and previously received advice about iron deficiency

- **A — Assets:** WHO maternal nutrition guidelines for East Africa, local market price data, community health worker field reports

- **P — Prompt/Actions:** Deliver via SMS. If user replies "no matooke" automatically trigger alternative ugali-based suggestions

---

**Key Improvement:** Eliminates hallucination of Western dietary advice by anchoring AI in real local food staples, economic constraints, and delivery format. Reduces risk of harmful or irrelevant nutritional guidance.

---

## PROMPT B — Appointment Reminders

**Original prompt:** *"Remind users about doctor visits."*

**Problem:** Assumes smartphone access, proximity to clinics, and flexible scheduling — ignoring rural travel distances, limited clinic days, and connectivity blackouts.

---

**REWRITTEN PROMPT — AIM Framework:**

- **A — Actor:** You are a community health communication specialist working with rural maternal health programs in Western Kenya and Eastern Uganda

- **I — Input:** Target user is a pregnant woman in her third trimester in rural Siaya County, Kenya. Key constraints:
  - Lives approximately 7km from nearest clinic
  - Travels by foot or boda boda
  - Clinic operates Tuesday and Thursday only, 8am–1pm
  - Assigned Community Health Worker visits every Monday morning
  - Daily 4-hour connectivity blackout occurs between 6am–10am

- **M — Mission:** Generate an SMS reminder telling her exactly when to leave home, accounting for boda boda availability, road conditions during long rains season, and CHW confirmation. Under 160 characters. If appointment conflicts with clinic closure, suggest next available Thursday slot automatically

---

**MAP Framework:**

- **M — Memory:** She missed her last appointment due to an unannounced public holiday closure. She has been reminded twice already about this appointment

- **A — Assets:** Kenya public holiday calendar 2025, Siaya County clinic schedule, boda boda availability data, April–May rainfall pattern data

- **P — Prompt/Actions:** Send SMS reminder 48 hours before appointment. If no confirmation within 24 hours trigger CHW phone call. If connectivity blackout detected delay SMS until 10am when network restores

---

**Key Improvement:** Moves from passive generic reminder to context-aware, actionable communication that accounts for real infrastructure constraints — dramatically reducing missed appointments due to preventable logistical failures.

---

## PROMPT C — Emergency Triage

**Original prompt:** *"Tell me what to do if I feel unwell during pregnancy."*

**Problem:** AI answers immediately with assumptions, potentially overwhelming a frightened woman with irrelevant or dangerous information without knowing her actual situation.

---

**REWRITTEN PROMPT — Chain of Thought + Verifier Pattern:**

**Verifier Pattern — Ask first, answer second:**

Before providing any health advice, ask the user these clarifying questions one at a time via SMS:

- **Question 1:** "How many weeks pregnant are you?" — determines which conditions are most likely by trimester
- **Question 2:** "Where does it hurt or what exactly do you feel?" — headache, swelling, and blurred vision together signal pre-eclampsia emergency
- **Question 3:** "Is your Community Health Worker reachable right now?" — determines what immediate human support is available

Do not proceed to advice until all three questions are answered.

---

**Chain of Thought — Reason before responding:**

After receiving answers, think through the situation step by step:

- **Step 1:** Identify what information is still missing before assessing severity
- **Step 2:** Consider the three most dangerous conditions for third trimester pregnancies in rural East Africa — pre-eclampsia, malaria, obstetric emergency
- **Step 3:** For each condition identify which reported symptoms confirm or rule it out
- **Step 4:** Assess what local resources are available at this hour — CHW, clinic, nearest hospital, M-Pesa for emergency transport
- **Step 5:** Only after completing steps 1–4, formulate a calm, clear, actionable response under 160 characters that does not cause panic

---

**Key Improvement:** Eliminates dangerous assumptions by forcing AI to gather critical information before responding. Slows down the interaction deliberately — because in emergency maternal triage, a wrong fast answer is far more dangerous than a careful slow one.

---

## REFLECTION

Before this exercise, I thought AI in healthcare meant mostly advanced machines and automated diagnosis systems used in hospitals. What surprised me most was how much the quality of AI responses depends on context, local realities, and the way questions are asked. Now I understand that AI's real role in healthcare is not to replace human judgment but to support healthcare workers with faster insights, better organization, and more informed decision-making. This changes how I will approach every AI prompt going forward — not as a casual question, but as a precise instruction with real consequences.

---

