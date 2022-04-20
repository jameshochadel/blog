---
title: "Writing Go with Sublime Text"
date: 2022-01-03T21:14:21-05:00
draft: true
---

I mostly write software in Go, and I write Go in Sublime Text on macOS. GoLand and VSCode are more common choices for Go development. These are my thoughts on Sublime and why I think it's a good match for Go.

# Why Sublime?

Sublime has been my editor of choice for about ten years. There are a few standout features, but the best one is the most basic: It's fast. The feeling of speed is informed by its performance and by its ergonomics.

In terms of performance, Sublime starts nearly instantly, switches projects with no delay, and scrolls files smoothly, an underrated and surprisingly rare feature in editors. Sublime's ergonomics are also excellent, in my opinion. Sublime is an unapologetically visual editor that makes good use of the mouse, having pioneered features like multiple selection (or at least made them mainstream). But it also lets you maintain flow from the keyboard with features like the Command Palette and Goto Anything, both of which support fuzzy matching. Goto Symbol in particular is tremendously valuable when exploring unfamiliar codebases, or jumping around quickly in familiar ones.

Lastly, Sublime's UI elements are very responsive. Despite using a custom UI library, the UI has always felt uniquely native to me. There are certainly some odd non-native paradigms to get used to. Preferences, for instances, are not configured via a UI, but are made available as a JSON file and modified right in the editor.

The upshot of all this quickness is that Sublime lets me work very close to the speed of thought.

Besides its speed, I find ST a good match for Go because it complements, rather than replaces, the CLI and CLI-based tools. `go` ships with excellent tools for formatting, profiling, and testing your code. Sublime integrates with many of them via the Build Systems feature, but I typically invoke them from the CLI. There's a minimal amount of IDE magic involved either way. Sublime does lack some clever features that GoLand includes, and while it is multiplatform, it has no web version or iPad version.

The last feature I like about Sublime is that I have a very clear relationship with the company that sells it. I pay Sublime HQ $99 USD, in return I got a license key and three years of updates. If I want to continue receiving updates in three years, I'll pay them again. Visual Studio Code is free, but Microsoft must believe that's to its benefit. Perhaps they get developer mindshare, or a common platform on which to build products like GitHub Codespaces and Copilot. Those things aren't bad, but the murkiness puts me off.

I'm glad that excellent free editors like VSCode exist; 'free' lowers the barrier to entry for new programmers, and that's a good thing. But once I started getting paid to code, I decided to start paying for a few tools that helped me improve my craft, and I haven't regretted it since.

Sublime feels like it is a good match for Go. The [go.dev](https://go.dev) website promises you can "build fast, reliable, and efficient software at scale" using Go, and the language accomplishes this in part by being deliberately simple and reliable itself.

# My Setup

Basics are Go and Sublime, as well as Package Control, the Sublime package manager. It's not installed by default, but can be installed from inside the app. I'm on the dev channel; not easy to find.

The key is Sublime LSP and `gopls`.

* Install `gopls`, the LSP-compatible Language Server for go. Instructions [here](https://go.googlesource.com/tools/+/refs/heads/master/gopls/README.md), or simply run:

```bash
go install golang.org/x/tools/gopls@latest
```

LSP-gopls connects the two.

Other plugins:

* Golang Build
* gomod
* SidebarEnhancements

Settings:

* Go


* Sublime plugins
	* SublimeLSP
* Sublime settings?
	* Also LSP settings, like format on save
* Possibly get on the dev channel, discord

# Using Sublime

* Most helpful shortcuts
	* Project > Save As
	* Mapping cmd+shift+o to "Switch Project", like "Switch Repo" in Merge
	* Sublime has a built-in spell check! Cmd+shift+? to get MacOS menu search > "Spell Check"
	* `cmd+,` to edit settings
		* Approach to settings: Everything you can adjust is on the left. Look through it like you'd look through a normal settings page. When you find something you want to change, add an entry on the right.
* Build system
	* Still exploring
	* Hugo though, custom build system for this!

# Bugs, Pitfalls, and Shortcomings

* Sublime
	* Fullscreen with MacOS and native tabs buggy for years
	* Sidebar, no drag & drop
	* $PATH
* LSP
	* Have to restart after running go generate, doesn’t pick up changes automatically
	* Autocomplete menu disappearing after doing X
	* Top autocomplete option changing after typing out exact how it starts
	* Enter sometimes fills autocomplete, sometimes inserts a newline
	* Weird formatting behavior when structs are missing a comma somewhere
	* Can't complain, it's free!
