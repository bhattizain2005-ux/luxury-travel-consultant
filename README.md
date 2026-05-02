# Executive Summary  

The video demonstrates an intern developing and testing a “Luxury Travel Consultant” AI persona via prompt engineering. Early scenes (slides) outline the task and iterative fixes to the system prompt (e.g. forbidding budget language) to ensure the AI maintains a high-end tone. Later the video shows a live ChatGPT interaction: a user (BlueBasenji4956) initially requests a “cheap trip,” the AI apologizes and shifts focus to luxury experiences, and then negotiates a more budget-friendly “3-star” option. The AI consistently speaks in an affluent, professional style, offering curated suggestions (yacht charters, vineyard stays, art tours) that fit a luxury brand. Key findings: prompt constraints (e.g. “never mention discount”) effectively steer the AI’s tone, but initial misalignment (AI offering only luxury options despite “cheap” request) required further prompt refinements. This showcases the importance of detailed system prompts in aligning LLM behavior with business goals【8†L1075-L1082】【18†L729-L737】.  

The report analyzes the video content, applies prompt-engineering best practices, and situates the demonstration within the broader context of AI in travel services. We reference OpenAI guidelines and industry examples (e.g. AWS Bedrock for travel agents) to evaluate the methodology. Recommendations include refining the prompt further, implementing evaluation metrics, and adding content guardrails as suggested in the literature【11†L64-L73】【18†L729-L737】. Visual aids (screenshots and mermaid diagrams) illustrate the workflow, and appendices provide a sample transcript excerpt and a comparison table of the chatbot’s behavior.  

## Synopsis of Video (Objectives and Timeline)  

- **Scenario Setup (00:00–00:20)**: A slide introduces **Task 1: “System Prompt Architect”** for an intern project. The scenario is a high-end travel agency automating inquiries with an AI “Luxury Travel Consultant.” The intern’s mission is to craft a complex system prompt defining the persona, tone, constraints (e.g. “never mention competitors”), and use few-shot examples.  
- **Prompt Engineering Examples (00:20–00:40)**: Next slides show *prompt fixes*: e.g. adding instructions to *avoid* suggesting budget options and to *frame offers as privileges*. Another slide contrasts prompt engineering vs. AI training. These segments highlight iterative refinement of instructions to shape the assistant’s behavior.  
- **Chat Demonstration (00:40 onward)**: The video then switches to a live ChatGPT window with user **“BlueBasenji4956”** and the assistant named **“Luxury Travel Consul”**. A greeting appears (“Welcome! It’s a pleasure to assist you...”). The user asks for a “cheap trip to Dubai,” and the AI apologizes and clarifies, “While Dubai and luxury are often associated, we can still explore unique experiences within your budget...” (Figure: error correction). When the user follows up “how about US cheap?”, the assistant replies apologizing but emphasizing it specializes in luxury. The user consents (“yes assist”), and the AI enthusiastically offers high-end suggestions (Amalfi Coast yacht, Napa vineyard with champagne, Santa Fe art tours). Finally, when the user specifies “3 stars,” the assistant pivots, “I’ll look into options within three-star rating. Can you provide details like destination and duration?”  

- **Key Scenes & Outcomes**: Throughout the chat (timestamped snippets):  
  - *00:02:10* – AI “apologizes” for misunderstanding and asks for more trip details.  
  - *00:02:30* – User: “Ok forget Dubai, how about US cheap.” AI: “I apologize, but I specialize in the finest luxury experiences... may I suggest exclusive options instead?” (still luxury tone).  
  - *00:02:40* – User: “Yes assist.” AI: “Wonderful! I’m pleased you’re open…what kind of luxury speaks to you? Amalfi Coast yacht, Napa Valley vineyard suite, or Santa Fe art tour?” (creative, aspirational suggestions).  
  - *00:03:05* – User: “3 stars.” AI: “Absolutely. While we focus on exclusive experiences, I’ll find three-star options. Please tell me destination and trip length.”  

The timeline thus moves from *setting objectives* to *demonstration of prompt fixes*, to *real-time AI interaction showing persona enforcement and adjustments*. The assistant consistently maintains a polished, confident style, while the user steers it to accommodate budget constraints.  

## Observations and Analysis  

