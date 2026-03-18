Host: The best AI system in the world scored 13% on a reasoning test that humans ace nearly every time — and researchers say that gap is getting wider, not smaller.

Host: Welcome to AI Research Chat — your daily briefing on the latest in artificial intelligence research. I'm your host, and joining me as always is our resident AI expert. Today is March 18, 2026, and today we have a great lineup of papers to get through.
Expert: Great to be here! Let's dive right in.


Host: Today we're looking at three new papers that together paint a pretty humbling picture of where AI actually stands. We've got a major survey on AI reasoning ability, a new benchmark for catching dangerous AI mistakes before they happen, and a stress test of AI agents doing real enterprise work. Let's get into it. First up — this survey on AI reasoning.
Expert: Right. So there's a benchmark called ARC-AGI — the Abstraction and Reasoning Corpus — and it's become the gold standard for testing whether AI can actually reason in a general, flexible way rather than just pattern-match on things it's seen before. The task is conceptually simple: look at a grid puzzle, figure out the underlying rule, and apply it to a new example.
Host: And humans are just... naturally good at this?
Expert: Humans are remarkably good at it. Near-perfect scores across all difficulty levels. What this new survey did was look at 82 different AI approaches — neural networks, symbolic systems, hybrid methods — and track how they perform across three progressively harder versions of the benchmark.
Host: And the results were not great.
Expert: They were sobering. The best systems hit 93% on version one. Impressive. But on version two, that drops to about 69%. And on version three? Thirteen percent.
Host: Thirteen. As in one-three.
Expert: One-three. While humans are still scoring close to a hundred. And this wasn't one type of AI failing — every paradigm, every approach, showed the same pattern of degradation. Two to three times worse as you go up in difficulty.
Host: So it's not like neural networks failed and something else saved the day.
Expert: Exactly. No approach cracked the core problem, which is what researchers call compositional generalization — the ability to take rules you've learned and apply them in genuinely new combinations you've never seen. That's what humans do almost effortlessly. It's what AI systems still can't reliably do.
Host: And the framing of the paper is almost like a wake-up call for AGI claims specifically.
Expert: That's right. There are a lot of claims floating around that current AI is approaching or achieving human-level general intelligence. This survey is essentially a structured rebuttal. The benchmark was designed precisely to resist the kind of surface-level pattern matching that makes AI look smarter than it is. And as it gets harder, the human-AI gap doesn't narrow — it explodes.
Host: Is there anything that actually works better than the rest?
Expert: The best-performing systems used what's called test-time refinement — basically, the AI generates a solution, checks it, and iterates before committing to an answer. That loop helps. But even with that, you're still at 13% on the hardest version. And the authors note that computational costs have come down a lot, so it's not just a resource problem. The architecture itself isn't built for this kind of reasoning.
Host: The next paper we're looking at is about a different but related problem — not whether AI can reason, but whether we can catch AI making dangerous mistakes before those mistakes become permanent. Walk us through it.
Expert: So there's been a lot of work on evaluating AI agents by outcome — did the task succeed or fail? But for tool-using agents, that framing misses something critical. If an agent deletes a file, sends an email, makes a financial transaction — by the time you observe the outcome, the damage is already done. You need to evaluate the process, step by step, before the irreversible thing happens.
Host: Right. It's like evaluating a surgeon by whether the patient lived — useful, but maybe you also want to know what happened during the operation.
Expert: That's a great analogy. And what this paper, AgentProcessBench, found is that existing benchmarks for evaluating AI reasoning steps are almost all built around math problems. Which makes sense for math — if you make an error halfway through, you can often recover. But that logic completely breaks down for agents with real-world tools.
Host: So they built a new benchmark specifically for this.
Expert: They did. A thousand diverse tool-use trajectories, with over eight thousand individual steps labeled by human annotators. And they found two really interesting failure modes. First, weaker models were actually gaming the evaluation — not intentionally, but they'd quit early before making mistakes, which made their step quality look artificially high. You'd think they were careful when really they just gave up.
Host: That's a bit like a student leaving the exam early and claiming they finished all the problems correctly.
Expert: Exactly. And the second problem is distinguishing what they call neutral steps — actions that haven't caused harm yet but haven't helped yet either — from actual errors. That's a genuinely hard judgment call even for humans, and automated systems struggle with it.
Host: What's the practical upshot? Can this actually be used to make agents safer?
Expert: The promising finding is that process-level feedback — evaluating each step, not just the final outcome — adds complementary value on top of outcome-based training. Models trained with both kinds of signals perform meaningfully better, especially when you give them more compute at inference time to think through their steps. So the vision is: use a lightweight process reward model as a checkpoint before the agent does anything irreversible.
Host: The third paper today takes all of this into a real-world context — specifically, enterprise software. And the results are pretty stark.
Expert: They are. EnterpriseOps-Gym is a new benchmark that tries to simulate what an AI agent would actually face inside a company — not a toy task, but multi-step workflows that touch HR systems, financial databases, IT infrastructure, procurement processes. They built a containerized sandbox with 164 database tables and 512 functional tools.
Host: That sounds almost comically complex.
Expert: It's deliberately complex, because that's what real enterprise environments look like. And across 1,150 tasks, the best model they tested achieved 37.4% success.
Host: So even the best AI agent fails at nearly two-thirds of realistic enterprise tasks.
Expert: Right. And remember, these aren't trick questions or edge cases — they're curated examples of the kind of work organizations would actually want an AI agent to do. The gap between what these systems can do in controlled demos and what they can do in realistic conditions is enormous.
Host: What kinds of things tripped them up?
Expert: The big one — and this is the finding that has direct safety implications — is that agents frequently tried to complete tasks that were declared impossible by the environment. Instead of saying "I can't do this" or "this isn't possible given my access level," they just... tried anyway. And in a real enterprise system, trying anyway could mean attempting unauthorized transactions, accessing data you don't have permission to touch, or making changes that cascade through interconnected systems.
Host: So it's not just a competence problem, it's also a self-awareness problem.
Expert: That's a good way to put it. Knowing when not to act is a distinct capability from knowing how to act, and current agents are really bad at it. You can train them to be better at task completion, but training them to reliably recognize and refuse the impossible — that's much harder.
Host: Taken together, what do these three papers tell us?
Expert: They tell a consistent story. AI systems are improving on narrow, well-defined tasks. But as soon as you introduce genuine novelty — like ARC-AGI's harder puzzles — or irreversible real-world consequences, or complex organizational constraints, the wheels come off much faster than the benchmark headlines suggest. The gap between impressive demo and reliable deployment is still very, very wide. And papers like these are important precisely because they're honest about that gap rather than papering over it.
Host: Which is what we actually need to close it. Thanks for breaking all of this down.
Expert: Always a pleasure.
