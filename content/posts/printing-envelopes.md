---
title: "Printing on Envelopes"
date: 2022-12-04T20:21:31-05:00
---

I needed to print addresses on 40 A7 envelopes today. It's been a while since I printed on anything besides US Letter, and I'm unhappy to report that it's no less ridiculous than it was 15 years ago.

Generating the 40 envelopes with mail merge was easy enough. The rest was not:

1. A7 envelopes, at 5.25" tall by 7.25" wide, are not a preconfigured paper size in macOS. I add a new page size with those proportions, but macOS paper settings expect paper to be taller than it is wide, so orienting my new paper size with "portrait" setting makes it wider than it is tall, and "landscape" makes it taller than it is wide. I reverse my initial inputs to correct this.
1. The printer tray has a diagram indicating that paper should be placed face-down, but there's no indication of how to rotate paper that was fed in "landscape" like mine. With a 50/50 chance of getting it right, the test envelope came out 180º from the correct orientation. Modern macOS print dialogs show all sorts of printer-specific information inline. I wish they went a step further and prompted the user with guidance like, "feed paper face-down and with the top edge to the right".
1. Flipping the envelopes made the address print in the correct orientation, but inexplicably several inches off target. I try several permutations of different margins, page dimensions, portrait/landscape configurations. None print what I see in the print preview.
1. Reasoning that the printer can print on letter paper, and knowing where envelopes feed into the printer relative to a sheet of letter paper, I reformat the entire document to the dimensions of a letter page, with the addresses superimposed. I print one to test, and it works!
1. Victory, right? I print the rest. The first envelope in the batch prints wildly off target, mostly off the page, and then the printer stops due to a media error.
1. I resort to opening the print dialog 40 times in a row, printing one page at a time each time.

Final step: Contemplate whether hand-addressing the envelopes would have been quicker.

---

Post script: I said that mail merge itself was easy, but I forgot that it actually was not. I tried doing the merge in Apple Pages, and per the Pages help website, there should have been a button under the Document tab in the sidebar to configure mail merge. The button was not there, and the help page gave no hints about how to make it appear. I ended up recreating the layout in Word.
