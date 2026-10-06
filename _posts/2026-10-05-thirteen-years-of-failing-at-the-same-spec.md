---
layout: post
title: "Thirteen Years of Failing at the Same Spec"
date: 2026-10-05
series: thirteen-years
series_title: "Thirteen Years, One Week"
part: 1
---

*Part 1 of 3*

Is there a project sitting in a folder on your machine that you haven't touched in years? Something you were sure you could build?

Mine sat there for thirteen years.

Then I got a working version of it in about a week. Not a perfect one, a working one. This series is about how both of those are true.

## The dream

In 2013, my friend Jeffrey and I started a project called Worldvax. Jeffrey was the energy behind it, and he's the reason I started. The idea was an immunization engine that runs off-grid on constrained hardware, so a doctor in a remote place could get the same vaccine guidance a clinic gets here: proper schedules, who has had what, what's due next.

The existing engine had licensing problems for us, and we both worked in the Microsoft world, so we decided to write our own in C#.

Then I read the CDC's logic specification, and it looked easy. It's decision tables. If this, then that. I'd write a few ifs, and boom, done.

![A page of decision tables from the CDC logic specification]({{ '/assets/images/thirteen-years/logic-spec.png' | relative_url }})

It was not done.

## The graveyard

My GitHub is full of attempts. I couldn't work out how to get the data where it needed to be. I thought about writing it in Lisp, just so I could use macros. Jeffrey reminded me, "Remember, Dennis, this was designed by committee," and I laughed and failed some more.


![My GitHub repository list, full of attempts]({{ '/assets/images/thirteen-years/graveyard.png' | relative_url }})


The furthest I ever got was most of chapter six, and something called the conditional skip stopped me cold. My best win was the date math. When a date doesn't exist, the spec says to roll forward to the next valid date, and most libraries roll it back. I got that right, and it made me very happy. But how many times can you write the same code?

Then I retired, Jeffrey moved on to another project, and I started to wonder if I was as good a programmer as I thought.

## The lark

I'm not a Luddite, and I haven't been living under a rock. I'd seen the headlines: AI will change everything, AI will kill us all. I'd also seen the demos, and the big one was a to-do list app. A to-do list is what you give a junior developer in a job interview. If that's the peak, what good is it?

So one day, sitting in my living room, I did it as a lark. I handed the spec to an AI agent and figured nothing would come of it. This was a problem I thought needed a whole team.

The first agent came back and said it couldn't read the PDF, but here was an "industry-standard implementation." It checked exactly one thing: was there enough time since the previous dose? That was the entire evaluation. I'd spent years with that spec, and I knew it was malarkey.

Fine. You suck. Goodbye.

But I tried a second agent. I uploaded the spec and said, "Here's a federal spec for immunization decision support. I want to implement it as an engine I can drop into other projects. Read it and tell me how to proceed." It chewed on it for a while. Then it said: "Good. This is meaty."

An AI that was enthusiastic about my problem. I thought, I like this guy.

> **Lesson 1: Your struggle is your judgment.** I could call that first answer malarkey because I'd lost thirteen years to that spec. The failure wasn't wasted time. It was my qualification.

## Doing it wrong

I had no idea what I was doing. I didn't know you're not supposed to hand an AI an entire PDF at once. I didn't know what "prompt engineering" meant, or that people talk about engineering the context. I just uploaded the spec and said, do something.

And I was in a chat window, not a coding agent. So it kept telling me: "I don't have build tools in this sandbox. Here's the code. Download it, run the tests, and tell me what happened."

![A zip file going back and forth between a laptop and a chat window]({{ '/assets/images/thirteen-years/zip-loop.png' | relative_url }})

So I became the build server. Download the zip, run the tests, paste the results back, repeat. I even had to get a .NET environment working on my Mac, and there are a zillion ways to do that, and exactly one of them worked for me.

The AI wrote the code, and I was the build server. I stayed in that loop for the whole engine, and it worked anyway.

> **Lesson 2: Start with what you have.** A chat window and a zip file were enough. If you're waiting until you understand prompt engineering or have the perfect setup, don't.

## Next time

Then something happened that I didn't expect. We were working on age evaluation, and the AI stopped reading the spec and opened the real data. What it found there is the reason this series exists.

*Part 2: The Day My AI Read the Spec Better Than I Did.*

{% include series.html %}

{% include ai-note.html %}
