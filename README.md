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

![Screenshot](https://user-images.githubusercontent.com/58962/141682345-19eb1f49-6808-45f8-95e6-67ab3af971c8.png)

### 🚨 WARNING! 🚨

This is new software and definitely not mature!
Error handling is bad!
You may have to help fix things!

## How It Works

Every morning [the porter][] creates a new ticket for the day from [a template][]
you control. We suggest this template contains habits you aim to complete each
day but that’s up to you.

Tick off the habits (or strike-them-out† if you couldn’t do them) and once they
are all checked off the ticket is closed by our automation.

> † Surround text in `~` to strike-out

Habit tracking is the just the first part of GitTD, the rest is up to you.


### Getting Things Done

The beauty of Git Things Done is the *ecosystem*. Anyone can create actions
so you can customize it to exactly what you need.

We provide the following:

* A [powerful templating system][the porter] for creating daily entries
* An opinionated (and novel) [task tracking system](https://github.com/git-things-done/now-now)
* An easy way to [add new tasks](https://github.com/git-things-done/new-now-now)
* [A mechanism for making “sticky” comments](https://github.com/git-things-done/usher)
* An automated [labeling bot](https://github.com/git-things-done/librarian) based on comment content
* A daily [fortune](https://github.com/git-things-done/fortune)
* [The weather forecast](https://github.com/git-things-done/forecast)

> [Browse our Awesome List for GitTD][Awesome List]

> [Search for more GitTD actions on the GitHub Actions Marketplace](https://github.com/marketplace?type=actions&query=git+things+done)

## Getting Started

1. **Do Not Fork**\
  Unfortunately, GitHub do not allow you to make a private fork of a public
  repository[^1].\
  Instead use [`gh`][]:
  ```sh
  gh repo create gtd --private --template git-things-done/template
  ```
2. [Edit the templates](/templates/)
3. Wait for tomorrow‡

> ‡ If you can’t wait, [manually dispatch the porter](../../actions/workflows/porter.yml).

[`gh`]: https://cli.github.com
[^1]: If you work at GitHub could you perhaps consider allowing private forks
  **for templates**. This is presumably useful in general and not just for us.
  Thanks muchly bae 💜.

# Detritus

<details>
<summary>
Suggestions and tips for using GitTD effectively
</summary>

## Suggested Usage

* Every morning ensure you’ve closed out yesterday
* Tick habits and tasks off during the day
* Try it out for a week
* Start adding “[Sticky Comments](https://github.com/git-things-done/usher)”
* Start editing the workflows to suit your usage
* Add an occasional:
  * Journal (How are you feeling?)
  * Audit (How’s life going? What needs changing?)
* Publish any new stuff you make and buoy up the ecosystem

</details>


<details>
<summary>
Preventing your GitTD from falling behind updates
</summary>

## Staying Updated

We are unlikely to bump our major versions so you should automatically be
up-to-date, but just in case consider setting up [Dependabot][].

Changes to our template workflows are more likely and easier to miss.
Subscribe to this repo’s release updates to get pings.

</details>


<details>
<summary>
Want a URL that goes straight to today’s entry? We got you covered.
</summary>

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

You can use [this Shortcuts.app shortcut][shortcut] that we already prepared for
you.

</details>

<img width="378" alt="image" src="https://user-images.githubusercontent.com/58962/140531618-5012f544-4f25-4815-9978-f3f0e6bf80dd.png">


# Contributing

1. [Create a GitHub Action](https://docs.github.com/en/actions/creating-actions)
2. [The porter][] provides `GTD_TODAY` (today’s ticket number) and `GTD_YESTERDAY`†
3. Ensure your repo is public
4. Tag the repo with `GitTD` and `github-actions`
5. Publish to the GitHub Actions Marketplace and tag it `GitTD`
6. Consider a PR on our [Awesome List](https://github.com/git-things-done/awesome)

> † For other variables you might need, check out the sources for [our actions](https://github.com/git-things-done).

## Branding

Consistent GitTD branding assists user recognition:

```yml
# `action.yml`

name: “Foo” for Git Things Done
branding:
  icon: check-square
  color: green
# …
```

We suggest setting your primary category in the GitHub Actions Marketplace to
**Utilities**, but this is optional—choose whatever you feel is appropriate.

> [Here’s a Marketplace example.](https://github.com/marketplace/actions/fortune-for-git-things-done)

> **Please note**, to be added to our [Awesome List] your branding must be
> match the above guidelines.

## Work in Your Fork

It can be *fiddly* to develop GitHub Actions, so we suggest starting in your own
fork and making the action *locally*:

```
- uses: ./my-gtd-action
  ## ^^ will run $REPO_ROOT/my-gtd-action/action.yml
```

When it works move the code to its own *public* repo and publicize it.


# More Like This?

Want to make things like this with people who make things like this?

[Join Bootstrap Club](https://mxcl.dev/bootstrap-club/).


[Fork]: ../../fork
[the porter]: https://github.com/git-things-done/porter
[dependabot]: https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/keeping-your-actions-up-to-date-with-dependabot
[shortcut]: https://www.icloud.com/shortcuts/25c9d874988d497f862d31fe5e587a96
[a template]: /templates/quotidian.md
[Awesome List]: https://github.com/git-things-done/awesome
