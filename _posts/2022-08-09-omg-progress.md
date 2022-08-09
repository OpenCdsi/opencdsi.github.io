---
title: OMG! Progress!!
author: Dennis Dunn <ansofive@gmail.com>
layout: post
---

# OMG! Progress!!

After 6 weeks of hacking I've actually made some progress on the vaccine evaluation code. This is more progress than I made
in the 9 years previously.

The only thing left, besides testing to see if it actually works, is the completed-series check in the conditional skip code. 

My next step will be to write a couple of tests to see what breaks. I'll take  the medical info from one of the 
supporting data test cases, run it through the vaccine evaluator, and then check the status of the vaccine and target doses.
I fully expect that the evaluation will blow up because some date is null or I've mispelled some string constant but
that's what testing is for, right?!
