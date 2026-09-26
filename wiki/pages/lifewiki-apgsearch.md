---
title: "LifeWiki: apgsearch"
category: Sources
summary: LifeWiki's article on apgsearch, Adam P. Goucher's Ash Pattern Generator Search - how it runs 16 × 16 soups and classifies the ash, its symmetric and inflated soups, GPU searching, the rule families it supports, its limits, notable discoveries, and its version history from Golly Python scripts to the C++ lifelib-based apgluxe
tags: [source, lifewiki, apgsearch, soup-search, census, catagolue, software]
sources: [lifewiki-apgsearch]
created: 2026-09-25
updated: 2026-09-25
---

# LifeWiki: apgsearch

**Source:** raw/lifewiki-apgsearch.md, saved from https://conwaylife.com/wiki/Apgsearch
**Date ingested:** 2026-09-25
**Type:** wiki article

## Summary

Describes [[apgsearch](pages/apgsearch.md)], the program that feeds
[[catagolue](pages/catagolue.md)].[^1]
- **What it does.** Runs random 16 × 16 soups to stability and classifies the ash:
  still lifes, oscillators, spaceships, linear growth, unusual growth, and in Life also
  methuselahs, diehards and very large final populations.
- **Soup shapes.** Symmetric soups (C2, C4, D2, D4, D8 families), long thin soups, and
  "inflated" soups; a GPU mode pre-screens soups and censuses only interesting ones.
- **Beyond Life.** Outer-totalistic, isotropic non-totalistic, higher-range, Larger than
  Life, hexagonal, Generations and B0 rules, and custom Golly rule tables.
- **Limits.** Object separation can fail for large groups; periods above 1,048,576 are
  "PATHOLOGICAL".
- **Finds.** The first natural nonstandard flotilla, the pufferfish, 112P15, the
  long-lived methuselahs, and Rob's p16.
- **Versions.** 0.x-1.x were Python scripts for Golly; 2.x-5.x are C++ (apgnano, apgmera,
  apgluxe), with 5.x adding CUDA.

## Entities & Concepts

- [[apgsearch](pages/apgsearch.md)], [[catagolue](pages/catagolue.md)], [[soup-search](pages/soup-search.md)], [[methuselah](pages/methuselah.md)], [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)], [[larger-than-life](pages/larger-than-life.md)], [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)], [[ruleloader](pages/ruleloader.md)]

[^1]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L15-212 [synthesis] - introduction, higher symmetries, GPU searching, notable patterns, other rules, limitations, version history
