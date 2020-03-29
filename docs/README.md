# Twine Resources

This is a collection of resources and tools for use with [Twine](https://twinery.org/), an "open-source tool for telling interactive, nonlinear stories." The name "Twine" can refer to several different things: one of two applications, the type of story or game you make (e.g., a "Twine game"), and it often refers to the entire ecosystem of compilers, story formats, and tools designed to make said stories.

> [!NOTE]
> In this guide, when we refer to **Twine**, we will generally be talking about the entire ecosystem. If we mean the genre of IF that Twine produces, we will use the term ["CYOA"](https://en.wikipedia.org/wiki/Gamebook), and if we are talking about one of the Twine applications, we will say "Twine 1" or "Twine 2."

> [!TIP]
> If you have or know of resources that you'd like to see in this guide, open an issue or a pull request. Note that this list is *curated*, so if I have reservations about a resource or if it does not appear to work, I reserve the right to deny it.

## Contents

- [Compilers](#compilers)
- [Story Formats](#story-formats)
- [Tooling](#tooling)
- [Extensions and Libraries](#extensions-and-libraries)
- [Guides, Examples, and References](#guides-examples-and-references)
- [Communities](#communities)
- [Publishing Resources](#publishing-resources)

## Compilers

A Twine *compiler* refers to a program that takes your raw code and metadata: passage names, tags, source code, etc, and compiles it with a [story format](#story-formats) to generate a Twine game. There are two main types of compilers: [GUI](https://en.wikipedia.org/wiki/Graphical_user_interface) comilers and [CLI](https://en.wikipedia.org/wiki/Command-line_interface) compilers. Most beginners may prefer to use GUI compilers, as they more readily reflect the way most users interact with their computers, but CLI comilers typically offer more options and flexibility. While some CLI compilers can process JavaScript, CSS, HTML, and even published or archived Twine 2 files, you will commonly use [Twee notation](https://twinery.org/cookbook/terms/terms_twee.html) with these compilers.

There are also two *generations* of Twine compilers and story formats. First generation Twine compilers typically only work with first generation story formats, and second generation compilers typically only work with second generation formats. However, there is at least one compiler and a handful of story formats that work across both generations.

> [!NOTE]
> The term "generation" is, to my knowledge, an invention of this guide, not an official or widely accepted term.

|Generation|Compilers|Story Formats|
|---|---|---|
|**1**|Twine 1, Twee, Tweego|SugarCube, Sugarcane, Jonah, Snowman|
|**2**|Twine 2, Twee2, Extwee, Tweego|SugarCube, Snowman, Harlowe|

\*Note: the above table is not exhaustive.

### Twine 2

- [Website](https://twinery.org/)
- [Use Online](https://twinery.org/2)
- [Releases](https://github.com/klembot/twinejs/releases)
- [Repository](https://github.com/klembot/twinejs)

The currently maintained Twine GUI application. The recommended GUI compiler for most users. For second generation formats only.

### Twine 1

- [Website](https://twinery.org/)
- [Repository](https://github.com/tweecode)

The old, unmaintained Twine GUI. Only recommended for use with generation 2 formats that also support this compiler (e.g., SugarCube). The old formats that come with Twine 1 should no longer be used, especially for new projects. For first generation formats only.

### Tweego

- [Website](https://www.motoslave.net/tweego/)
- [Documentation](https://www.motoslave.net/tweego/docs)
- [Repository](https://github.com/tmedwards/tweego)

A CLI compiler. Works with formats from either generation. The recommended CLI compiler for most users. 

### Entwine

- [Entwine and Twine Utilities](https://github.com/klembot/twine-utils)
- [Grunt Entwine Quickstart](https://github.com/klembot/grunt-entwine-quickstart)

A node.js-powered CLI compiler made by the creator of Twine 2. For second generation formats only.

### Twee2

- [Website](https://dan-q.github.io/twee2/)
- [Documentation](https://dan-q.github.io/twee2/documentation.html)
- [Repository](https://github.com/Dan-Q/twee2)

Another CLI compiler. Works with Twine 2-style formats. Has slightly better interoperability with Twine 2 thanks to allowing for positional notation in the passage metadata, but its particular brand of Twee notation is not supported by any other compilers or tools. For second generation formats only.

### Extwee

- [Repository](https://github.com/videlais/extwee)

Another CLI compiler designed to work with second generation formats. Adheres to the [Twee3 specification](https://github.com/iftechfoundation/twine-specs/blob/master/twee-3-specification.md). For second generation formats only.

### Twee

- [Documentation](http://twee-twine-doc.tiddlyspot.com/)
- [Repository](https://github.com/tweecode/twee) 

The original CLI compiler for Twee. No longer maintained and not recommended for use by anyone anymore. For first generation formats only.

## Story Formats

A [**story format**](https://twinery.org/cookbook/introduction/story_formats.html) is the run-time engine for your Twine game. This choice is very important to how you'll approach development, what sort of features your game will have, and the way you'll write your code. A Twine compiler combines your source code, passages, and metadata with a story format to generate a complete, playable game.

### Core Formats

The "core" formats are the ones included with the Twine 2 application. These formats are still developed by third parties, but are more widely used, and typically better maintained, than other formats. The core formats are SugarCube, Harlowe, and Snowman. When using *any* format, you should always use the most recent possible version; older versions of formats are *only* included for compatibility with on-going projects and are not intended for use with new stories or games. <!-- wait to mention chapbook until it's out and in the core -->

#### SugarCube

- [Website](http://www.motoslave.net/sugarcube/2/)
- [Documentation](http://www.motoslave.net/sugarcube/2/docs/)
- [Repository](https://github.com/tmedwards/sugarcube-2)

SugarCube is a feature-rich, extensible, and simple story format. While in a few ways more complicated than Harlowe, SugarCube is still intended for beginners, but also comes with a variety of features and options for more advanced users as well. When choosing a format, **SugarCube is hard to go wrong with**. It may not always be the best fit, but it can always be adapted to work with whatever you have in mind.

#### Harlowe

- [Documentation](https://twine2.neocities.org/)
- [Repository](https://bitbucket.org/_L_/harlowe/)

Harlowe is a format designed for novices and is ideal for CYOA games with some dynamic content. If you want to build something more complex, like turn-based combat or inventory systems, Harlowe is generally not recommended. While simpler than SugarCube, Harlowe provides almost no options for extensibility; the core feature-set is largely all you have to work with. **Harlowe is ideal for authors who aren't looking to learn a lot about programming and just want to make a game**.

#### Snowman

- [Documentation](https://videlais.github.io/snowman/)
- [Repository](https://github.com/videlais/snowman)

Snowman is essentially just a link markup parser, a markdown parser, and a templating engine, with a few nuts-and-bolts APIs built in to handle passages and such. It is agressively minimal, requiring authors to build almost every bit of funcitonality they may need in JavaScript. **Snowman requires a great deal of knowledge of JavaScript (and general web development) to get anywhere with**. Even then, its thin feature set may still make it a poorer choice than the other core formats for many projects, even for developers with the know-how to make it work for them.

#### Chapbook

- [Website](https://klembot.github.io/chapbook/)
- [Documentation](https://klembot.github.io/chapbook/guide/)
- [Repository](https://github.com/klembot/chapbook)

Chapbook is designed to be simple to use. Compared to the other formats, it has the smallest feature set and is the most *opinionated* format. **Chapbook has some important limitations to consider, but if you can bend your ideas to fit its mold, it is probably the easiest format to learn.** Even if you have relatively large ideas, Chapbook is extensible, and there are ways to circumvent most of its limitations. However, it's simply not ideal for more complex ideas and mechanics. 

### Proofing and Utility Formats

Twine 2 introduced the concept of "proofing" formats; story formats designed to create more readable copies of your source code for proofreading and editing. "Utility" formats are a related concept that sprung up in the wake of proofing formats--typically these formats output Twine stories to some other useful format--JSON or Twee, for example, but there are many that do other cool things.

The default proofing format is [*Paperthin*](https://github.com/klembot/paperthin); it just shows your Twine file as a simple list of passage names and passage source code. Some community developed proofing formats, like [*Illume*](http://www.maximumverbosity.net/twine/Illume/) arrived later. Examples of utility formats include [*Entwee*](http://mcdemarco.net/tools/entwee/) and [*Enscree*](http://mcdemarco.net/tools/scree/enscree/).

### Other Formats

Many, many story formats exist. A catalogue of formats can be found [here](http://mcdemarco.net/tools/hyperfic/twine/catalog/), courtesy of [M. C. DeMarco](http://mcdemarco.net/). Many of these formats may not work, may be incomplete, or may not have ever been released, however. This list is *probably* not exhaustive, given that potentially thousands of bespoke and custom formats could exist across the web, just waiting to be discovered, but it is by far the best list of its kind.

#### Some Formats of Note

The following is a list of some third-party, non-core story formats that have been confirmed to work and are actively maintained.

##### Paloma (story format)

- [Website](http://www.mcdemarco.net/tools/scree/paloma/)

A Snowman-based story format that features stretch-text--that is, new passages are rendered below the old ones, rather than replacing them. By M. C. DeMarco.

##### Trialogue (story format)

- [Documentation](https://phivk.github.io/trialogue/)
- [Demo](https://phivk.github.io/trialogue/docs/trialogue-demo.html)
- [Repository](https://github.com/phivk/trialogue)

Trialogue is a chat-style Twine Story Format based on Paloma, which is in turn based on Snowman.

##### Adventures (story format)

- [Website](http://adventures.longwelwind.net/)

Adventures is a custom story format for Twine 2 made by Longwelwind that allows writers to add RPG elements such as health, items, golds and more to their story. 

##### Twine-Monotagari (story format)

- [Demo](https://haroldo-ok-2.github.io/twine-monogatari/v0.2.0/demo.html)
- [Repository](https://github.com/haroldo-ok/twine-monogatari/)

This Twine 2 story format allows one to use Twine to create Visual Novels for the Monogatari engine.

##### Entwee (utility format)

- [Website](http://www.mcdemarco.net/tools/entwee/)

Entwee is a one-time-use story format for exporting a Twine 2 story into the old twee format, based on Michael McCollum’s similar story format, Entweedle. By M. C. DeMarco.

##### Enscree (utility format)

- [Website](http://www.mcdemarco.net/tools/enscree/)

Enscree is a one-time-use story format for exporting a Twine 2 story into a MultiMarkdown format used for importing into Scrivener/Scree. By M. C. DeMarco.

##### DotGraph (utility format)

- [Website](http://www.mcdemarco.net/tools/scree/dotgraph/)

DotGraph is a proofing format that uses a JavaScript implementation of Graphviz to automatically lay out a Twine story as a layered graph. By M. C. DeMarco.

##### Illume (proofing format)

- [Website](http://www.maximumverbosity.net/twine/Illume/)

Illume is a proofing format for Twine 2 that offers more functionality than a simple text dump. Its primary purpose is to provide an interface for reviewing and editing passages in a workflow that allows an author to easily have another person, even someone who does not use Twine, proofread and provide edits to a story.

##### poof (proofing format)

- [Website](https://poof.twinelab.net)

Poof is a comment-based proofing format with a variety of utility features, like exports to Twee, PDF, and archive files.

!> **DISCLOSURE:** This resource was created by the primary author, maintainer, and curator of this guide.

## Tooling

"Tooling" is essentially any program or software that helps you make Twine stories that isn't a requirement (like a format or a compiler) and doesn't go on to become part of your game (like a library or script). A few of these tools are not designed *specifically* or *only* for Twine, but work with it all the same.

### HTMLE

- [Itch.io](https://gritfish.itch.io/htmle)
- [Repository](https://github.com/gritfish/HTMLE)

A suite of tools and software for releasing Twine games (and potentially other HTML-based games) to a variety of platforms and services. By Gritfish.

### Web2Executable

- [Releases](https://github.com/jyapayne/Web2Executable/releases)
- [Repository](https://github.com/jyapayne/Web2Executable)

A tool for turning web applications (including Twine games) into standalone hybrid applications using [NW.js](https://nwjs.io/).

### Electrify

- [Releases](https://github.com/jyapayne/Electrify/releases)
- [Repository](https://github.com/jyapayne/Electrify)

A tool for turning web applications (including Twine games) into standalone hybrid applications using [Electron](https://electronjs.org/).

### Tweego Installer (Windows)

- [Releases](https://github.com/ChapelR/tweego-installer/releases)
- [Repository](https://github.com/ChapelR/tweego-installer)

A Windows-only installer that simplifies installing Tweego.

!> **DISCLOSURE:** This resource was created by the primary author, maintainer, and curator of this guide.

### Tweego Installation Script (OS X)

- [Gist](https://gist.github.com/jsoma/5ef3045b2004a610455f371479a6f0cf)

A shell script for installing Tweego on MacOS.

### Tweego Setup

- [Repository](https://github.com/ChapelR/tweego-setup)

A boilerplate project and toolchain for creating Tweego porjects with [Node](https://nodejs.org/en/) and [Gulp](https://gulpjs.com/).

!> **DISCLOSURE:** This resource was created by the primary author, maintainer, and curator of this guide.

### Tweego Development

- [Repository](https://github.com/saltire/tweego-dev)

A Tweego development boilerplate.

### Tweego Webpack

- [Repository](https://github.com/DustinWoods/tweego-webpack)

A Tweego development boilerplate featuring [webpack](https://webpack.js.org/).

### Adventure Game Engine - Tweego

- [Repository](https://github.com/forkedlogic/AdventureGameEngine-TweeGo)

An adventure game engine based on Sugarcube 2 & TweeGo. An opinionated boilerplate for Tweego projects.

### TweeFly

- [Website](https://stonedrum.de/tweefly-interactive-fiction-made-easy/)

TweeFly is a tool for generating complex game systems in SugarCube and Twee2 without having to code them yourself. Available in both free and Patreon versions, the latter of which comes with a few extra bells and whistles.

## Extensions and Libraries

Since a great deal of web libraries can be made to work with Twine story formats (though it may take some doing), and since Snowman essentially requires *all* functionality to be built by the author (and I'm unaware of any specific libraries designed for it), this list will only include libraries, scripts, and extensions designed to work with either Harlowe or SugarCube, at least for now.

SugarCube is more extensible than Harlowe, so will have more scripts and extentions.

### SugarCube Libraries

#### Official Add-ons

- [Website](http://www.motoslave.net/sugarcube/2/#downloads)

The author of SugarCube maintains several external add-ons on the SugarCube website.

#### HiEv's UInv

- [Repository](https://github.com/HiEv/UInv)

An inventory system by HiEv. Probably the most full-featured inventory extension available for SugarCube.

#### Akjosch's SugarCube Modules

- [Repository](https://github.com/Akjosch/sugarcube-modules)

A collection of macros, functions, and other code bits for SugarCube by Akjosch.

#### Mike Westhad's SugarCube Resources

- [Repository](https://github.com/mikewesthad/twine-resources)

A collection of macros, functions, and other code bits for SugarCube by Mike Westhad.

#### Hogart's SugarCube Utils

- [Repository](https://github.com/hogart/sugar-cube-utils)

A collection of macros, functions, and other code bits for SugarCube by Hogart (Konstantin Kitmanov).

#### Chapel's Custom Macro Collection

- [Website](https://macros.twinelab.net/)
- [Repository](https://github.com/ChapelR/custom-macros-for-sugarcube-2)

A collection of macros, functions, and other code bits for SugarCube by Chapel.

!> **DISCLOSURE:** This resource was created by the primary author, maintainer, and curator of this guide.

#### TheMadExile's SugarCube Basic Internationalization Example

- [Gist](https://gist.github.com/tmedwards/33f3b4b7ada317fc9cc70aa8580c03f0)

A GitHub gist with code and examples for switching between two languages / localizations using the `Setting` API in a SugarCube project.

#### Harlowe-style Text Effects by Greyelf

- [Forum Post](https://twinery.org/forum/discussion/comment/14968/#Comment_14968)

A forum post by Greyelf providing the CSS for a variety of text effects in SugarCube, mirroring the effects available in Harlowe by default.

#### Right Sidebar by Greyelf

- [Forum Post](http://twinery.org/forum/discussion/comment/17617/#Comment_17617)

A forum post by Greyelf providing code to create and implement a second sidebar on the other side of the screen in SugarCube.

### Harlowe Libraries

#### Harlowe Audio Library

- [Website](https://hal.twinelab.net/)
- [Repository](https://github.com/ChapelR/harlowe-audio)

An audio library for Harlowe, designed to give it feature parity (or close to it) with SugarCube's built-in audio subsystems.

!> **DISCLOSURE:** This resource was created by the primary author, maintainer, and curator of this guide.

#### Harlowe Custom Macro API

- [Website](https://harlowe.twinelab.net/)
- [Macros](https://twinelab.net/harlowe-macro-api/#/examples/main)
- [Repository](https://github.com/ChapelR/harlowe-macro-api)

A framework for developing custom macros for Harlowe.

!> **DISCLOSURE:** This resource was created by the primary author, maintainer, and curator of this guide.

#### Harlowe Inventory System Example

- [Post](https://gersande.com/blog/designing-inventories-in-twine-2-with-the-built-in-harlowe-macros/)

A blog post detailing a potential method for implementing a simple, key-based inventory in Harlowe.

#### Harlowe Tag-based Styles by Greyelf

- [Forum Post (for v1)](https://twinery.org/forum/discussion/4797/basic-harlowe-passage-tag-based-styling)
- [Forum Post (ammendment for v2+)](https://twinery.org/forum/discussion/comment/21541/#Comment_21541)

A forum post by Greyelf providing a tag-based styles feature to Harlowe v1, with ammendments for Harlowe v2+.

## Guides, Examples, and References

Guides for Twine can sometimes be hard to find when you need them, particularly because most guides, by necessity, are format-specific. Here are a few guides from across the web. There are other guides out there too, but many are out-of-date, written for older or defunct versions of Twine or story formats, or are (no disrespect intended to the original authors) simply wrong--so YMMV.

### General Guides

Guides for the Twine application itself, for general Twine development information, or that just cover a lot of different story formats.

#### The Twine Cookbook

- [Website](https://twinery.org/cookbook/)

A "cookbook" featuring code examples and explanations of common use-cases in several different formats. A great place to start learning Twine.

#### The Twine Q&A Archive

- [Website](https://twinery.org/questions/)

A place where technical questions about Twine used to be asked. The Q&A has since been shutdown and made read-only, but is is still home to thousands of great answers that you may want to peruse. This site will frequently show up in Google searches as well.

#### The Twine Forum Archive

- [Website](https://twinery.org/forum/)

Years upon years of wisdom and answers can be found by searching the old forum archive. Typically, the archive will appear in Google searches, so it's more common to find it there then to comb through the archive itself.

#### The Official Twine Wiki

- [Website](https://twinery.org/wiki/)

This wiki is useful, but also has a mix of Twine 1 and Twine 2 content, and a mix of content regarding different story formats. This unfortunately can sometimes make it hard to tell what the information you're reading *is actually for*. Still, the wiki remains an impressive collection of information, and is typically worth exploring when you have questions that aren't specifically about a story format.

#### Official Twine Specifications

- [Repository](https://github.com/iftechfoundation/twine-specs)

Specifications drafted and approved by the Twine committee and other related documentation, primarily for the developers of tools, compilers, and formats.

#### Videlais's Guides and Videos

- [Tutorials](https://videlais.com/twine-tutorials/)
- [YouTube](https://www.youtube.com/channel/UCTWJzxNdsIDHiYzGh-2Fd1w)

Videlais (aka, Dan Cox), a member of the Twine Committee and community, has produced many guides, videos, and explanations for all of the core story formats and for Twine in general.

#### A Quick Twine (2.2+) Tutorial

- [Tutorial](http://catn.decontextualize.com/twine/)

As it says on the tin, a quick guide to using Twine 2. Note that the examples in this guide use the deprecated `<<end...>>` style closing tags rather than the `<</...>>` style closing tags that *should* be used in SugarCube.

#### Standard Patterns in Choice-Based Games

- [Blog Post](https://heterogenoustasks.wordpress.com/2015/01/26/standard-patterns-in-choice-based-games/)

An overview and explanation of typical game structures used in choice-driven games.

#### Converting Twine 2 Stories to Android APK Apps

- [Blog Post](https://whatbinder.com/2018/06/01/converting-twine-2-stories-to-android-apk-apps-for-the-google-play-store/)

A guide to using [PhoneGap](https://phonegap.com/) to convert Twine games (not just those made with Twine 2) into Android APK apps.

### SugarCube Guides

#### Official Documentation

- [Website](https://motoslave.net/sugarcube/2/docs/)

The official documentation for SugarCube. While it includes some guides and tips, the documentation is intended as a reference, so may not always explain certain things in the level of detail required by a novice.

#### HiEv's SugarCube Sample Code

- [Website](https://bit.ly/TwineSampleCode)

A large amount of sample code for SugarCube covering a variety of common and uncommon use-cases. Frequently updated with new samples.

### Harlowe Guides

#### Official Documentation

- [Website](https://twine2.neocities.org/)

Harlowe's official documentation. Like SugarCube's docs, this is primarily a reference, though it does try to provide a lot of ground-floor explanations and examples to help novices understand.

#### Introduction to Twine (Harlowe 2.1.0) by Connor Walsh

- [Document](https://docs.wixstatic.com/ugd/d1fd96_4cea140f718a483689aa26a67981671c.pdf)

A fairly wide-ranging beginner-to-intermediate guide to Harlowe 2.

### Snowman Guides

#### Official Documentation

- [Website](https://videlais.github.io/snowman/)

Snowman's official documentation, complete with several usage examples.

### Chapbook Guides

#### Official Documentation

- [Website](https://klembot.github.io/chapbook/guide/)

Chapbook's official documentation. Reads a bit more like a guide than the documentation for the other formats.

## Communities

There are several places across the web where you can discuss Twine, get help with it, or find and connect with other Twine users. Here are several of them.

### Dedicated Communities

These dedicated communities are all about Twine.

#### The r/twinegames Subreddit

- [Subreddit](https://www.reddit.com/r/twinegames/)

An unofficial subreddit dedicated to Twine and Twine games.

#### The Twine Games Discord

- [Invite](https://discord.gg/JbJu25S)

An official Discord server where you can live chat about Twine and Twine games.

### Communities Where Twine May Be Discussed

These more general communities are places with specific Twine subforums, places where discussion about Twine is fairly common, or places where Twine-users tend to congregate, thought they aren't specifically *for* Twine.

#### Intfiction.org

- [Website](https://intfiction.org/)

A forum for interactive fiction with tags/categories for Twine.

#### TFGames.site (WARNING: NSFW)

- [Website](https://tfgames.site/phpbb3/index.php)

A NSFW game development forum with a prominent Twine user base.

#### The r/interactivefiction Subreddit

- [Subreddit](https://www.reddit.com/r/interactivefiction/)

A subreddit for general IF discussion, where Twine may also be discussed.

## Publishing Resources

There are several places across the web where you can host your Twine game for free. You can also always share the HTML file itself (or an archive containing the file and its assets) if you don't want to host it.

> [!WARNING]
> You will not be able to host your Twine game though certain providers like Wix or Wordpress, or through most blogging platforms. Most of these services do not allow users to upload arbitrary HTML files (e.g., your Twine game) and many also have specific limitations on how you can use iframes, so even hosting it elsewhere and making it merely *playable* through your website may not be possible with such services. Some services, like [GoDaddy](https://www.godaddy.com/) have also been known to break the Twine files they are meant to serve, so some research may be needed even if your preferred service does allow you to upload arbitrary HTML files.

### Itch.io

- [Website](https://itch.io/)

Itch.io is an open marketplace for independent digital creators with a focus on independent video games. It allows you to upload assets with your HTML file, and allows you to make downloadable games.

### GitHub Pages

- [Website](https://pages.github.com/)

GitHub pages is great for testing your game, but there are bandwidth limitations, so publishing a game here may have some issues. You can upload assets with your game, and the whole game is structured as a repository on GitHub as well.

### BitBucket Pages

- [Website](https://pages.bitbucket.io/)

Very similar to GitHub pages, but uses BitBucket as a backend.

### Neocities

- [Website](https://neocities.org/)

A free place to host your Twine game, along with any assets it needs. It's limitations are similar to GitHub and BitBucket pages, but you can pay for unlimited bandwidth and other perks.

### DriveToWeb

- [Website](https://drv.tw/)

Allows you to use Google Drive as your website's backend. You can upload assets in addition to your HTML file, as you'd expect. Has potentially stricter limitations than the preceding options.

### Newgrounds 

- [Website](https://www.newgrounds.com/)

Newgrounds accepts HTML games, like Twine. You can upload assets with yout HTML file in much the same way as on Itch.io.