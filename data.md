---
title: "KnightBot Data"
keywords: nerd navy non major nerd nonmajornerd knightbot twitch channel bot chat
tags: [Nerd_Navy, KnightBot]
sidebar: knightbot_sidebar
permalink: data.html
toc:false
---  

## Overview
> This is semi-live data from KnightBot


<table>
  {% for row in site.data.CharacterData %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}
    {% tablerow pair in row %}
		{% if pair[0] == "Archetype" %}
			{% assign archdata = pair[1] | split: "/" %}
			{{ archdata[1] }}
		{% elseif pair[0] == "Artifact" %}
			{% assign artdata = pair[1] | split: "/" %}
			{{ artdata[1] }}
		{% else %}
			{{ pair[1] }}
		{% endif %}
    {% endtablerow %}
  {% endfor %}
</table>

<table>
  {% for row in site.data.CharacterData %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>