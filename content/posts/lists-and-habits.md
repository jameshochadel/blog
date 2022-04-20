---
title: "Make Lists, Build Habits, Get Un-Stuck"
date: 2022-04-20T12:39:29-04:00
---

Today I nearly got stuck while learning something new. In the early years of my programming career, I got stuck all the time. Now, I rarely do. I thought I'd write about how I got from there to here, using today's experience as a representative example of what often happens when I'm learning something new.

My goal today was to create a GraphQL server using Go. I've used Go professionally for three years but only built APIs in the RESTful style, and those were coded largely by hand. Motivated by Dan Luu’s [In Defense of Simple Architectures](https://danluu.com/simple-architectures/), in which (among other things) Dan enumerates some benefits of GraphQL over REST APIs, I set about looking for libraries or tools that would generate Go code from a GraphQL specification.

After some searching, I found [this podcast episode](https://changelog.com/gotime/218) about GraphQL libraries and decided to check out [gqlgen](https://gqlgen.com). I visited the gqlgen documentation website and start going through the tutorial.

Gqlgen works by generating code, which is common in the Go ecosystem. You write a GraphQL Schema and gqlgen generates Go code representing the schema’s objects, queries, and mutations for you. This sounds similar to another package I like, [sqlc](https://sqlc.dev), which generates Go code from SQL. In both cases, the package uses a statically-typed schema to generate predictable Go code. That’s promising — I’m hoping to improve velocity by reducing redundant work, and hand-writing Go code to match a GraphQL schema that is already well-defined would definitely be redundant.

Not only had I not used gqlgen before, I'd only used GraphQL once or twice, and a few things confused me as I went through the tutorial. For instance, I'm not sure how GraphQL queries translate to database queries and whether a client can make arbitrary queries, or only one of a preset selection of queries. I know GraphQL is supposed to be very flexible, so the former seems more likely, but it’s not clear how that works.

I also have a nagging feeling that there is a simpler way to do what I’m currently doing. Sqlc generates type-safe Go code from SQL, since SQL itself is already statically typed. Couldn’t I generate a GraphQL schema and code from a database schema, further reducing my work?

A search online leads me to [Hasura](https://hasura.io), a hosted service that does exactly this. Generating a GraphQL API from a relational database should be even faster than my current approach since I wouldn't have to resolve SQL entities to GraphQL objects by hand. In my quest to reduce redundancy and improve velocity, this is even more promising! But is Hasura purely a hosted service? Does it expose the code that it generates? Can it generate Go?

I have unanswered questions about gqlgen and GraphQL, and now I also have questions about Hasura. There are more questions than I can hold in my head at once, so I cannot reason about them all at the same time. Should I bother with gqlgen when I think Hasura might cut out additional steps? Maybe, but I don’t want to leave my gqlgen exploration unfinished. Crap. I am close to getting stuck.

---

I got stuck very often as an undergraduate and during my first few years as a software engineer. Learning how to get un-stuck was probably the number one most difficult "meta-skill" I needed to learn. Learning how to avoid getting stuck was difficult for me because I had avoided it for so long. I worked around areas that I didn't understand and I procrastinated, and along the way I came up with a variety of rationalizations for my struggles. Once I got into the habit of rationalizing and blaming external factors for my lack of progress, it became easier and easier to get stuck and not learn.

My “one simple trick” for avoiding getting stuck is making lists. While exploring GraphQL, I was (almost) stuck for two reasons, and I made two lists so I could keep moving forward.

First, I was in danger of getting stuck because I had too many unanswered questions. Once I have more than three or four open questions, I can't keep them all in my head at once. To fix this, I made a list of my questions.

I put the list in my developer journal. My developer journal is a folder of markdown files, one file per day, with the date in the filename. I write down anything I think is especially novel to me or that I think will be important later.

Second, I was stuck because I wasn’t sure what to do next. I solved this by making a list of my goals. I wanted to know something like the following:

1. What would Ruby on Rails look like if it was written idiomatically in Go?
1. What is the fastest I could possibly write a web application with a UI and API in Go?
1. ...that is as statically typed as possible? (No `any`, no writing SQL queries using strings.)
1. ...that has a small number of dependencies?
1. ...that is simple and high quality? Where high quality means relatively bug-free, and designed to make it easy to add bug-free code (the ["pit of success"](https://blog.codinghorror.com/falling-into-the-pit-of-success/)).
1. ...with a little “magic” as possible? Examples of magic might be global variables that are set by a framework in a way I don’t understand, or an ORM’s query generator, which produces queries for reasons I don’t easily understand.

With my goals and requirements listed out, I can think about my options more clearly. Hasura seems like it would save me time by fully generating a GraphQL API from a database schema with little or no extra work, but I don’t think it is available as a library, only as a hosted service. It would add an external dependency and at least some magic. My ideal tool would work like sqlc, generating code that’s local to the project and easy to understand. Even though it probably incorporates some good ideas, it probably isn't a good candidate for building a Rails-in-Go. I make a note open an account and play around with the service, but to direct my search elsewhere.

---

My exact questions and priorities aren’t the point of this post, though if anyone reading this has ideas about what a Rails-in-Go would look like, I’m all ears. In both cases, the act of writing helped clarify my questions and my goals. Writing down my questions means I can revisit them later as needed instead of having to answer them all right now. And writing down my priorities helps me choose a direction for further exploration and learning. Without listing my priorities, I easily fall victim to analysis paralysis.

That making lists is a valuable habit will not be news to most engineers. In fact, I expect that most professionals and academics write down ideas and make lists without conscious effort! For instance, after I started my developer journal, I remembered that many scientists keep a lab notebook where they detail their findings and questions every day.

Regardless of what other people do, I had to deliberately build the habit of making lists. It was a lesson learned the hard way. I suspect other engineers getting started in their schooling or careers may need to learn it too. And in my experience, it never hurts to be reminded of the basics of any skill.

The phrase "*build the habit* of making lists" is intentional. It is not enough to "know" that writing down your questions and goals is valuable. You must actually build the habit of doing so. In the style of Cognitive Behavioral Therapy, you must find a trigger with which to associate the action of opening up a note or grabbing a piece of paper to write things down. For me, the most valuable triggers have been feelings. Whenever I [feel stupid](https://danluu.com/look-stupid/) — a distinct mental sensation of fogginess, denseness, and frustration — I reach for a list and write down the things that are confusing me. Whenever I feel the satisfaction of solving a problem or understanding a new concept, I make a new entry in my developer journal and record what I learned so I may reference it later.

I firmly believe that the only way for most people to learn is by doing. Building habits as I describe here is a specific case of learning by doing. If such things interest you and you would like further reading, I suggest:

* [*The Now Habit*](https://www.amazon.com/Now-Habit-Overcoming-Procrastination-Guilt-Free-dp-1585425524/dp/1585425524/ref=dp_ob_title_bk) by Nick Fiore, PhD., for great practical advice on the subject.
* [*Thinking, Fast and Slow*](https://www.amazon.com/Thinking-Fast-Slow-Daniel-Kahneman-ebook/dp/B00555X8OA) by Daniel Kahneman for a more academic and in-depth but supremely interest read on how we think. (Habits are of System 1, and building habits is achieved using System 2).
