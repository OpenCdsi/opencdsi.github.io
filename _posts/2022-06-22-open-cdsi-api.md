---
title: The Open CDSi API
layout: post
author: Dennis Dunn <ansofive@gmail.com>
---

# The Open CDSi API

Now you can browse the CDSi supporting data and defined testcases at
the (CDSi Data Browser)[https://opencdsi.org/api/].

The [api](https://github.com/opencdsi/api) project exposes the
data objects provided by the [CDC](https://www.cdc.gov/vaccines/programs/iis/cdsi.html)
as JSON over a REST-ish interface. Your application can access these endpoints:


* /api/antigens
* /api/antigens/{id}
* /api/antigens/{id}/series
* /api/antigens/{id}/contraindications
* /api/vaccines
* /api/vaccines/{id}
* /api/vaccines/{id}/conflicts
* /api/vaccines/{id}/antigens
* /api/vaccines/groups
* /api/vaccines/groups/{id}
* /api/vaccines/groups/{id}/antigens
* /api/observations
* /api/observations/{id}
* /api/testcases
* /api/testcases/{id}
* /api/testcases/{id}/medical

