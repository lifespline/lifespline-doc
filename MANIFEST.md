- [About](#about)
- [The Manifest](#the-manifest)
  - [Play](#play)
    - [Example 1 - Promises, promises...](#example-1---promises-promises)
  - [Serenity And Focus](#serenity-and-focus)
    - [.git](#git)
      - [Example 1](#example-1)
    - [SDK](#sdk)
      - [Example 1](#example-1-1)
  - [Coding](#coding)
  - [Mouse](#mouse)
  - [Laptop](#laptop)
  - [Monitor](#monitor)
  - [Sitting](#sitting)
  - [Sleeping](#sleeping)
  - [Sports](#sports)
  - [UI And UX](#ui-and-ux)
  - [Context Changing Is Expensive](#context-changing-is-expensive)
    - [Example 1](#example-1-2)
  - [Remote Is Heaven](#remote-is-heaven)
    - [.git](#git-1)
  - [Semantic Versioning](#semantic-versioning)
  - [Log Your Changes](#log-your-changes)
  - [Humanity](#humanity)
    - [Open-Source Community, Democracy, Freedom, Responsability](#open-source-community-democracy-freedom-responsability)
  - [The Ocham's Razor](#the-ochams-razor)
  - [Versioning And Control](#versioning-and-control)
  - [Eh... What's up, Doc?](#eh-whats-up-doc)
  - [Don't Multiply Beyond Necessity](#dont-multiply-beyond-necessity)
    - [.git](#git-2)
    - [LOC And Refactoring](#loc-and-refactoring)
  - [See-To-Believe](#see-to-believe)
    - [Example 1](#example-1-3)
  - [Love-Averse: A History Of Decoupling](#love-averse-a-history-of-decoupling)
    - [Example 1](#example-1-4)
  - [Beauty](#beauty)
  - [Automation](#automation)
    - [.git](#git-3)
    - [doc](#doc)
      - [Example 1](#example-1-5)
    - [SDK](#sdk-1)
      - [Example 1](#example-1-6)
  - [Time-Driven-Development](#time-driven-development)
    - [Example 1](#example-1-7)

# About

Coding is a *way of life*, i.e., it is an activity a person dedicates his/her's life to. The activity has a set of principles that enables the **developer** to be extraordinarily happy by dedicating his/her life to this activity. The [manifest](#the-manifest) contains a non-exhaustive set of principles for *Coding*.

# The Manifest

## Play

It's fundamental to let **play** drive the coding. It's through play that the developer master its' craft.

### Example 1 - Promises, promises...

Learning to use the AWS SDK V3 JS, I came accross the notion of `promises` and then `asyn/await` + `Promise.then.catch` patterns. It was great dedicating some time to play with it to get a good grasp of what it is. If I'm doing [time-driven-development](#time-driven-development), I could never play without a guilty consciousness. Play requires [serenity-and-focus](#serenity-and-focus).

[⌂ home](#about) / [the-manifest](#the-manifest)

## Serenity And Focus

Writing code is a creative and a learning activity. It requires a fair amount of constant focus, and focus requires serenity. These two forces provoke happiness.

### .git

Having your solutions pushed to a remote server provide **serenity**. Without a remote server, you can never trust your local copy will survive and eventuality.

#### Example 1

I was on the wrong AWS profile, that's why the lambda wasn't showing up on the list. I was relaxed however, I knew things had deployed through code, so it would simply be a matter of redeploying the solution.

### SDK

Having your solutions written in code provide **serenity**. Without the SDK, you can never trust recovering from a manual deployment.

#### Example 1

I was on the wrong AWS profile, that's why the lambda wasn't showing up on the list. I was relaxed however, I knew things had deployed through code, so it would simply be a matter of redeploying the solution.

## Coding

In the future we'll have devices reading biometric signals and outputting code based on our thoughts. For now, we have to use our hand fingers to insert code characters in a source file. The keyboard is a device adapted to our human hands. Typing is a very cumbersome and slow process, so it's very important to choose a great quality keyboard.

[⌂ home](#about) / [the-manifest](#the-manifest)

## Mouse

[⌂ home](#about) / [the-manifest](#the-manifest)

## Laptop

[⌂ home](#about) / [the-manifest](#the-manifest)

## Monitor

In the future we'll have AR devices in controlled environments showing the code based in an incredibly immersive and 3D UX. For now, all the information is shown in **windows** on a LED wall called a monitor. Moving windows around is very cumbersome

we have to use our hand fingers to insert code characters in a source file. The keyboard is a device adapted to our human hands. Typing is a very cumbersome and slow process, so it's very important to choose a great quality keyboard.

[⌂ home](#about) / [the-manifest](#the-manifest)

## Sitting

[⌂ home](#about) / [the-manifest](#the-manifest)

## Sleeping

[⌂ home](#about) / [the-manifest](#the-manifest)

## Sports

[⌂ home](#about) / [the-manifest](#the-manifest)

## UI And UX

[⌂ home](#about) / [the-manifest](#the-manifest)

## Context Changing Is Expensive

It's very expensive to change contexts, avoid this if possible. **It's not worth it multi-tasking. On the long run, the productivity decreases**.

### Example 1

I was wokring on documentation, and I receive an email regarding a check on the logic of a dataset. The email had two paragraphs. Reading the email alone required changing contexts. I did it, but now I'm out of the task I was doing before, and I can go back to it immediately, but I feel a sort of **fatigue** being exerted upon me simply by changing contexts. **It's not worth it multi-tasking. On the long run, the productivity decreases**.

[⌂ home](#about) / [the-manifest](#the-manifest) / [context-changing-is-expensive](#context-changing-is-expensive)

## Remote Is Heaven

### .git

Never leave your local changes unstaged and unpushed. Its preferable to unstage them from the current branch and stage them onto a pushed new temporary branch.

## Semantic Versioning

## Log Your Changes

## Humanity

### Open-Source Community, Democracy, Freedom, Responsability


## The Ocham's Razor

## Versioning And Control

## Eh... What's up, Doc?

Document, document, document. For the sake of the community (clients), for the sake of your own understanding and your [serenity-and-focus](#serenity-and-focus), for the sake of [automation](#automation).

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


## Love-Averse: A History Of Decoupling

If a component seems to be decoupable, affect some time to decouple it. Examples:

### Example 1

Working on `hawk-ts-template`, I thought of adding some demos to the repo as to help people getting started with the template/bootstrap. As the examples became more complex, it immediately became apparent the examples should not reside in the repo itself, but on separate repos (I even began adding a script what would reset the repo once forked+cloned, and a README.md pointing out which values precisely would need/could change to automate the bootstrapping of a new project). I immediately submitted an **issue** to `hawk-ts-template` in hopes that the work would be completed sometime soon.

[⌂ home](#about) / [the-manifest](#the-manifest) / [love-averse](#love-averse)

## Beauty

Beauty is balance, power, efficacy, elegance. This is what guides the developer, not the end-result. The balance, the power, the efficacy, the elegance of process - and as a consequence - of the solution.

[⌂ home](#about) / [the-manifest](#the-manifest)

## Automation

Automation is one of the pillars of the manifest.

### .git

Having your solutions pushed to a remote server provides [serenity-and-focus](#serenity-and-focus). Without a remote server, you can never trust your local copy will survive any eventuality.

### doc

Documentation is a form of automation because it persists the extremely valuable high-level knowledge a developer retains when it is working on the solution. This knowledge deteriorates as time stars counting from the moment the developer last worked on the solution. See: [eh-whats-up-doc](#eh-whats-up-doc)

#### Example 1

I was on the wrong AWS profile, that's why the lambda wasn't showing up on the list. I was relaxed however, I knew things had deployed through code, so it would simply be a matter of redeploying the solution.

### SDK

Having your solutions written in code provide **serenity**. Without the SDK, you can never trust recovering from a manual deployment.

#### Example 1

I was on the wrong AWS profile, that's why the lambda wasn't showing up on the list. I was relaxed however, I knew things had deployed through code, so it would simply be a matter of redeploying the solution.

## Time-Driven-Development

It's an awful thing. Not unless somebody/something crucially depends on it, and nobody else can/is assigned to do it but you, - **never code with regards to time**. Coding is not meant to produce, coding is a way of life: **The Way Of The Developer**. Beautifully functional software is a product of **enjoying the process of writing code**, not a product of **trying to deliver the solution on time and according to the specs**.

[⌂ home](#about) / [the-manifest](#the-manifest)

### Example 1

A way I can get out of the stress of the **Time-Driven-Development** is to:
- allocate almost all my time to the activity of development
- get rid of the tasks at work ASAP without compromising too much on quality
- get rid of all compromises in life ASAP without hurting my loved ones
- My work is mine, my company's work is my company's

[⌂ home](#about) / [the-manifest](#the-manifest)