---
layout: page
title: Tracks
include_in_header: true
include_in_footer: true

tracks:
  - name: Kart Point
    city: Brasilia
    country: Brazil
    slug: kartpoint
  - name: Galaxy Motorsports Karting
    city: Athens
    country: Greece
    slug: megarakartingcircuit
  - name: Kartodromo Città di Messina
    city: Messina
    country: Italy
    slug: kartodromomessina
  - name: Pista del Corallo
    city: Sassari
    country: Italy
    slug: pistadelcorallo
---

# Licensed Tracks

These partner tracks let us tap straight into their live timing feed, so you get race updates as they happen. New tracks join the lineup from time to time, so keep an eye out for fresh additions.

<style>
    .tr_container {
        display: flex;
        flex-wrap: wrap;
        gap: 16px;
        padding-top: 16px;
    }
    .tr_track {
        display: flex;
        align-items: center;
        gap: 8px;
        padding: 8px;
        width: 238px;
        height: 94px;
        border: 1px solid rgb(185, 198, 212);
        border-radius: 5px;
    }
    .tr_logo {
        width: 60px;
        height: 60px;
    }
</style>

{% assign sorted_tracks = page.tracks | sort: "name" | sort: "country" %}
{% assign countries = sorted_tracks | map: "country" | uniq %}

{% for country in countries %}

### {{ country }}

<div class="tr_container">
    {% for track in sorted_tracks %}
        {% if track.country == country %}
        <div class="tr_track">
            <img class="tr_logo" src="/assets/tracks/{{ track.slug }}.jpg" />
            <span><strong>{{ track.name }}</strong><br>{{ track.city }}, {{ track.country }}</span>
        </div>
        {% endif %}
    {% endfor %}
</div>
{% endfor %}
