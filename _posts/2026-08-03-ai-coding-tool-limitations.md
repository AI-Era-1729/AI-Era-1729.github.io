---
layout: post
title: "AI Coding Tool Limitations"
description: "Karpathy highlights LLMs failing simple spatial tasks, revealing AI coding tools struggle with edge cases and custom code, increasing bug risk."
date: 2026-08-03
categories: [news]
---

Measuring AI coding tools on standard boilerplate gives engineering teams a false sense of security.

Andrej Karpathy highlighted how LLMs fail on simple spatial tasks like rendering a pelican in SVG. They look brilliant until hit with an off-distribution prompt. We see this exact pattern in daily web development.

Generative tools crush basic React forms and REST endpoints. But hand them a custom state machine or layout edge case, and they output plausible garbage. (I spent two hours debugging an AI flexbox snippet that broke touch scrolling on mobile Safari.)

The trade-off is clear: these models speed up routine syntax, but increase the cost of lazy code reviews. If engineers stop reading generated diffs carefully, subtle architectural bugs slip through.

This week, test your AI assistant on your codebase's most awkward edge case instead of clean greenfield boilerplate. Find its blind spots before trusting it with sprint commits.

## Sources

- [https://twitter.com/karpathy/status/2083749667410727319](https://twitter.com/karpathy/status/2083749667410727319)
