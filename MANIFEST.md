- [About](#about)
- [The Manifest](#the-manifest)
  - [Semantic Versioning](#semantic-versioning)
  - [Log Your Changes](#log-your-changes)
  - [Humanity](#humanity)
    - [Open-Source Community, Democracy, Freedom, Responsability](#open-source-community-democracy-freedom-responsability)
  - [The Ocham's Razor](#the-ochams-razor)
  - [Versioning And Control](#versioning-and-control)
  - [Don't Multiply Beyond Necessity](#dont-multiply-beyond-necessity)
    - [.git](#git)
    - [LOC And Refactoring](#loc-and-refactoring)
  - [See-To-Believe](#see-to-believe)
    - [Example 1](#example-1)
  - [Love-Averse](#love-averse)
    - [Example 1](#example-1-1)
  - [Time-Driven-Development](#time-driven-development)
    - [Example 1](#example-1-2)

# About

The guide showcases a set principles with which the developer could develop software solutions.

# The Manifest

## Semantic Versioning

## Log Your Changes

## Humanity

### Open-Source Community, Democracy, Freedom, Responsability


## The Ocham's Razor

## Versioning And Control

## Don't Multiply Beyond Necessity

### .git

Commit titles should be systematic and converge to a finite list of possible values.

### LOC And Refactoring

Abstain from having the same logic twice in the same file. Unless unpractical, abstain from having the same logic twice in your project. Unless unpractical, abstain from having the same logic twice in all the projects you'll work with in the course of your career.

[⌂ home](#about) / [the-manifest](#the-manifest)

## See-To-Believe

When you're learning something, **don't read and believe**, you'd rather **see to believe**. Technology is not science, systems are hardly deterministic. When you're learning, always do a POC on the side to verify what's really working.

Ideally, you'd then merge this knowledge with your existing knowledge by creating an industry-standardized demo, and you would contribute to the open-src technology at least with an issue, at the best with a PR.

### Example 1

I wasn't succeeding on deploying a nodejs docker image (`ENTRYPOINT ["handler.handler"]`) to an AWS ECR registry with a TS app and executing the container successfully from an AWS lambda. I was exporting the app's function `async handler` as a `default export handler;` and the lambda would keep throwing the error:

```
handler.handler not in $PATH
```

I thought of giving up, *'It's OK, you're almost there, just focus on something else now.'*. Sometimes these are words of wisdom, but frequently they will force you to don't come up with a solution, and you'll never feel you've **Seen-To-Believe**, you won't feel **ownership on the knowledge** you've adquired.

[⌂ home](#about) / [the-manifest](#the-manifest) / [see-to-believe](#see-to-believe)


## Love-Averse

If a component seems to be decoupable, affect some time to decouple it. Examples:

### Example 1

Working on `hawk-ts-template`, I thought of adding some demos to the repo as to help people getting started with the template/bootstrap. As the examples became more complex, it immediately became apparent the examples should not reside in the repo itself, but on separate repos (I even began adding a script what would reset the repo once forked+cloned, and a README.md pointing out which values precisely would need/could change to automate the bootstrapping of a new project). I immediately submitted an **issue** to `hawk-ts-template` in hopes that the work would be completed sometime soon.

[⌂ home](#about) / [the-manifest](#the-manifest) / [love-averse](#love-averse)

## Time-Driven-Development

It's an awful thing. Not unless somebody/something crucially depends on it, and nobody else can/is assigned to do it but you, - **never code with regards to time**. Coding is not meant to produce, coding is a way of life: **The Way Of The Developer**. Beautifully functional software is a product of **enjoying the process of writing code**, not a product of **trying to deliver the solution on time and according to the specs**.

### Example 1

A way I can get out of the stress of the **Time-Driven-Development** is to:
- allocate almost all my time to the activity of development
- get rid of the tasks at work ASAP without compromising too much on quality
- get rid of all compromises in life ASAP without hurting my loved ones
- My work is mine, my company's work is my company's

[⌂ home](#about) / [the-manifest](#the-manifest)