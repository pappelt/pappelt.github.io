---
layout: post
title: "Get a file from another branch or commit"
date: "2015-10-10"
tags: git
---
As Jason Rudolph states in an [article][0] `git checkout` actually accepts any tree-ish here. So you're not limited to grabbing code from the current tip of a branch; if needed, you can also check out files using a tag or the SHA for a past commit.

**Example**

`git checkout source_branch <paths>`

[0]: http://jasonrudolph.com/blog/2009/02/25/git-tip-how-to-merge-specific-files-from-another-branch/
