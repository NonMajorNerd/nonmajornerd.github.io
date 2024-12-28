---
title: "KnightBot Data"
keywords: nerd navy non major nerd nonmajornerd knightbot twitch channel bot chat
tags: [Nerd_Navy, KnightBot]
sidebar: knightbot_sidebar
permalink: data.html
toc:false
---  

## Overview
> This is semi-live data from KnightBot which is typically updated shortly after every Twitch stream.
> This data was last updated {{ page.last-modified-date | date: '%B %d, %Y' }}.

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
			{% assign archimg = "<img src='" | append: "https://raw.githubusercontent.com/NonMajorNerd/nonmajornerd.github.io/refs/heads/main/_assets/GFX/KB/" | append: {{archdata[0]}} | append: ".png'>" %}
			{{ archimg }}
			{{ archdata[1] }}
		{% elsif pair[0] == "Artifact" %}
			{% if pair[1] != "None" %}
				{% assign artdata = pair[1] | split: "/" %}
				{% assign artimg = "<img src='" | append: "https://raw.githubusercontent.com/NonMajorNerd/nonmajornerd.github.io/refs/heads/main/_assets/GFX/KB/Artifacts/" | append: {{artdata[0]}} | append: ".png'>" %}
				{{ artimg }}
				{{ artdata[1] }}
			{% else %}
				{{ pair[1] }}
			{% endif %}
		{% else %}
			{{ pair[1] }}
		{% endif %}
    {% endtablerow %}
  {% endfor %}
</table>