---
title: "KnightBot Data"
keywords: nerd navy non major nerd nonmajornerd knightbot twitch channel bot chat
tags: [Nerd_Navy, KnightBot]
sidebar: knightbot_sidebar
permalink: data.html
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
  {% endfor %}
</table>