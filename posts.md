# Release Notes Overview

{% for release_note in site.release_notes %}
    <h2>{{ release_note.title }} </h2>
    <p>{{ release_note.content | markdownify }}</p>
{% endfor %}