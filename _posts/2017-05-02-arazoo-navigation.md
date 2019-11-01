---
layout: post
date: 2017-05-02
title: 'Rebuilding Arazoo part 1: navigation'
---

Hiring our new CTO, Peter Stern, back in early 2017 was an excellent opportunity for us at Arazoo to reexamine some of the design decisions that were made early on but were no longer carrying their weight. Peter was fresh to our org and had no emotional ties to our existing code. Whereas I'd had problems in the past getting user testing and user experience at the front of the process, Pete naturally gravitated towards the "let's go talk to people" side of things.

## Too much execution, not enough learning

Because we had been working in "execution" mode rather than in a "lean" learning-oriented way, our product had become sort of a palimpsest of compromises. We wanted to build Large Featureset X, but technical limitations, time (that is, budget) limitations, or both meant we built Y, which is sort of like X, but with fewer features. Meanwhile, we didn't run any of this by our users or even think about the notion of what an MVP of that solution might really look like.

Then in a subsequent sprint, we would manage to add some more of X to Y. Along the way, someone might have an idea elsewhere that has design ramificaitons that ripple throughout the product. What we wanted to be X, and built as Y, now becomes Z. It's _okay_, but it's a feature that was born from outside constraints rather than purpose-built to serve a user need.

And more importantly, it's not really something we ever tested on users, or even built because they said they needed it.

Navigation in the Arazoo web app had been one of these ~~X~~ ~~Y~~ Z features.

In the original MVP that was developed for our founders by consultants, the feature set was small enough and the data scarce enough that navigation was able to be functional and superficial at the same time. There were only a couple different things you could do: Be on your firm homepage, go into a project, create a product, and invite new users.

As the features in Arazoo grew and gained complexity, navigation was scaled to accommodate it. More and more functionality (even editing some kinds of data) were squeezed into the nav.

We found from session playback in FullStory that users were often confused by our navigation. They weren't able to get to the features that could help them, so they would just give up and abandon.

At the time, there were a few major things in Arazoo that a user could access:

- the "Global Library," a collection of all the public products all Arazoo users had saved from the web. It had category-based subnavigation.
- the "Firm", a user's team. This had a few subnav items as well: 
  - the "Firm Library" was the collection of that firm's products
  - the "Firm Projects" page, where that firm's projects (collections of products that will be used together for a construction project) were gathered. 
- the "Personal Library," a user's personal list of products

In addition to these, we had various marketing pages:

- the homepage
- the pricing page
- a team page
- a product explainer page
- a link to our FAQs

All of the above items were packed into _one settings menu_ in Arazoo at the time. We had a top nav bar that displayed the breadcrumb for your current page, and you used this settings menu to hop to different places.

You _also_ used this settings menu to edit some kinds of data:

- your user display name and image
- your firm's display name and image
- project names
- workspace (i.e., folders inside a project) names

![](/images/2018/05/13/old-nav.png)

###### see that "settings" icon in the top left? That's where everything lived.

It was... sort of a mess. There was a huge amount of importance placed on that one affordance, and a mix of navigational and functional features.

##Fixing it, part one: talking to users

One major difference was that for the first time, we _went to talk to users about it_. Our users told us what we already observed from FullStory: the nav was confusing. But more importantly, they told us how it confused them; they let us watch them get confused; and they asked for things.

People like to toss around that old Henry Ford quote:

> If I had asked people what they wanted, they'd have asked for a faster horse.

But honestly: yes. It's not terrible if people ask you for a faster horse, as long as you can ask some _whys_ to get to the bottom of it. People ask for a faster horse because they want to go faster, and they're used to horses. It's the going faster you need to solve. 

So when our users asked for things in our nav, we thanked them for their suggestions then asked them _why they wanted that_. And generally it was all about orientation. Our users wanted to know where the heck they were in our site. The wanted to be able to quickly intuit how to get from one place to another. 

We took their feedback and our observations and mocked up some solutions. For example:

![](/images/2018/05/13/new-nav-1.png)

###### the first round of design improvements

In this early mockup, I did several things:
- moved the settings icon to the right, where people expect settings stuff to be
- gave four obvious navigational anchors:
  - the brand icon takes you to the homepage
  - Products goes to the All Products page (we rebranded the "Global Library" because... well, "All Products" is what it actually contains)
  - Libraries is a dropdown with all the libraries you have access to
  - Projects is a dropdown with all the projects you have access to
- a secondary nav bar is there to hold in-page search and sorting
- knowing where you are is handled with an underline on the top-level bucket you're in, plus an H1 on the page

We got some positive feedback on this one when we shopped it around to users as just a static image, but they pointed out that this was focused entirely on the app, and didn't really address the need or desire to check out the static marketing pages. 