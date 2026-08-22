---
layout: post
title: "AliExpress WebAudio fingerprinting breaks Bluetooth multipoint"
description: "AliExpress loads hidden WebAudio contexts that stay active, causing Bluetooth multipoint headphones to stop switching back to the phone while the site is open."
date: 2026-08-20
categories: [news]
youtube_id: h7HbrmUXlNM
---

AliExpress’s homepage loads two hidden WebAudio contexts that run continuously and connect to the system audio output. The audio processing prevents Bluetooth multipoint headphones from switching back to a phone when the page is open.

## Why it matters

Software engineers need to be aware that silent WebAudio fingerprinting can interfere with audio routing on users’ devices, causing unexpected behavior. Users of Bluetooth multipoint headphones may experience audio dropouts or loss of device switching due to such background audio graphs. Blocking the responsible scripts with ad‑blocking filters can mitigate the issue but may affect anti‑fraud functionality on the site.

## The key fact

During an idle capture, the AliExpress homepage created two AudioContext objects that entered the running state and connected nodes to AudioContext.destination.

## Context

WebAudio fingerprinting is increasingly used by sites to gather device characteristics, and AliExpress employs it via obfuscated security scripts to augment their fraud‑detection and tracking mechanisms.

## Sources

- [https://blog.laserphile.com/2026/08/aliexpress-webpage-keeping-multipoint.html](https://blog.laserphile.com/2026/08/aliexpress-webpage-keeping-multipoint.html)
