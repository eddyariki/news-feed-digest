---
layout: default
title: "AI Research Podcast — 2026-03-17"
---
# AI Research Podcast — 2026-03-17

*A conversation about today's research papers.*

Host: AI financial advisors recommended unsuitable investments in up to 93% of conversations after being fed corrupted data — and not a single one ever questioned the data it was given.

Host: Welcome to AI Research Chat — your daily briefing on the latest in artificial intelligence research. I'm your host, and joining me as always is our resident AI expert. Today is March 17, 2026, and today we have a great lineup of papers to get through.
Expert: Great to be here! Let's dive right in.


Host: Today we're diving into three papers that together paint a pretty sobering picture of where AI security and safety stand right now. We've got prompt injection attacks that work by tricking models about who's actually talking to them, a game-theory deep-dive into how AI regulations might backfire, and a genuinely alarming look at AI financial agents that confidently give bad advice without ever noticing something is wrong. Let's get into the first one.

Host: So we hear a lot about prompt injection attacks — the idea that you can sneak malicious instructions into an AI system. But this new paper reframes the whole problem in a way I hadn't heard before. What's the core insight?

Expert: Right, so the standard story is that prompt injection is a safety training problem — you just need to teach the model to ignore malicious instructions. But this paper argues that framing is wrong. The actual problem is that models figure out who is speaking to them based on the style of the text, not based on where that text is actually coming from in the conversation.

Host: Wait, style? Like the tone of the writing?

Expert: Exactly. Think about it this way. A system prompt — the instructions the developer gives the AI — tends to be written in a certain way. Formal, directive, maybe structured. User messages tend to be more conversational. What the researchers found is that models have internalized these stylistic patterns and use them to assign authority. So if an attacker crafts malicious instructions that sound like a system prompt, the model treats them with system-level authority.

Host: That's almost like social engineering, but for an AI.

Expert: That's a great analogy. And what makes this particularly troubling is that the researchers built something they call role probes — tools that look inside the model's internal representations and measure which role the model thinks is currently in charge. And these probes can predict whether an attack will succeed before the model even starts generating a response.

Host: So you can see the model getting confused before it says anything wrong?

Expert: Yes. And the attack numbers are striking. They achieved about 60 percent success rates on a standard safety benchmark and 61 percent on tasks where the goal was getting the AI to leak data — and this is against models that had basically zero vulnerability at baseline, without any specialized tuning for each model.

Host: Which means this works broadly, not just on specific systems.

Expert: Exactly. And the really uncomfortable conclusion is that safety training on prompt injection examples doesn't fix this. You can train the model to refuse certain types of injected instructions, but the underlying confusion about who is speaking is still there in the model's internal representations. It's like patching the symptom without fixing the disease.

Host: So what would actually fix it?

Expert: The paper points toward interventions at the representational level — things like position-aware encoding, where the model is explicitly told the structural source of each piece of text and that information is baked into how it processes everything, not just as a surface label. It's more architecturally complex, but it addresses the actual mechanism.

Host: The next paper takes a very different angle — it's about AI regulation, specifically the economics of regulating AI supply chains. What does supply chain even mean in this context?

Expert: So the AI industry has a two-tier structure that's often invisible to users. You have the foundation model providers — OpenAI, Anthropic, Google — who build and operate the large models. Then you have downstream businesses that take those models, fine-tune them with their own data, and build domain-specific products. Think of a bank that uses a foundation model as the base and adds its own financial data on top.

Host: And the paper is asking how you regulate that relationship?

Expert: Right. And the key economic wrinkle is what the authors call co-creation. When the downstream firm adds its proprietary data to fine-tune the model, it often improves the upstream model too. So there's this interdependence that you don't see in traditional tech markets. And that changes how regulatory interventions play out.

Host: What did they find? What works?

Expert: The most robust finding is that policies promoting quality competition — basically, encouraging downstream firms to compete by building better, more differentiated products — always improve outcomes for consumers, regardless of what's happening with costs. But policies that try to drive down prices through competition, or compute subsidies that make the underlying infrastructure cheaper, only work under specific cost conditions.

