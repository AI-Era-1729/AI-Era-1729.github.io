---
layout: post
title: "SQLite WAL-Reset Bug: Tailscale Database Corruption"
description: "Tailscale's investigation into repeated control plane database corruption uncovered a 16-year-old WAL-reset concurrency bug in SQLite's source code."
date: 2026-08-12
categories: [news]
youtube_id: 81wkbTZMZ-c
---

Tailscale investigated repeated control plane database corruptions and helped SQLite developers identify a rare data race in SQLite's source code. The issue, dubbed the "WAL-Reset bug," occurred when a write transaction intersected with a checkpoint, causing uncopied database pages to be permanently lost.

## Why it matters

Database corruption forced Tailscale to halt control plane shards during repairs, temporarily blocking new devices from joining mesh networks. The bug demonstrates how obscure concurrency flaws can remain hidden for over a decade in widely trusted database software. Software engineers who take manual control of SQLite checkpointing must adopt the fix to prevent silent data loss.

## The key fact

Tailscale experienced 19 separate instances of database corruption over six months before helping SQLite developers isolate the bug, which had been present in SQLite for at least 16 years.

## Context

Tailscale has used SQLite as its primary control plane database since 2022, taking manual control of the WAL checkpoint process to facilitate automated backups to Amazon S3.

## Sources

- [https://tailscale.com/blog/sqlite-wal-reset-bug](https://tailscale.com/blog/sqlite-wal-reset-bug)
