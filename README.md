# Git Things Done (GitTD)

Every few years I hunt around for a habit-tracker that meets my needs.

And for *maybe a week*: my needs are met.

It’s not long however before I want to *track tasks*, add *journal entries*; add
*tags*, *images* and *notes*; I want to *set deadlines*; *make API calls* and
synchronize with other tools on the web. The apps are never flexible enough;
so I give up.

This year it occurred to me that I could build what I needed using
GitHub *Issues*, GitHub *Actions*, GitHub *Pages* and GitHub *Flat Data*.
Git Things Done is a **programmable**, **flexible**, **hackable** and **extensible**
“Getting Things Done” system. Try it out and make it yours.


### 🚨 WARNING 🚨

This is new software and definitely not mature.
Error handling is bad. You may have to help fix things.


## How It Works

Every morning [the porter][] creates a new ticket for the day from [a template][]
you control. We suggest this template contains habits you aim to complete each
day but… it can be whatever you want.

<img width="571" alt="image" src="https://user-images.githubusercontent.com/58962/140620440-673a7a31-7fb4-4c19-b432-bc6f2c95e2ec.png">

Tick off the habits and once they are all checked off the ticket is closed by
our automation.


### Getting Things Done

The beauty of Git Things Done is the *ecosystem*. Anyone can create actions
so you can customize it to exactly what you need.

We provide the following:

* An opinionated (and novel) [task tracking system](https://github.com/git-things-done/now-now)
* An easy way to [add new tasks](https://github.com/git-things-done/new-now-now)
* [A mechanism for making “sticky” comments](https://github.com/git-things-done/usher)
* An automated [labeling bot](https://github.com/git-things-done/librarian) based on comment content
* A daily [fortune](https://github.com/git-things-done/fortune)

## Getting Started

* Fork this repo (it’s a template).
* Make it private (up to you, but probably you want this)
* Check out [`porter.yml`](/.github/workflows/porter.yml) and edit if needed
* Edit the [templates](/templates/)


### Suggested Usage

* Every morning ensure you close out yesterday
* Tick habits and tasks off
* Try it out for a week
* Start adding “[Sticky Comments](https://github.com/git-things-done/usher)”
* Start editing the workflows to suit your usage
* Add an ocassional:
  * Journal (How are you feeling?)
  * Audit (How’s life going? What needs changing?)
* Publish any new stuff you make and buoy up the ecosystem


### Staying Updated

We are unlikely to bump our major versions so you should automatically be
up-to-date, but just in case consider setting up [Dependabot][].

Changes to our template workflows are more likely and easier to miss.
Subscribe to this repo’s release updates to get pings.


## Bookmarkable URL

We generate a HTML redirect to the latest ticket every day and make it the
GitHub Pages for your GitTD repo.
It has the form: https://YOU.github.io/REPO/

> eg. https://mxcl.github.io/gtd/

Bookmark it and you can quickly and easily get to today’s entry.

### Considerations for iOS

It is complicated to bookmark a URL that is just a redirect on iOS.
Additionally, if you succeed (there are tricks) the bookmark will *always* open
Safari before opening the GitHub app.
Thus we recommend using an iOS Shortcut that opens the URL as it solves
both issues (iOS asks if you want to let the shortcut open GitHub a few times
but stops after about 3).

You can use [this Shortcuts.app shortcut][shortcut] that we already prepared for you.

<img width="378" alt="image" src="https://user-images.githubusercontent.com/58962/140531618-5012f544-4f25-4815-9978-f3f0e6bf80dd.png">


## Contributing

1. [Create a GitHub Action](https://docs.github.com/en/actions/creating-actions)
2. [The porter][] provides `GTD_TODAY` (today’s ticket number) and `GTD_YESTERDAY`†
3. Ensure your repo is public
4. Tag the repo with `GitTD` and `github-actions`
5. Publish to the GitHub Actions Marketplace and tag it `GitTD`
6. Consider a PR on our [Awesome List](https://github.com/git-things-done/awesome)

> † For other variables you might need, check out the sources for [our actions](https://github.com/git-things-done).


# More Like This?

Want to make things like this with people who make things like this?

[Join Bootstrap Club](https://mxcl.dev/bootstrap-club/).


[the porter]: https://github.com/git-things-done/porter
[dependabot]: https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/keeping-your-actions-up-to-date-with-dependabot
[shortcut]: https://www.icloud.com/shortcuts/25c9d874988d497f862d31fe5e587a96
[a template]: /templates/quotidian.md
