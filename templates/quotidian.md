---
name: Quotidian
about: This is your daily GitTD template.
title: "{{ timestamp | moment('Y-MM-DD, ddd') }}"
labels: ''
assignees: ''
---

# Quotidian
- [ ] Slept well
- [ ] Had breakfast

{% if (timestamp | moment("isoWeekday")) == 7 %}
{% include "templates/hebdomadal.md" %}
{% endif %}

{% if (timestamp | moment("isoWeekday")) == 1 %}
{% include "templates/aspirations.md" %}
{% endif %}
