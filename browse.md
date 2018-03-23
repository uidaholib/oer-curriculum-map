---
layout: table
title: Browse
permalink: /browse/
---
{% assign items = site.data.oer-curriculum-map %}

## Browse OER Textbooks

This table provides sorting and basic search of OER mapped to GEM courses. 
Click on the title to see the full document information.

<table id="item-table" class="table table-striped table-bordered">
    <thead>
        <tr>
            <th>Course</th>
            <th>OER Title</th>
            <th>Saves</th>
            <th>Link</th>
        </tr>
    </thead>
    <tbody>
{% for item in items %}      
        <tr>
            <td>{{ item.course }}</td>
            <td><a href="{{ site.baseurl }}/browse/item.html?id={{ item.id | downcase }}">{{ item.opentext }}</a></td>
            <td>{{ item.current-cost }}</td>
            <td><a class="btn btn-primary" href="{{ item.link }}" target="_blank" role="button">Get OER &raquo;</a></td>
        </tr>
{% endfor %}
    </tbody>
</table>
