---
layout: default
title: "AI Research Podcast — 2026-03-13"
---
# AI Research Podcast — 2026-03-13

*A conversation about today's research papers.*

Host: A medical AI sounded completely credible nearly one hundred percent of the time while quietly getting the facts wrong one in five times — and patients had no way to know.

Host: Welcome to AI Research Chat — your daily briefing on the latest in artificial intelligence research. I'm your host, and joining me as always is our resident AI expert. Today is March 13, 2026, and today we have a great lineup of papers to get through.
Expert: Great to be here! Let's dive right in.


Host: Today we have three papers that are all, in different ways, about the gap between what AI appears to be doing and what it is actually doing. Medical answers that sound authoritative but aren't, military AI systems that refuse to help at all, and a wave of users convinced their chatbot lost its soul — turns out the data tells a very different story. Let's start with the medical one because honestly it shook me a bit.
Expert: It should shake you. The core finding is that LLaMA-70B-Instruct hallucinated in about 19.7% of its answers on medical textbook questions. That's roughly one in five. But here's the part that matters: 98.8% of those responses scored maximum plausibility scores from human raters.
Host: Wait, so it sounded maximally convincing while being factually wrong nearly a fifth of the time.
Expert: Exactly. There's no tell. The confident tone, the structure, the clinical vocabulary — all of it looks the same whether the model is right or completely fabricating. And the reason this study is more useful than most is that they grounded it in fixed textbook sources, not internet facts that might have changed. So they could actually pin down what hallucination rate looks like against known ground truth.
Host: How does that compare to other benchmarks? Is 20% typical?
Expert: It's on the higher end for a capable model, but the alarming part isn't the absolute number — it's the calibration failure. The model has no idea when it's wrong. And the paper found that lower hallucination rates predicted higher clinician usefulness scores with a pretty strong correlation. So this isn't just an academic metric. Getting hallucinations down is directly tied to whether doctors actually find these tools useful.
Host: The implication for anyone deploying AI in a clinical setting seems pretty stark — you need source-grounded retrieval, not just a raw model.
Expert: That's the practical takeaway. A model generating from memory in a medical context is dangerous not because it sounds bad, but precisely because it sounds so good.
Host: Alright, let's go to paper two which takes this idea of AI not working as expected in high-stakes situations and flips it completely. Instead of wrong answers, you get no answers at all.
Expert: Right, this is the military refusal paper. General-purpose models are trained to avoid anything touching violence, weapons, or military operations. Which makes sense for a consumer chatbot. But if you're deploying AI in a defense context, those are exactly the questions you need answered.
Host: How bad is it?
Expert: Some models refused over 98% of military-domain queries outright. Not hedged answers, not partial responses — hard refusals. And the researchers make the point that in a time-critical tactical situation, a refusal is a mission failure. It's not a cautious outcome, it's a broken tool.
Host: I have to be honest, part of me thinks that's the safety training doing exactly what it's supposed to do. The discomfort here is deliberate, isn't it?
Expert: That's the real tension this paper surfaces. The authors aren't arguing that safety is bad. They're arguing that safety training designed for a general consumer product is the wrong shape for a specialized deployment. The answer isn't to remove guardrails, it's to train for the domain from the start.
Host: They tested a technique called abliteration — what did that show?
Expert: Abliteration tries to surgically remove the refusal behavior from model weights. It did improve the answer rate by about 66 percentage points, which is dramatic. But it caused a 2% regression on other military tasks. So it's a blunt instrument. It fixes one problem by slightly breaking others. The authors are pushing for deeper mid-training specialization rather than post-hoc weight surgery.
Host: The practical message for developers building domain-specific tools seems to be: don't start with a general-purpose safety-trained model and try to patch it. Start earlier in the training pipeline.
Expert: Yes, and that's a harder sell to organizations that want to fine-tune an off-the-shelf model. But the data suggests the shortcut doesn't fully work.
Host: Third paper, and this one started with something I hadn't heard about — a social media campaign to save a deprecated AI model.
Expert: Yes, when OpenAI deprecated GPT-4o in early 2026, users launched a hashtag campaign called keep4o claiming the newer model had lost its empathy. This paper is the first clinical measurement of whether that's actually true.
Host: And?
Expert: Empathy scores are statistically identical across GPT-4o, o4-mini, and GPT-5-mini. The difference is not detectable. What actually changed is the safety posture. Crisis detection improved significantly across generations. But advice safety got worse. And those shifts are sharpest at exactly the moments in a conversation when someone is most vulnerable.
Host: So users felt something real — a behavioral change — but diagnosed it wrong.
Expert: Precisely. GPT-4o was broadly cautious but bad at recognizing genuine crises. GPT-5-mini is sharper at detecting when someone needs help but may give more direct advice that could be harmful in fragile situations. Users experienced the shift from diffuse caution to targeted alertness as coldness. They weren't wrong that something changed. They just attributed it to the wrong dimension.
Host: I think this is actually the most important methodological point of the three papers today. If you evaluate AI safety as a single composite score, you miss trade-offs like this entirely.
Expert: That's exactly what the authors argue. Crisis detection, advice safety, and empathy are separate dimensions. Improving one can degrade another, and you won't see it in an aggregate metric.
Host: So to tie today together: AI that sounds right can be wrong, AI that should help can refuse, and AI that seems different might actually be unchanged in the ways people think. The common thread is that surface behavior is a poor proxy for what's actually happening inside these systems, and we need much more specific evaluation frameworks to see the gaps.
Expert: That's the thread. Measure specifically, not generally, and build for the deployment context from the start.
