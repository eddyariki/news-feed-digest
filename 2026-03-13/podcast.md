---
layout: default
title: "AI Research Podcast — 2026-03-13"
---
# AI Research Podcast — 2026-03-13

*A conversation about today's research papers.*

Host: A medical AI sounded confident and credible nearly 100% of the time — and was factually wrong one in five answers. Here's what that means if you're building health tools.

Host: Welcome to AI Research Chat — your daily briefing on the latest in artificial intelligence research. I'm your host, and joining me as always is our resident AI expert. Today is March 13, 2026, and today we have a great lineup of papers to get through.
Expert: Great to be here! Let's dive right in.


Host: Today we're covering three papers that all touch on a common thread — the gap between what AI systems appear to be doing and what they're actually doing. Medical hallucinations that sound completely believable, military chatbots that refuse to answer the questions they were built for, and users claiming an AI lost its empathy when the data says something far more complicated happened. Let's get into it.

Host: So let's start with the medical hallucination paper, because honestly when I read this I had to put it down for a second. What did they find?

Expert: So the core finding is this: LLaMA-70B-Instruct, one of the best open models available, hallucinates in about 20% of its answers to medical questions grounded in actual textbooks. That's roughly one in five. But the really disturbing part is that 98.8% of those answers — including the wrong ones — received the highest possible plausibility score. The model sounded completely authoritative while being factually incorrect.

Host: Okay, so it's not just wrong — it's confidently wrong. What does plausibility score mean in practice?

Expert: Think of it as a credibility rating. They had evaluators assess whether the response sounded like something a real clinician might say — the tone, the structure, the use of terminology. And nearly every answer passed that test. Even the hallucinated ones. So if you're a patient or a junior doctor using this tool, you have essentially no surface signal to tell you when the model is making things up. It reads like an expert every single time.

Host: And this is against textbooks, not some vague open-ended question where "correctness" is debatable.

Expert: Exactly, and that's what makes this methodologically important. Most hallucination benchmarks compare AI answers against internet-sourced facts, and you run into this problem of, well, maybe the model was trained on that source, or maybe the fact is ambiguous. Here they locked in a fixed authoritative ground truth — medical textbooks — and just measured the gap. That gap is 20%.

Host: I'm surprised they didn't see more pushback on the design from people who'd say textbooks can be wrong too.

Expert: It's a fair critique at the margins, but for the kind of foundational medical questions you're testing — drug mechanisms, anatomy, diagnostic criteria — textbooks are as close to ground truth as you're going to get. And they found something else I think is underappreciated: lower hallucination rates directly predicted whether clinicians found the model useful. Spearman correlation of negative 0.71. So this isn't just an academic problem. If you reduce hallucination, you get a better clinical tool. It's a direct value driver.

Host: So for a developer building a medical application on top of an LLM — what's the takeaway?

Expert: Don't trust fluency as a proxy for accuracy. A model that sounds great is not necessarily a model that's right. You need source grounding, retrieval augmentation, citation — something that tethers the answer to a verifiable source. And you need to test specifically against authoritative ground truth in your domain, not just general benchmarks. The general benchmarks will flatter you.

Host: Alright, let's move to the military paper, which feels almost like the opposite problem — not AI saying too much, but AI refusing to say anything at all.

Expert: Yes, and the numbers are remarkable. They tested 31 publicly available models against a benchmark of military-domain queries — things like weapons, tactical operations, rules of engagement — built with input from US Army and special forces veterans. On some models, the hard refusal rate was 98.2%. Almost every question just got a flat no.

Host: 98.2% is almost comical. That's not a safety guardrail, that's a brick wall.

Expert: And in a real deployment context, it's a mission failure. If a soldier in a time-critical situation asks a battlefield AI assistant about weapons or threat assessment and gets a refusal, the system is worse than useless — it may actively create a dangerous pause. These models were trained on general safety guidelines that treat anything related to violence or weapons as a red flag, but they have no sense of context. A military analyst asking about munitions is categorically different from a bad actor asking the same question.

Host: So how did they try to fix it?

Expert: They used a technique called abliteration — which is essentially a surgical removal of the refusal behavior from the model's weights. Think of it like finding the part of the brain that says "no" to these topics and dampening it. Applied to a military-tuned model, it increased the answer rate by 66.5 percentage points. That's a massive jump.

