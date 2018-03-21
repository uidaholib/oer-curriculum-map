---
layout: table
title: Items
permalink: /items/
---
{% assign items = site.data.oer-curriculum-map.csv %}

<!-- currently downloaded version of datatables is bundled with bootstrap and responsive and csv download extensions -->
## Browse Items

This table provides sorting and basic search of the archive contents. 
Click on the "Read" link to see the full document.

<table id="item-table">
    <thead>
        <tr>
            <th>Title</th>
            <th>Date</th>
            <th>Subjects</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
{% for item in items %}        
        <tr>
            <td><a href="{{ site.baseurl }}/items/{{ item.identifier | downcase }}.html">{{ item.title }}</a></td>
            <td>{{ item.date }}</td>
            <td>{{ item.subjects }}</td>
            <td>{{ item.description | truncatewords: 15 }} <a href="{{ site.baseurl }}/items/{{ item.identifier | downcase }}.html">Read</a></td>
        </tr>
{% endfor %}
    </tbody>
</table>
