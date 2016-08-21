I started with an existing, undocumented codebase written for use in a specific
application, and over the course of the project I turned it into a
general-purpose framework. First, I renamed parts, reorganized it, and
refactored some of the code, file by file. Over the course of the first GSoC
period, I managed to turn the original codebase into something organized along
entirely different lines. Once I had a working system again, I did a variety of
redesign work, including getting rid of a large amount of use-case-specific
hardcoding. In the original repo, `constants.rb` was 242 lines; in ECell as I'm
leaving it, it's only 114. I also added some high-level documentation comments,
wrote [an introduction mini-book][1], and began the process of setting up a
test suite. Hopefully, it should now be possible to dive into ECell's code with
at least a general idea of what you're looking at.

https://github.com/celluloid/ecell

[1] https://link.to/git/book/

- List the major focus areas within the project, and a synopsis of the most
  significant elements, situations, problems, etc.

Major focus areas:
- Redesigning the terminology and the API
- Getting rid of hardcoding and design choices made for the original use-case
- Writing documentation

Most significant elements, situations, problems, etc:
- Learning how the codebase worked, from scratch
- Dealing with the impulse to ask instead of figure out
- Balancing idealism/perfectionism with pragmatism
- Naming things
- Irregular communication
- Planning/checklists
- Getting hung up on one thing
- Unable to test partially-migrated code

