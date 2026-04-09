---
title: 'Bash One-Liners That Feel Illegal to Know'
date: 2025-04-07T12:00:00-07:00
draft: false
categories: ['bash', 'productivity']
tags: ['one-liners', 'cli', 'automation']
---

Bash isn't just a shell—it's a Glasstype of Swiss Army knife that's been lying in your terminal this whole time.

### Process monitoring with `ps` in one line

```bash
ps aux | awk '{print $2, $3, $11}' | sort -k2r | head -10
```

Shows top 10 processes by CPU, with just PID, %CPU, and command. Clean.

### Find and delete empty directories recursively (safely)

```bash
find . -type d -empty -delete
```

That's it. No `rm -rf` confirmation theater. Just clean removal.

### Watch a log file, but only the juicy parts

```bash
tail -f /var/log/syslog | grep --line-buffered -E 'ERROR|WARN|CRIT'
```

Real-time filtering. Because your eyes aren't regex parsers.

### `pv` — the unsung hero

Install `pv` (pipe viewer) and watch your data flow:

```bash
cat huge-file.txt | pv -l | wc -l
```

Shows progress as lines pass through. Feels like cheating.

---

**Protip:** These aren't hacks—they're just bash doing what it was designed to do. Most people never read the manual.
