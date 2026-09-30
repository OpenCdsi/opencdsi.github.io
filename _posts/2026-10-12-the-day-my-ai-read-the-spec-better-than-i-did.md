---
layout: post
title: "The Day My AI Read the Spec Better Than I Did"
date: 2026-10-12
series: thirteen-years
series_title: "Thirteen Years, One Week"
part: 2
---

*Part 2 of 3. Part 1 covered thirteen years of failing at the same spec, and the day I handed it to an AI agent as a lark.*

## Age evaluation

We started on chapter six of the CDC spec with age evaluation. If a dose is given when the patient is too young, it doesn't count. That sounds simple: check the patient's age on the day of the dose. One comparison.

Then the AI did something I'd never have thought to do. It stopped reading the spec and opened the real data.

![Two age-rule blocks for the same COVID-19 dose, side by side]({{ '/assets/images/thirteen-years/age-rule-cards.png' | relative_url }})

- **Rule A**, for a COVID-19 dose: absolute minimum age of 0 days, retired on 2023-09-11.
- **Rule B**, same dose: absolute minimum age of 6 months minus 4 days, effective 2023-09-12.

Same dose, two age windows, split by date. A rule that had been tightened in 2023.

The point is that a dose isn't judged by today's rules. It's judged by the rules in effect on the day the shot was given. A 2016 shot needs the 2016 rule. That meant a design decision I didn't know I was making: you never delete old reference data. You only supersede it.

I hadn't read the spec that closely. My reaction was, well, how about that. The AI had found the trap before we'd written a line of code or run a single test.

Then it happened again, with intervals. The XML has two blocks that look exactly like the age blocks, but the meaning flips. With age, two blocks means pick one, by date. With intervals, two blocks means satisfy both. Same shape, opposite meaning. A naive engine would work today and quietly break the day the spec changed.

> **Lesson 3: Ask for a second reader.** Before it writes code, ask the agent to check your spec against your real data and tell you what's odd.
>
> **Lesson 4: Ground it in real source material.** Give it your actual documents and data, not your memory or its own.

## Trust, and steering

Here's what I did next, honestly: not a lot of double-checking. If it was talking sense, I told it to continue. And it kept finding things I'd missed, so I trusted it more.

But something else happened at the same time. I got more assertive. Not long after, the agent proposed one implementation plan and I stopped it and said, "I'd really like to see this and this before we do all of that." It said, sure, we can do that.

That's a strange thing to realize: the more I trusted it, the more confident I got about steering it.

> **Lesson 5: You say what, it says how.** Steer early, and stop a plan when it drifts.

By chapter eight, the agent wrote that the chapter was completely done, rules and wiring both, matching chapters six and seven, and that this was a good place to pause. The last piece left was the merge step that would turn everything into a full end-to-end pipeline.

I wrote back: *"Let's continue. I'm really excited to see the whole pipeline chugging away."*

Thirteen years, and that was the sentence.

## "It makes sense" is not a test

Let me name the worry. AI hallucinates, and a hallucination sounds exactly as plausible as the truth. If it's talking sense to me, how would I know?

For a long time, I wouldn't have. The agent was testing its work against examples from the spec and small slices of the supporting data. That's far better than answering from memory, but it's still the same mind writing the code and the tests. For a long time, the only thing checking the agent's work was the agent.

Then the engine could run the whole pipeline, and we could finally run the CDC's own conformance tests: 1,064 cases in the adult and early childhood corpus. Nobody in this conversation wrote them.

We failed 431 of them. About 40 percent.

![Failing conformance cases over time: 431, then 255, then 172]({{ '/assets/images/thirteen-years/failure-chart.png' | relative_url }})

Here's what I'd want you to take from that stretch of work: **the tests didn't tell me who was wrong. They told me where to look.** Sometimes the agent's understanding of the spec was wrong. Sometimes the test data itself looked a little off. And sometimes the agent's own guess was wrong, and it said so. In one case it predicted a result, ran the real thing, saw it was wrong, and fixed its own test.

## The one-day bug

My favorite failure was off by a single day. Three cases expected December 1st and got November 30th. The agent traced it to .NET's month arithmetic, which clamps to the last day of the month. The spec says a date that doesn't exist rolls forward to the first of the next month, and it even gives an example: March 31st plus six months is October 1st.

Think about that. Rolling dates forward instead of back was the one thing I got right in thirteen years. I started at the bottom and built the date math first. The agent started at the top, built the hard decision logic on simple date handling, and got to the date math last, because a failing test pointed it there.

Neither of us was wrong. But only one of us had a test suite telling us what to fix.

We got it down to 172 failures, about 84 percent passing. The ones left are strange, specialized cases, and I'm at peace with that. One week to working. Not one week to perfect.

> **Lesson 6: Find an independent judge.** A test suite you didn't write, or the equivalent for your project. Don't ask whether it sounds right. Ask what will tell you if it's wrong.
>
> **Lesson 7: Failing tests tell you where to look, not who's wrong.**

## Next time

The engine worked. But Worldvax was never about an engine. In Part 3, I ask the AI to build a mobile app, run most of that session from an old iPad, catch a case of featureitis, and find out what a thirteen-year failure is actually good for.

*Part 3: From Software Engineer to Product Designer.*

{% include series.html %}

{% include ai-note.html %}
