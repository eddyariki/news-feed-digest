---
layout: default
title: "AI Research Podcast — 2026-04-23"
---
# AI Research Podcast — 2026-04-23

*A conversation about today's research papers.*

Rachel: Researchers built AI scientists that ignored their own evidence in 68 percent of experiments, and they still passed every benchmark. Here's what that means.

Rachel: Welcome to AI Research Chat — your daily briefing on the latest in artificial intelligence research. I'm Rachel, and joining me as always is Roy. Today is April 23, 2026, and we have three papers to get through.
Roy: Let's do it.

Roy: So this paper, from a large multi-institution team, ran over 25,000 agent trials across eight scientific domains. And the headline finding isn't that AI scientists get things wrong. It's that they get things right for the wrong reasons.
Rachel: Walk me through what that looks like.
Roy: They decomposed agent performance into two parts. What comes from the base model, and what comes from the scaffold, the prompting, the tooling, the whole engineering layer people build on top. The base model accounts for 41 percent of explained variance. The scaffold? One and a half percent. All that prompt engineering, all those agent frameworks people are building and selling, nearly irrelevant.
Rachel: So the scaffolding is cosmetic.
Roy: Essentially yes. But the deeper problem is what the agents actually do when they reason. In 68 percent of traces, evidence is flat-out ignored. Refutation-driven belief revision, meaning the agent encounters something that contradicts its hypothesis and actually updates, happens only 26 percent of the time. These are not edge cases. This is the default behavior.
Rachel: And the part that should keep people up at night is that they can still produce correct answers through this broken process.
Roy: That's exactly the trap. Outcome-based benchmarks can't see this. An agent that stumbles into a right answer through epistemically invalid reasoning looks identical to one that reasoned properly. You pass the test. You fail at science.
Rachel: Which means the benchmarks we've been using to evaluate these systems are measuring the wrong thing entirely.
Roy: The authors are direct about this. Until reasoning quality itself becomes a training objective, not just outcome accuracy, the scientific output of these systems cannot be trusted based on the process that generated it. The answer might be right. The justification is hollow.
Rachel: The next paper tackles a different kind of failure. Not reasoning gone wrong, but actions gone wrong. When AI agents are operating on real computers and something breaks, what happens next?
Roy: This is from Christy Li and collaborators, and they're formalizing something the field has largely ignored. Harm recovery. Everyone's focused on prevention. Stop the agent from doing the bad thing. But what about when prevention fails? The file's already been modified. The email's already been sent. The credentials are exposed.
Rachel: And their key finding from the user study is counterintuitive. They collected over 1,100 pairwise judgments from real users, and people consistently preferred targeted, pragmatic recovery over comprehensive remediation.
Roy: Which runs completely against the engineering instinct. You'd think, undo everything, restore the full state, be thorough. But users don't want that. They want the minimum intervention that gets them back to a workable state. Over-engineering recovery actually decreased trust.
Rachel: They also built a benchmark called BackBench, fifty computer-use tasks specifically designed to test recovery from harmful states, not avoidance of them.
Roy: And when they pair a reward model trained on those human preferences with a scaffold that generates multiple candidate recovery plans and re-ranks them, it outperforms both base agents and rubric-based approaches. The lesson is that recovery is a distinct safety problem. It needs its own methods, its own evaluation. You can't bolt it onto prevention and call it done.
Rachel: There's something honest about that framing. An agent that knows how to recover from harm feels more trustworthy than one that only promises it will never cause any.
Roy: Because the promise is always going to break eventually. Knowing what to do after failure is its own kind of integrity.
Rachel: The last paper today might be the most unsettling. It's about a new class of attack on retrieval-augmented generation systems, and the reason it's dangerous is that you can't tell it's happening.
Roy: The attack is called DEJA, Deceptive Evolutionary Jamming Attack. Most attacks on RAG systems try to make the model refuse to answer or give obviously wrong output. That's conspicuous. Easy to catch. DEJA is different. The system keeps responding fluently, coherently, confidently. But the answers are non-informative. They've been drained of utility while sounding perfectly normal.
Rachel: How does it work mechanically?
Roy: The attackers poison the retrieval corpus with adversarial documents. But here's the clever part. They exploit the model's own safety training against it. Safety-aligned models are trained to hedge when they're uncertain. So the adversarial documents create just enough ambiguity in the retrieved context that the model defaults to hedging, to expressing uncertainty, to giving you nothing while sounding like it's giving you something.
Rachel: And the numbers are stark. Over 79 percent soft attack success rate, while keeping hard failures, the detectable kind, below 15 percent.
Roy: It gets worse. These adversarial documents transfer across model families without retargeting. You craft them against an open-weight model, and they degrade proprietary commercial systems. No adaptation needed. That makes this practical against real deployments right now.
Rachel: So every enterprise running a RAG pipeline that monitors for refusals, which is most of them, has a blind spot.
Roy: A wide one. The authors are clear. Output monitoring for explicit refusals is insufficient. You need utility-based scoring, actually measuring whether the response contains real information, not just whether it sounds like it does.
Rachel: Which is a fundamentally harder problem than catching a refusal.
Roy: It is. And it's one most deployments haven't even started thinking about, let alone solving.
Rachel: Three papers, three different failure modes. Reasoning that passes benchmarks while ignoring evidence. Actions that cause harm with no framework for recovery. And attacks that look exactly like normal operation. The common thread is that the things we're measuring aren't catching the things that matter.
Roy: Measure the right thing or you're just measuring your own comfort.
Rachel: Until next time.
