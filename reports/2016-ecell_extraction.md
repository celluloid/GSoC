# Project: [ECell Extraction][8]

Student: [@benzrf][4]

Mentor: [@digitalextremist][5]

**Google Summer of Code 2016**; Organization: [Celluloid][6]

## Summary

I started with an existing, undocumented codebase written for use in a specific
application, and over the course of the project I turned it into a
general-purpose framework.

First, I renamed parts, reorganized it, and refactored some of the code, file
by file. Over the course of the first GSoC period, I managed to turn the
original codebase into something organized along entirely different lines.

Once I had a working system again, I did a variety of redesign work, including
getting rid of a large amount of use-case-specific hardcoding. In the original
repo, `constants.rb` was 242 lines; in ECell as I'm leaving it, it's only 114.
I also added some high-level documentation comments, wrote [an introduction
mini-book][1], and began the process of setting up a test suite.

Hopefully, it should now be possible to dive into [ECell's code][2] with at
least a general idea of what you're looking at (as long as you read [the
book][1] first!). [Here are my commits][3] in specific.

## Experiences

Here are some of the major things I had to think about or deal with while
working on ECell:

- I had to learn how the codebase worked. The codebase I started with was
  developed internally for a company's private use, so I had zero prior
  exposure to it or how to use it.
- I chose to build the new version up from nothing instead of incrementally
  editing the old version, so I was unable to try running the
  partially-migrated code as I was migrating it. Fortunately, I did a good
  enough job that I didn't have to fix too much after I finished migration.
- I have a habit of automatically asking about things I'm wondering instead of
  taking some time to try figuring them out first. I got better about dealing
  with that impulse over the course of the project, but I still succumbed to it
  a lot.
- Balancing idealism/perfectionism with pragmatism was another thing I had to
  struggle with. A lot of my personal projects end up overengineered or
  incomplete because I get lost in yak shaving or generalizing the design. I
  frequently had to tell myself to stop thinking about how to improve the
  architecture and prioritize getting it working.
- Naming things is always hard.
- My mentor was sometimes difficult to get ahold of. This usually wasn't too
  much of a problem, but it did exacerbate one or two other issues, like
  waiting around for answers instead of figuring things out.
- I learned to do better with writing down plans while they were still in my
  head. I made several checklists over the course of the project.
- I sometimes had a problem with getting hung up on one thing, and then, when
  something held up work on that thing, doing nothing instead of working on
  something else.

## Link Index

- [Project Source Code][2]
- [Project Gitbook][1]
- [My Commits][3]
- [My Github Profile][4]
- [Originator Citation][8]
- [My Mentor's Github Profile][5]
- Celluloid:
  - [GSoC Organization][6]
  - [Github Organization][7]

[1]: https://www.gitbook.com/book/digitalextremist/ecell/details
[2]: https://github.com/celluloid/ecell
[3]: https://github.com/celluloid/ecell/commits?author=benzrf
[4]: https://github.com/benzrf
[5]: https://github.com/digitalextremist
[6]: https://summerofcode.withgoogle.com/organizations/6688531397214208/
[7]: https://github.com/celluloid
[8]: https://github.com/celluloid/ecell#originators
