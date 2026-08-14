---
layout: post
title: "How Database Indexes Work: Read vs Write Performance"
description: "A database index replaces slow full table scans with sorted lookup maps and memory pointers, reducing query execution time while adding write overhead."
date: 2026-08-12
categories: [evergreen]
youtube_id: 9ADgPCNHHqU
---

You do not read a seven-hundred-page textbook line by line just to find one definition. You flip to the index at the back, find the topic alphabetically, get the page number, and open directly to it.

A database works the exact same way. When a database table — an organized grid of stored data — grows to millions of rows, searching for a single record takes time. Without help, the database engine runs a full table scan, meaning it inspects every single record one by one from start to finish.

When you add an index — a small, sorted lookup map pointing to the exact location of each record — the work drops instantly. Instead of checking a million entries, the database reads the index, gets the target memory address, and jumps straight to that single row.

The trade-off is write performance. Every time you insert or update a record, the database must re-sort its index. Adding too many indexes slows down writes to keep reads fast.

You now understand why a database index turns a slow, page-by-page scan across millions of records into an instant jump to the exact location.

Have you ever added an index that fixed a slow query but unexpectedly degraded write performance elsewhere in your system?

## What a database index actually does

Flipping to the back instead of reading every single page.

## Scanning every page takes too long

Searching without an index forces the database to inspect every single record from start to finish.

## An index is a sorted lookup map

It stores key values alongside precise pointers, letting the database jump directly to the target record.

## Faster reads mean slower writes

Every new entry forces the database to re-sort its index, making write operations slightly more expensive.

## Query time drops from seconds to milliseconds

Small lookup maps eliminate full scans, keeping huge applications responsive under heavy user traffic.
