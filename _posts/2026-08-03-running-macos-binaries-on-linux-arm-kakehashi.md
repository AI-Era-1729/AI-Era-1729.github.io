---
layout: post
title: "Running macOS Binaries on Linux ARM: Kakehashi"
description: "Kakehashi translates macOS Mach-O binaries to run on Linux ARM, offering a path to reduce Mac CI costs despite current ABI and syscall translation limits."
date: 2026-08-03
categories: [news]
youtube_id: rUjx26ppYk8
---

Running macOS workloads on Linux infrastructure sounds like an academic exercise until you look at your cloud bill for Mac build instances.

Projects like Kakehashi translation layers show how close we are to running Mach-O binaries directly on Linux ARM nodes. But running a binary in userspace isn't full OS compatibility.

You quickly hit missing framework ABIs, complex dynamic linking edge cases, and untranslated system calls. (My own early cross-platform build experiments usually ended with me giving up and spinning up another overpriced Mac EC2 instance.)

These tools aren't ready to replace your iOS build farm tomorrow. But as userspace translation matures, our reliance on dedicated macOS hardware in CI will shift from a permanent requirement to a temporary technical debt.

This week, audit your team's CI costs and count how many hours are spent waiting on specialized Mac runners versus standard Linux workers.

## Sources

- [https://github.com/wie-project/kakehashi](https://github.com/wie-project/kakehashi)
