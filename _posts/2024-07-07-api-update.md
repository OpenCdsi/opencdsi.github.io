---
title: API Update
author: Dennis Dunn <ansofive@gmail.com>
layout: post
---

I've updated both the API endpoints and the UI for the [CDSi Browser](https://opencdsi.org/).

### V2 Endpoints

- /v2/antigens/
- /v2/antigens/*antigen-key*/
- /v2/antigens/*antigen-key*/series/
- /v2/antigens/*antigen-key*/series/*series-key*/
- /v2/vaccines/
- /v2/vaccines/*cvx*/
- /v2/vaccines/*cvx*/livevirusconflicts/
- /v2/observations/
- /v2/observations/*observation-code*/
- /v2/groups/
- /v2/groups/*vaccine-group*/
- /v2/groups/*vaccine-group*/antigens/
- /v2/cases/
- /v2/cases/assessments/
- /v2/cases/*case-id*/
- /v2/cases/*case-id*/assessment/

### Legacy Endpoints

- /v1/antigens/
- /v1/antigens/*name*/
- /v1/antigens/*name*/series/
- /v1/antigens/*name*/series/*series-name*/
- /v1/vaccines/
- /v1/vaccines/*cvx*/
- /v1/observations/
- /v1/observations/*observation-code*/
- /v1/groups/
- /v1/groups/*vaccine-group*/
- /v1/groups/*vaccine-group*/antigens/
- /v1/cases/
- /v1/cases/*case-id*/
- /v1/cases/*case-id*/test-data/
- /v1/cases/*case-id*/expected-result/