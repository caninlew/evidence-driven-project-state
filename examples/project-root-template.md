# Project Root Template

Use one folder per project.

```text
project-root/
├─ 01_sources/
│  ├─ briefs/
│  ├─ meeting-notes/
│  ├─ consultant-feedback/
│  ├─ email-excerpts/
│  ├─ drawings-and-analysis/
│  └─ site-media/
├─ 02_state/
│  ├─ source-register/
│  ├─ state-register/
│  ├─ change-log/
│  ├─ open-questions/
│  └─ tasks/
└─ 03_outputs/
   ├─ alignment/
   ├─ consensus/
   ├─ design/
   └─ acceptance/
```

## Rules

1. Keep the folder boundary project-specific.
2. Do not mix materials from multiple projects in the same root.
3. Treat raw source files as immutable inputs.
4. Write new state versions instead of overwriting history.
5. Keep research outputs separate from raw source material.
