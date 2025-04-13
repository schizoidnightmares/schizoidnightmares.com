---
title: Gallery
description: A gallery of images present on the website
last_modified_at: April 12, 2025
---

# Gallery
65 images in total
{: .cap}

A gallery of the images on the website (newest created first)

<div class="table" markdown=0>
  <table class="full borders smallest">
    <tr>
      <th>Image</th>
      <th>Description</th>
      <th>Year</th>
      <th>Attribution</th>
      <th>Licence</th>
    </tr>
    {% for item in site.data.gallery %}
    <tr>
      <td><a href="{{ item.full }}" target="_blank" aria-label="Click to view full image"><img src="{{ item.thumb }}" width="50" alt="{{ item.alt }}" title="Click to view full image"></a></td>
      <td>{{ item.title }}</td>
      <td>{{ item.year }}</td>
      <td>{{ item.attribution }}</td>
      <td>{{ item.licence }}</td>
    </tr>
    {% endfor %}
  </table>
</div>