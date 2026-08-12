---
layout: post
title: "Skin Tone Generation"
description: "Generate diverse skin tones using OKLCH color space for natural hues and chroma in user avatar generators and customization tokens."
date: 2026-08-05
categories: [news]
youtube_id: jjyhw_EY1n0
---

Linear math in standard HSL color spaces breaks down the moment you try to programmatically generate skin tones or dynamic avatar palettes.

When building user avatar generators or customization tokens, engineers usually take a base hex code and tweak lightness in HSL. It works fine for bright UI accents, but human skin tones aren't linear. Standard color spaces shift hue unevenly, turning realistic shades muddy or washed out when scaled.

Switching to perceptually uniform spaces like OKLCH fixes the underlying color curves. It lets you programmatically adjust lightness while preserving natural hue and chroma across diverse palettes. (I once wrote an avatar generator that accidentally turned half our user base slightly gray in dark mode because I trusted standard RGB math.)

The trade-off is contrast management. Perceptually uniform skin tones look natural, but they don't automatically guarantee text contrast ratios. You still need explicit WCAG checks on top of any generated shades.

This week, inspect where your frontend generates dynamic user colors. Swap out standard HSL math for OKLCH in one component and compare the edge-case shades side by side.

## Sources

- [https://toneyalexander.github.io/inclusive-color-space/](https://toneyalexander.github.io/inclusive-color-space/)