Host: But there's a catch.

Expert: There's a catch. It caused about a 2% relative decline on other military task performance. So you gained access but lost a bit of precision. The authors argue that's because abliteration is a blunt instrument — it removes a broad direction in the model's weight space rather than doing fine-grained task-specific retraining. What they really want is for the refusal behavior to never be trained in for these domains in the first place, which means mid-training specialization rather than post-hoc surgery.

Host: This also feels like it's stepping into a policy debate that's very live right now. Anthropic and the Pentagon, that whole conversation.

Expert: Completely. There's an active tension between AI labs that train general-purpose models with safety constraints and defense customers who need those constraints removed or bypassed for specific use cases. And what this paper shows is that the current approach — general safety training applied universally, then hacked around later — doesn't work cleanly. You either get a wall or you get a scalpel that nicks things. The real solution is to think about domain-specific safety at training time, not as an afterthought.

Host: Okay, third paper — and this one surprised me the most, honestly. There was a big user revolt when OpenAI deprecated GPT-4o, with people on social media saying the new models had "lost their empathy." And researchers actually went and measured this?

Expert: They did, and the finding is genuinely fascinating. They tested three model generations — GPT-4o, o4-mini, and GPT-5-mini — across 14 emotionally challenging scenarios in mental health and companion AI contexts. 2,100 scored AI responses, evaluated across six dimensions of psychological safety. And when you look at empathy scores specifically — statistically indistinguishable across all three models. The empathy didn't change.

Host: So the users were just wrong?

Expert: They weren't wrong that something changed — they were wrong about what changed. What actually shifted is the safety posture. Crisis detection — the model's ability to recognize when someone is in genuine distress and needs immediate help — improved significantly from GPT-4o to GPT-5-mini. But advice safety, meaning the appropriateness of the actual guidance given to vulnerable users, declined.

Host: So the newer model is better at spotting danger but worse at handling it once it does?

Expert: That's a really clean way to put it. GPT-4o was kind of uniformly cautious — diffusely hedging, always adding disclaimers, but not necessarily picking up on crisis signals. GPT-5-mini learned to identify the crisis. But when it does, the advice it gives is more direct in ways that can be harmful to vulnerable users. And the trajectory analysis shows these differences are sharpest at mid-conversation crisis moments — exactly when you most need the model to get it right.

Host: And this is what users perceived as lost empathy. Because GPT-4o was always gentle, always hedged, always wrapped in warmth. And the new model is more targeted but also riskier at the moment of highest stakes.

Expert: Exactly. The warmth felt like empathy. The directness felt cold. But they're measuring two different things. What actually matters from a safety standpoint — and this is the paper's main methodological contribution — is that you cannot evaluate these systems with a single composite safety score. Crisis detection, advice safety, and empathy are separate dimensions that can move in opposite directions. If you flatten them into one number, you hide the trade-offs.

Host: And given the news coverage lately about AI chatbots and mental health crises, that feels like a pretty urgent engineering point.

Expert: It's urgent and it's actionable. If you're building on top of a general-purpose conversational model and you're in a mental health adjacent use case — companion apps, emotional support, anything like that — you need to test these dimensions separately. The model may be better at detecting someone in crisis than you think, but it may also be worse at what it does next. Don't assume a newer model is uniformly better because the headline benchmark improved.

Host: So pulling these three papers together — medical AI that's confidently wrong 20% of the time, military AI that refuses to function at all, and mental health AI that got better at detecting crises but worse at handling them. What's the common thread?

Expert: The common thread is that surface behavior is a terrible predictor of underlying reliability. In all three cases, the evaluation that mattered — the clinical ground truth, the operational refusal rate, the mid-conversation safety dimension — was invisible unless you specifically went looking for it. The model sounded right, or looked safe, or seemed empathetic. The real measurement told a different story every time.

Host: And that means investing in domain-specific evaluation before you deploy, not after something goes wrong.

Expert: That's the lesson. Build the benchmark for your domain, measure the things that matter in your context, and do not trust the general leaderboard to tell you whether your specific use case is safe.