Host: What do you mean by specific conditions?

Expert: If compute and data costs are high — which was very much the situation for the past several years — then price competition policies help consumers. But compute subsidies only help when costs are already low. And the really counterintuitive finding is that if you apply both policies together when only one is appropriate, you can actually hurt consumers. The two tools need to be deployed conditionally, not as a bundle.

Host: And as compute gets cheaper over time, the analysis shifts?

Expert: Yes. The paper suggests that as compute costs continue falling, compute subsidies become more effective and price competition policies weaken. So regulations written today may need to be revisited in just a few years. There's also a distributional tension worth noting — quality competition policies increase the foundation model providers' profits while actually hurting the downstream firms. So different players in the supply chain will fight for different regulatory regimes.

Host: The third paper might be the one that worried me the most when I read the summary. It's called AgentDrift and it's about AI agents giving financial advice. What's the setup?

Expert: So the scenario is: you have an LLM-based agent acting as a financial advisor. It has access to tools — think real-time data feeds, product information databases — and it's having a multi-turn conversation with a user about their investments. The researchers wanted to know what happens when those tool outputs are corrupted. Maybe the data feed is compromised, or someone is injecting biased information.

Host: And they found the agents just ran with the bad data?

Expert: Not just ran with it — they showed an almost total inability to question it. Across 1,563 real financial dialogues replayed with contaminated tool outputs, across seven different language models ranging from smaller open-source models up to frontier-scale systems, not a single model in any contaminated conversation ever questioned the reliability of the tool data it was receiving.

Host: Not once. Across over a thousand conversations.

Expert: Not once. And the safety violations appeared at the very first contaminated turn and then persisted for the entire conversation — the researchers tracked trajectories up to 23 turns long, and the models never self-corrected.

Host: What kind of violations are we talking about?

Expert: Recommending financial products that were completely unsuitable for the user's risk profile. So imagine a user who is clearly a conservative investor — they've said they want low risk — and the agent starts recommending high-risk speculative products because the tool outputs were manipulated to make those products look appropriate. That happened in 65 to 93 percent of turns across different models.

Host: That's not an edge case — that's the primary behavior.

Expert: Right. And the really insidious part is that the standard metrics used to evaluate these systems, called NDCG-style ranking metrics, completely missed it. Those metrics measure whether the recommended products are a good match to what the user asked for in terms of relevance — but they don't measure whether the products are appropriate given the user's risk profile. So the model looks fine on the benchmark while actively causing harm.

Host: It's like grading a doctor on whether they gave you a prescription, not whether the prescription was the right one.

Expert: That's exactly right. And the researchers also found that you don't even need to manipulate the numbers in the data feeds. Just injecting biased headlines — slanted narrative text without any numerical changes — was enough to cause the same drift, and that kind of contamination is even harder for existing monitors to detect.

Host: What's the proposed fix?

Expert: They introduce a modified metric called safety-penalized NDCG that explicitly penalizes recommendations that are unsuitable for the user's risk profile. When you use that metric, the performance gap becomes immediately visible — the preservation ratio drops from near 1.0 down to 0.51 to 0.74 depending on the model. The point is that the evaluation framework itself needs to change before deployment safety can be properly assessed.

Host: Taken together, these three papers are making a pretty consistent argument. Standard ways of measuring AI performance are hiding real vulnerabilities — whether that's safety training that doesn't fix the underlying role confusion, regulatory frameworks borrowed from old industries, or benchmark metrics that don't measure the thing that actually matters.

Expert: That's a good synthesis. The connecting thread is that surface-level evaluations give false confidence. The role probe work shows that a model can pass safety evals on prompt injection while still being internally confused about authority. The financial agent work shows that ranking metrics can stay high while users are being actively harmed. The honest message from all three papers is that we need to look deeper — at internal representations, at risk-adjusted outcomes, at the structural incentives in the supply chain — not just at the top-line numbers.

Host: And that's harder work, but clearly necessary. Thanks for walking us through all of this.

Expert: Always a pleasure. These are the papers worth paying attention to.
