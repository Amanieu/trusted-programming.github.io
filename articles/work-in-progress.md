---
layout: post
title: Work in Progress to the Open Source Communities by Huawei Trusted Programming 
toc: true
---

* toc
{:toc}


Here is the list of opensource work in progress by huawei employees. If you want to look at the opensource contributions, take a look [here]({{ site.baseurl }}/articles/opensource-contributions.html).

### (rustdoc) Generate links to definition in rustdoc source code pages

This [pull request](https://github.com/rust-lang/rust/pull/84176) adds a the possibility to jump to an item definitions from the rustdoc source code pages (you can see a video in the pull request description). It got a lot of support from rust users as you can see from this twitter feed:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">I&#39;m very excited to show some feature I&#39;m working on in <a href="https://twitter.com/rustlang?ref_src=twsrc%5Etfw">@rustlang</a>&#39;s rustdoc: ever wanted to be able to jump to a type definition from the source code pages directly? It&#39;ll be possible soon! More to come! Here is a small preview: <a href="https://t.co/ICPXH35Q8V">pic.twitter.com/ICPXH35Q8V</a></p>&mdash; Guillaume Gomez (@imperioworld_) <a href="https://twitter.com/imperioworld_/status/1379506735094857728?ref_src=twsrc%5Etfw">April 6, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### (rustdoc/rust infra) Add new tool to check generated HTML

This [pull request](https://github.com/rust-lang/rust/pull/86059) adds a new test-suite to ensure that the HTML generated by rustdoc is valid. It's especially important for accessibility and prevent silent regressions.

### (rustc) Rework SESSION_GLOBALS API

Thanks to [this pull request](https://github.com/rust-lang/rust/pull/84953), we realized that the `SESSION_GLOBALS` API allowed to do invalid operations, messing up the spans. This [pull request](https://github.com/rust-lang/rust/pull/84961) fixes it by preventing to access the global static directly.

### (rustc/infra) Enforce error codes checks

The Rust compiler uses error codes (which look like "E0111") and provide an explanation alongside them which can be seen using `rustc --explain E0111`. However, as time passes, some error codes are not used anymore and are often not cleaned up correctly. This [pull request](https://github.com/rust-lang/rust/pull/86137) ensures that they are cleaned up appropriately if they are removed by sending an error when the `tidy` check is run.