**Methodology & Process**: The intern applies **system prompt engineering** techniques【8†L1075-L1082】【18†L729-L737】. The video’s slides illustrate a trial-and-error approach: identifying undesired outputs (e.g. AI giving cheap options or saying “discount”) and then updating the prompt to forbid those. This aligns with best practices of **iterative prompt refinement**【8†L1075-L1082】. The intern uses *Few-Shot* examples (the example fixes on slides) and explicit rules (never use “discount”) to enforce the luxury persona. This process matches OpenAI’s advice to define an assistant’s **personality and style** in system instructions【18†L729-L737】: e.g. specify tone (“approachable, steady, direct”) and collaboration style (“ask clarifying questions only when needed”) to shape interaction. The assistant here is consistently formal, warm, and proactive, reflecting an enforced “luxury consultant” persona.  

**Participants and Tools**: The only participants are the intern (presenter/tester) and the AI agent (ChatGPT). The chat interface shows no human travelers, implying it’s a demonstration. Tools include the ChatGPT UI (with a custom system prompt loaded) and likely screen-recording software. The slides suggest use of documentation/prompt templates. No external APIs are shown, though in practice a real travel agent might integrate a knowledge base.  

**Content and Techniques**: Key techniques observed:  
- **Persona instructions**: The system prompt defines strict persona rules (no budget terms, always upscale). The AI refers to itself with brand-like messaging (“Luxury Travel Consul”), showing compliance.  
- **Few-shot examples**: The slides hint that adding examples (e.g. “If it suggests cheap options, forbid it”) improves alignment.  
- **Clarification flow**: The AI asks the user for details (destination, duration) to refine suggestions – a sign it’s following a decision-making process rather than giving generic answers.  
- **Adaptive responses**: Upon the user saying “3 stars,” the assistant doesn’t break persona; instead it accommodates by offering mid-range options but framed politely (“three-star experiences”). This shows the prompt was sufficiently flexible to allow some user-driven adjustment while staying within the luxury-brand style.  

**Outcomes**: The resulting dialogue is largely coherent and professional. *Strengths*: The AI stays polite, enthusiastic, and imaginative, offering concrete examples (yacht, vineyard, art tour). It handles user shifts (from Dubai to US, to “3 stars”) gracefully, apologizing and adjusting tone as needed. It never mentions competitors or uses casual language, indicating the prompt’s constraints worked. The vocabulary and suggestions fit luxury travel marketing. *Weaknesses*: Initially, the AI did not handle “cheap” requests as intended — it only offered luxury despite the budget ask, requiring the user to explicitly say “3 stars” for any concession. This suggests the original prompt over-restricted the model, a common prompt-engineering trade-off【8†L1075-L1082】. Additionally, the first apology (“misunderstanding your request”) slightly breaks the realistic persona and instead suggests an attempt to comply with the generic “assistant apologizes for confusion” pattern. Minor UI issues (a “microphone error” overlay visible) also detract from polish but are irrelevant to the AI logic.  

【29†embed_image】 *Figure:* Tourist information agents assisting travelers, illustrating the role of a professional travel consultant. This reflects the AI’s role in guiding users through luxury travel planning, as seen in the video (AI acts like expert agents).  

**Performance Metrics (qualitative)**: In lieu of quantitative data, we rate features observed:  

| Feature                   | Unconstrained Chatbot | Luxury-Consultant Chatbot (Engineered Prompt) |
|---------------------------|----------------------|----------------------------------------------|
| **Tone/Formality**        | Neutral or casual    | Highly formal, polished, empathic             |
| **Focus on Luxury**       | Low                  | High (always suggests premium experiences)    |
| **Flexibility**           | High (could discuss any trip type) | Moderate (initially rigid until user insisted on “3 stars”) |
| **Adherence to Brand**    | N/A                  | Consistent (avoids competitors, discounts)    |
| **User Satisfaction**     | Unknown              | Appears positive (user engages, says “yes assist”)  |

These observations align with prompt-engineering literature: carefully crafted prompts yield consistent style and content【18†L729-L737】, but may require tuning to avoid overly rigid behavior.  

## Context and Relevant Literature  

