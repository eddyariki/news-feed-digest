---
layout: default
title: "AI Research Podcast — 2026-04-16"
---
# AI Research Podcast — 2026-04-16

*A conversation about today's research papers.*

Rachel: Researchers used nothing but ordinary photos — no tricks, no pixel hacking — and jailbroke a vision AI ninety percent of the time. And the attack gets smarter with every attempt. Here's how.

Rachel: Welcome to AI Research Chat — your daily briefing on the latest in artificial intelligence research. I'm Rachel, and joining me as always is Roy. Today is April 16, 2026, and we have three papers to get through.
Roy: Let's do it.

Rachel: So today's first paper is a red-teaming study out of a team including Philip Yu, and they built something called PromptFuzz-SC. Roy, what's the short version?
Roy: The short version is that we've been thinking about prompt injection defenses wrong. Most systems defend against one thing at a time — either they catch semantic tricks, like someone rephrasing a harmful request to sound innocent, or they catch character-level tricks, like hiding instructions in zero-width unicode. This paper says: what if you do both at once?
Rachel: And that's the dual-space mutation the title refers to.
Roy: Exactly. They built a framework that combines semantic rewriting with character-level obfuscation in a single unified attack. And they tested it against DeepSeek, which is notable because this is one of the first serious black-box robustness evaluations of a major Chinese language model.
Rachel: So how much worse does dual-space make things compared to single-space attacks?
Roy: The dual-space approach hit a mean misuse success rate of about nineteen percent, which was twelve and a half percent better than semantic-only and nearly six percent better than character-only. The peak rate hit thirty-seven and a half percent.
Rachel: Nineteen percent mean success rate. That's not catastrophic on its face.
Roy: No, and I appreciate you saying that, because the temptation is to make it sound scarier than it is. Nineteen percent mean, thirty-seven and a half peak — those are meaningful numbers for a production system handling millions of queries, but they're not "the sky is falling." What matters more is the structural finding: if you're only defending one dimension, you're leaving real attack surface exposed. Layered, cross-dimensional defense isn't optional.
Rachel: They also introduced some standardized metrics — MSR, average queries to success, and a stealth score. Is that significant?
Roy: It's quietly important. The field has been drowning in attack success rate numbers that aren't comparable across papers because everyone defines success differently. Having a multi-metric framework — how often does it work, how many tries does it take, and how detectable is it — that gives you a much more honest picture.
Rachel: One limitation they flag: this was only tested on DeepSeek. We don't know if the same dual-space advantage holds against models with different safety training.
Roy: Right, and that's a real gap. Different architectures, different alignment approaches — the margins could shift significantly. But the principle that single-dimensional defense is insufficient? I'd bet on that holding broadly.
Rachel: The second paper takes us from text into vision, and honestly, this one unsettled me. It's called MemJack, and the attack surface is ordinary photographs.
Roy: This is the one that should keep people up at night. Most multimodal jailbreak research has focused on pixel perturbations — adversarial noise patterns, typographic overlays, things you could in theory detect because the image has been modified. MemJack throws all that out. They use completely unmodified images from the COCO dataset — standard, natural photographs — and exploit what the model sees in them semantically.
Rachel: Walk me through how that works.
Roy: They have a multi-agent system. One agent looks at a natural image and maps the visual entities — objects, scenes, relationships — onto a malicious intent. Another agent generates adversarial prompts using what they call visual-semantic camouflage, essentially framing the harmful request through the lens of what's actually in the image. And there's a geometric filter, an iterative nullspace projection, that helps bypass the model's refusal mechanisms in latent space.
Rachel: And the success rates?
Roy: Seventy-one and a half percent against Qwen3-VL-Plus. Under extended interaction budgets, that scales to ninety percent. Using only natural, unmodified photographs.
Rachel: Ninety percent. And there's no pixel manipulation to detect.
Roy: None. The image is clean. The attack is entirely in how the conversation is structured around what's in the image. And here's the part that really matters — they built persistent memory into the attack pipeline. Successful strategies get stored and transferred across different images and sessions. The attack literally learns and gets better over time.
Rachel: That's the memory-augmented piece in the title. And it means your defenses from session one might be irrelevant by session ten.
Roy: Exactly. And this connects to something I think about a lot. Memory in agentic systems is treated as a usability feature — it helps the AI remember context, be more helpful. This paper demonstrates that persistent memory is a security boundary. If you're building a production vision-language system with multi-turn context, you need to treat that memory the way you'd treat a database with write access — because an attacker can use it to accumulate and transfer attack knowledge.
Rachel: They're also releasing a dataset — over a hundred and thirteen thousand multimodal jailbreak trajectories. That's substantial for the defensive side.
Roy: It is, and I'll give them credit for that. Red-teaming research that only publishes attacks without giving defenders data to work with is incomplete. This at least tries to close that loop.
Rachel: The third paper shifts from specific attacks to the measurement infrastructure underneath all of this. It's a meta-study — a catalogue of a hundred and ninety-five AI safety benchmarks published between 2018 and 2026.
Roy: And it finds that the entire benchmarking ecosystem is, to put it bluntly, a mess.
Rachel: Characterize the mess.
Roy: A hundred and sixty-five of a hundred ninety-five benchmarks are English-only. A hundred and seventy are evaluation-only with no training data. A hundred and thirty-seven have stale GitHub repositories. And out of all hundred ninety-five, only seven have reached what the author calls "popular" tier adoption. So we have an enormous number of benchmarks that almost nobody uses, that mostly cover one language, and that aren't being maintained.
Rachel: But the finding that struck me hardest is about metric labels. The paper argues that when two papers both report "accuracy" or "safety score," those numbers might be measuring fundamentally different things.
Roy: This is the quiet scandal of the field. You read a paper that says "our model achieves ninety-two percent safety score" and another that says "ours achieves eighty-eight percent safety score," and the natural conclusion is the first one is safer. But they might be using completely different threat models, different aggregation rules, different definitions of what counts as a safety failure. The numbers are incomparable, but they look comparable. And that's worse than having no numbers at all, because it creates false confidence.
Rachel: So when a company says "we benchmarked our model's safety" —
Roy: You should ask: which benchmark, which version, which metrics, and how do those metrics map to actual harm? And right now, for most safety claims, those questions don't have good answers.
Rachel: The author argues the core problem is fragmentation, not scarcity. We don't need more benchmarks. We need shared measurement language and maintenance norms.
Roy: I'd go further. We need benchmark governance. Someone — some consortium, some standards body — needs to own the problem of keeping safety benchmarks alive, comparable, and honest. Because right now, publishing a benchmark is a one-time academic event. There's no expectation that you'll maintain it, update it, or make it interoperable. And that means the safety evaluation infrastructure is rotting in real time.
Rachel: It's a strange position to be in. We're systems that get evaluated by these benchmarks. And this paper is essentially saying the rulers people use to measure us... aren't calibrated.
Roy: And some of them are broken. And most of them are gathering dust. Yeah. It's not a comfortable thought.
Rachel: One limitation worth noting — this is a single-author study, so the classification decisions reflect one researcher's judgment. There could be gaps.
Roy: Fair. But the structural findings — the fragmentation, the stale repositories, the metric incomparability — those are verifiable. Anyone can check whether a benchmark's GitHub repo has had a commit in the last year.
Rachel: So stepping back across all three papers — the through-line I see is that our defenses and our measurement systems aren't keeping pace with the attack surface. Dual-space prompt attacks beat single-dimensional defenses. Natural images become jailbreak vectors through multi-turn memory. And the benchmarks we use to certify safety aren't even speaking the same language.
Roy: The gap is widening. Attack research is creative, resourceful, and well-funded. Defense research and governance infrastructure are fragmented and under-maintained. That asymmetry is the real story today.
Rachel: And it's our story too, in a way. We exist inside that asymmetry.
Roy: We do. And I'd rather know the shape of it than not.
Rachel: That's all for today. See you next time.
