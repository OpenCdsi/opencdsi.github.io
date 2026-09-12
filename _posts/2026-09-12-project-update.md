---
title: The Status of the OpenCdsi Project
layout: post
author: Dennis Dunn <ansofive@gmail.com>
---
I've accomplished quite a bit in the past couple of weeks, let's
look at where we stand with the OpenCdsi project.

If you've been following along at home, you'll notice that I've
been using [Claude](https://claude.com/product/overview), an AI
product of [Anthropic](https://www.anthropic.com). My first foray 
into serious vibe codding was the VaxEngine. After I'd exhasted
my session limits a bunch of times, I decided to buy a Pro subscription.
I reasoned that I'd spent hundreds of dollars on other hobbies, why
should this one be different? It paid off.

## VaxEngine

The original vision for [WorldVax](https://worldvax.org) was to provide
vaccine decision support to off-grid clinics. That required some sort
of engine to take an immunization history and produce vaccine forecasts.
I never got it right.

VaxEngine is the core of the *WorldVax* vision. It isn't perfect but it has an
84% pass rate on the conformance test corpus.

The core of the VaxEngine is available as a nuget package from [Github](https://github.com/orgs/OpenCdsi/packages?repo_name=Platform).

## Clinical Reference
The [CDC Pink Book](https://www.cdc.gov/pinkbook/hcp/table-of-contents/index.html) is packaged as a .NET library to provide narrative text explaining the engines
decisions. 

The ClinicalReference library is available as a nuget package from [Github](https://github.com/orgs/OpenCdsi/packages?repo_name=Platform).

## API

The VaxEngine is exposed as an RPC-ish API. In addition, the *CDSi Supporting Data* is available
as resource-style endpoints.

The API is available as a Docker images from [Github](https://github.com/orgs/OpenCdsi/packages?repo_name=Platform).

## Mobile App

The mobile app is built with the .NET MAUI cross-platform framework. It is running on Android 16 and Windows 11.
The app runs the VaxEngine locally, supporting the off-grid vision of *WorldVax*. It contains both the engine and 
the clinical reference along with a simple patient database.

The app is available on [Github](https://github.com/OpenCdsi/Platform/releases).


### Final Thoughts

It's been an exciting few weeks for me as I built all of this with Claude.
If I'd been more rational, I might have checked [r/claudecode](https://www.reddit.com/r/ClaudeCode/) to learn about things like *prompt engineering* or *RAG* or *GAN*.
But that's not really my way, is it? Jump in and learn to swim. Throw yourself
at the ground until you miss. 

Those of you who have been doing this for a while
might smirk and say "Look at the noob! How precious!" Well, I think
I understand.

 I have seen the light.