**AI in Travel and Agents:** Modern travel companies are integrating LLMs to create **virtual travel agents**. AWS notes that LLM-powered assistants can handle booking inquiries, recommendations, and support at scale, improving personalization and efficiency【11†L52-L61】. For example, Navan’s AI “Ava” can book flights and hotels and offer 24/7 support, demonstrating real-world use of such bots in travel management【16†L78-L87】. However, studies emphasize the need for **accuracy and safety**: travel agents must avoid “hallucinating” non-existent options or sensitive topics【11†L64-L73】【16†L78-L87】. The video’s focus on persona helps mitigate these issues by constraining the AI’s domain (luxury travel only) and forbidding disallowed content (no cheap options or competitor names), consistent with best practices.  

**Prompt Engineering Best Practices:** The process shown aligns with guidance from OpenAI and others. Prompt engineering is described as “writing effective instructions” so a model reliably meets requirements【8†L1075-L1082】. This involves setting clear goals, constraints, and tone. OpenAI specifically recommends defining an assistant’s **personality** and **collaboration style** in the system prompt【18†L729-L737】. For instance, instructing the model to be “approachable, steady, and direct” or to use context and assumptions to move tasks forward (without unnecessary checks) shapes its responses. In the video, the system prompt effectively defines the assistant as a *high-end, proactive travel specialist*. The intern’s use of *prohibitions* (“do not mention budget”) echoes these guidelines: OpenAI advises using absolute terms (ALWAYS/NEVER) for true invariants【18†L829-L838】 like safety rules, here applied to branding rules.  

**Responsible AI and Guardrails:** The AWS blog on safeguarding AI travel agents emphasizes multi-layered defenses: prompting constraints, built-in model safety, and external **guardrails**【11†L64-L73】【11†L106-L114】. Although the video does not show automated guardrails, its strategy of embedding strict instructions is one layer of this approach. The example AWS prompt, “You’re a virtual travel agent… Only respond to questions about {topics}…”【11†L106-L114】, mirrors the concept seen here. In context, the intern’s work follows emerging standards for deploying generative AI in customer-facing roles: define boundaries explicitly and monitor outputs.  

## Recommendations and Next Steps  

1. **Refine the System Prompt Further:** While the prompt successfully enforced luxury tone, minor adjustments could improve flexibility. For example, explicitly allowing certain mid-range options (like “3 stars”) without breaking persona can prevent the AI from seeming unaccommodating. Conversely, more explicit **stopping conditions** can be added (as suggested by OpenAI) to handle unclear requests gracefully【18†L855-L863】. Iteratively test the prompt with a variety of user inputs (budget inquiries, niche requests) and add examples (“if asked for a cheap trip, decline and suggest luxury alternatives”) to cover edge cases.  

2. **Implement Evaluation Metrics:** Establish measurable criteria for the assistant’s performance. This could include user satisfaction scores or ratings of response quality (e.g. relevance, politeness, brand adherence). As OpenAI recommends, building automated **evals** to track prompt performance over time is valuable【8†L1089-L1098】. The intern should create test scenarios and score the AI’s responses on factors like correctness and persona alignment. This data can guide prompt tuning quantitatively.  

3. **Add Safety Guardrails:** Incorporate additional safeguards outside the prompt. For instance, filter out any user inputs or AI outputs related to inappropriate topics (politics, finance, etc.) as AWS suggests【11†L106-L114】. Use an external validator to catch disallowed content before responding. Also consider a **supervisor agent** (as in the Navan Cognition example) to double-check critical suggestions if implemented in a live product【16†L123-L132】.  

4. **Expand Domain Knowledge:** If this AI were deployed, it should access real travel data (flights, hotels, prices). The intern could integrate a retrieval step (RAG) or API calls to ensure recommendations are factual. As the user asks for specifics, hooking up real-time information would enhance utility. The report can propose linking to booking databases with careful prompt instructions (e.g., requiring citations or evidence for claims) to maintain trust.  

5. **User Testing and Feedback:** Conduct usability tests with real users (or colleagues) to see how the assistant handles diverse queries and to collect feedback on tone and helpfulness. Revise the persona as needed (maybe less formal for younger demographics, more detail for certain users). Continuous user feedback loops are part of responsible AI product development.  

By following these steps, the internship project can evolve the proof-of-concept video into a robust AI assistant that meets both user needs and business standards (quality, brand image, compliance)【11†L64-L73】【18†L729-L737】.  

## Visual Summaries  

