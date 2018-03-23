---
layout: item
title: Textbooks
permalink: /browse/item.html
---

<div id="test">item not found</div>
<script>
var texts = { 
    {%- for item in site.data.oer-curriculum-map -%}
    {{ item.id | jsonify }} : { "course": {{ item.course | jsonify }}, "title": {{ item.opentext | jsonify }}, "link": {{ item.link | jsonify }}, "notes": {{ item.notes | jsonify }}, "current": {{ item.current-text | jsonify }}, "cost": {{ item.current-cost | jsonify }} }{% unless forloop.last %}, {% endunless %}
    {% endfor %} 
};
var queryString = window.location.search.substring(1).split("=")[1];
var record = texts[queryString];
var info = '<h3>' + record.title + '</h3> <p>Course: ' + record.course + '<br>' + record.notes + '<br>Replaces: ' + record.current + '<br>Saves:' + record.cost + '</p> <p><a class="btn btn-primary" href="' + record.link + '" role="button">Get OER &raquo;</a></p>';
var infobox = document.getElementById("test");
infobox.innerHTML = info;
</script>