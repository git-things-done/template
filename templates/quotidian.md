---
name: Quotidian
about: About can’t be blank
title: "{{ date | date('Y-MM-DD, ddd') }}"
labels: diem
assignees: ''
---

# Quotidian
- [ ] Slept well
- [ ] Had breakfast
{{ env.quotidian_extra }}