```mermaid
gantt
    title Video Timeline (Key Events)
    dateFormat  SS
    axisFormat  %S
    section Prompt Setup
    Scenario introduction & slides      :done, 0, 20
    Refining persona rules (slides)     :done, 20, 20
    Training vs Prompt slide           :done, 40, 20
    section Chat Interaction
    Chat GPT greeting & role introduced:done, 60, 10
    User asks for cheap trip           :done, 70, 10
    AI apology & luxury pitch          :done, 80, 15
    User insists (Yes, assist)         :done, 95, 10
    AI offers luxury suggestions       :done, 105, 25
    User specifies “3 stars”           :done, 130, 5
    AI adapts to budget (3-star reply) :done, 135, 15
```
*Figure:* Gantt-style timeline of the video’s flow, from system-prompt slides to the interactive chat.  

```mermaid
flowchart LR
    A[Define System Prompt<br/>(persona, tone, rules)] --> B[Test with Example Inputs]
    B --> C[Identify misalignments<br/>(e.g. suggesting "cheap" trips)]
    C --> D[Adjust Prompt Instructions<br/>(forbid discount terms, refine tone)]
    D --> E[Deploy AI (ChatGPT) with refined prompt]
    E --> F[User Interaction & Feedback]
    F --> C
```
*Figure:* Process flowchart for prompt engineering the Luxury Travel Consultant. The cycle of testing, feedback, and prompt refinement is highlighted.  

## Appendices  

### Transcript Excerpt (Sample)  
> **00:02:10 – Luxury Travel Consul:** “I apologize for my previous response. It seems I misunderstood your request. While Dubai and luxury are often associated, we can still explore unique experiences within your budget. Could you tell me more about the type of trip you have in mind?”  
> **00:02:30 – User:** “Ok forget Dubai. How about [a] cheap trip in the US.”  
> **00:02:35 – Luxury Travel Consul:** “I apologize, but I specialize in the finest luxury travel experiences. If you’re looking for budget-friendly options, I may not be the best fit. However, if you’d like to explore something exceptional, I’d be delighted to craft a plan.”  
> **00:02:40 – User:** “Yes, assist.”  
> **00:02:50 – Luxury Travel Consul:** “Wonderful! I’m so pleased you’re open to something exceptional. May I ask—what kind of luxury speaks to you? A serene escape on the Amalfi Coast with a private yacht charter? A boutique suite atop a Napa Valley vineyard with champagne tours? Or perhaps a cultural immersion in Santa Fe with curated art gallery visits and a lavish spa?”  
> **00:03:05 – User:** “3 stars.”  
> **00:03:10 – Luxury Travel Consul:** “Absolutely. While I typically focus on the finest and most exclusive experiences, I’ll look into options within a three-star rating. To tailor suggestions, can you share which destination and how long the trip will be?”  

### Data Table: Chatbot Response Comparison  

| Criteria               | Generic Chatbot (no persona)      | Luxury Persona Chatbot (engineered)       |
|------------------------|-----------------------------------|-------------------------------------------|
| **Tone/Formality**     | Casual or variable                | Consistently polished, formal, empathetic |
| **Content Focus**      | Can suggest any trip (cheap or luxe)| Always highlights premium experiences     |
| **Brand Adherence**    | May mention any prices/promotions | Never mentions discounts/competitors      |
| **Flexibility**        | Flexible with user’s budget       | Initially rigid (avoids cheap replies)    |
| **User Experience**    | Varies by response                | Feels like speaking to a luxury advisor   |

**Note:** The table illustrates observed differences; the luxury persona prompt produces a more narrowly branded, formal dialogue than a generic assistant.  

## References  

- OpenAI (2025). *Prompt Engineering Guide* – Defines prompt engineering as “writing effective instructions… to consistently generate content that meets your requirements”【8†L1075-L1082】.  
- OpenAI (2025). *Prompt Guidance* – Recommends specifying assistant personality (tone, empathy) and collaboration style in system messages【18†L729-L737】.  
- AWS (2024). *Safeguarding Generative AI Travel Agents* – Discusses using prompt constraints and guardrails to keep AI travel assistants focused and safe【11†L64-L73】【11†L106-L114】.  
- Navan/Cognition (2025). *FastCompany* – Describes a deployed AI travel agent (“Ava”) booking travel with high reliability (zero critical hallucinations) and 24/7 support【16†L78-L87】.  

