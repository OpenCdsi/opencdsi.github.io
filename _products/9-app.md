---
title: Mobile App
icon: fa-users-gear
---
The mobile app forecasts future vaccines for a patient
given their immunization history. It runs on Android and Windows&nbsp;11. 

<div class="buttons mt-5">

   {%- for item in site.data.app-installers -%}
     <a class="button is-small is-outlined" href="{{ item[1].url }}">{{ item[1].title }}</a>
   {%- endfor -%}

</div>

