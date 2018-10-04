# Tokio Doc Blitz

Welcome to the Tokio doc blitz effort. The goal is to organize a
concerted community effort to improve the Tokio documentation while also
gaining new contributors. At the end, we hope to have a significantly
improved set of [guides] and [API documentation][api].

The Tokio doc blitz can use the help of all, **no matter the level of
familiarity with Tokio**.

[guides]: https://tokio.rs/docs
[api]: http://docs.rs/tokio

Join us on [Gitter].

## Process

The steps are roughly:

1) Structure an [outline] of what we would like the Tokio guides to be.
2) Community members pick topics from the outline that they are familiar
   with and contribute guides.
3) New community members still unfamiliar with Tokio read the new
   guides, documenting questions and blockers they hit.
4) Update the guide outline based on the feedback, and repeat the
   process.

This git repository will be used to coordinate the effort. The current
outline is found [here][outline] and dicussion are in issues.

## Contributing

There are a few ways to jump and get involved depending on your comfort
level.

First, [watch] this repo and join us in the [Gitter] channel.

[watch]: https://help.github.com/articles/watching-and-unwatching-repositories/#watching-a-single-repository

### Read the existing guides

**Required Experience**: Any

Read the existing [guides] and try to learn how to use Tokio. While
doing so, keep track of the experience. Some things to keep in mind:

* What parts of the guides were confusing?
* What questsions went unanswered?
* Did anything flow strangely?

Then, [file issues][confusion] tracking your experience.

### Provide thoughts and feedback on the outline

**Required Experience**: Beginner

The [outline] proposed in this repository tracks where we would like the
Tokio [guides] to go. Browse through what is proposed and jump in the
disucssion providing thoughts and feedback on the proposed outline. What
topics did we miss?

Feel free to open new [issues][new-issue] or comment on [existing] ones.

### Brainstorm ideas for the cookbook and list of "gotchas"

**Required Experience**: Beginner

These two sections need to be based off of problems real users of Tokio
hit, so we want your ideas.

* [Gotchas](https://github.com/tokio-rs/doc-blitz/issues/14)
* [Cookbook](https://github.com/tokio-rs/doc-blitz/issues/23)

### Tweak an existing guide

**Requires Experience**: Beginner

The guides are part of the [website] repository. If you see a way to
tweak an existing guide to improve it, please open a PR.

### Review a guide pull request

**Requires Experience**: Beginner

As guides are written, they will need feedback. The pull requests will be
submitted to the [website] repository. Keep an eye out for new ones, and when
they appear, review the pull requests and provide your feedback.

### Write a guide

**Required Experience**: Intermediate

The goal of the doc blitz is to get the community to contribute guides.
While some level of Tokio experience is needed, it is probably less tha
you might expect. A detailed [outline] is provided to get started. We are also
available on [Gitter] to answer questions
and to teach you enough to get to the point of writing the guide. So why not
give it a shot?

If you want to take a stab at writing a guide, find a page in the
outline that is marked as unassigned and submit a PR with your GitHub
handle as the assignee for the page. Then, start writing.

Please file a PR to the [website] as soon as you can with your work in
progress (you can preface the PR with **work in progress**). This is
useful for getting early feedback from the community.

[Gitter]: https://gitter.im/tokio-rs/doc-blitz
[outline]: outline/README.md
[guides]: https://tokio.rs/docs
[new-issue]: https://github.com/tokio-rs/doc-blitz/issues/new
[confusion]: https://github.com/tokio-rs/doc-blitz/issues/new?labels=confusion
[existing]: https://github.com/tokio-rs/doc-blitz/issues
[website]: http://github.com/tokio-rs/website

## License

This repository is licensed under the [MIT license](LICENSE).

### Contribution

Unless you explicitly state otherwise, any contribution intentionally
submitted for inclusion in doc-blitz by you, shall be licensed as MIT,
without any additional terms or conditions.
