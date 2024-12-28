---
title: "KnightBot Hall of Heroes"
keywords: nerd navy non major nerd nonmajornerd knightbot twitch channel bot chat
tags: [Nerd_Navy, KnightBot]
sidebar: knightbot_sidebar
permalink: heroes.html
toc: false
---  

## Overview
> This is Character data from KnightBot which is typically updated shortly after every [Twitch](https://www.twitch.tv/nonmajornerd) stream.

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
		{% if pair[0] == "Name" %}
			{% assign namedata = pair[1] | split: "/" %}
			{{ namedata[0] }}<br>
			<small>({{ namedata[1] }})</small>
		{% elsif pair[0] == "Archetype" %}
			{% assign archdata = pair[1] | split: "/" %}
			{% assign archimg = "<img src='" | append: "https://raw.githubusercontent.com/NonMajorNerd/nonmajornerd.github.io/refs/heads/main/_assets/GFX/KB/" | append: {{archdata[0]}} | append: ".png' width='40' height='40'>" %}
			{{ archimg }}<br>
			{{ archdata[1] }}
		{% elsif pair[0] == "Artifact" %}
			{% assign artdata = pair[1] | split: "/" %}
			{% if artdata[0] != "None" %}
				{% assign artimg = "<img src='" | append: "https://raw.githubusercontent.com/NonMajorNerd/nonmajornerd.github.io/refs/heads/main/_assets/GFX/KB/Artifacts/" | append: {{artdata[0]}} | append: ".png' width='40' height='40'>" %}
				{{ artimg }}<br>
				{{ artdata[1] }}
			{% else %}
				{{ artdata[0] }}
			{% endif %}
		{% else %}
			{{ pair[1] }}
		{% endif %}
    {% endtablerow %}
  {% endfor %}
</table>