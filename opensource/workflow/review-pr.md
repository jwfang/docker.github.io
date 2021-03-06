---
description: Basic workflow for Docker contributions
keywords: contribute, pull request, review, workflow, beginner, squash, commit
title: Participate in the PR review
---

Creating a pull request is nearly the end of the contribution process. At this
point, your code is reviewed both by our continuous integration (CI) systems and
by our maintainers.

The CI system is an automated system. The maintainers are human beings that also
work on Docker. You need to understand and work with both the "bots" and the
"beings" to review your contribution.

> **Note**: These guidelines apply to Docker code submissions. If you want to
> contribute to the Docker documentation itself, see the guidelines in the
> `docker.github.io` repository's
> [README.md](https://github.com/docker/docker.github.io).

## How we process your review

First to review your pull request is Gordon. Gordon is fast. He checks your
pull request (PR) for common problems like a missing signature. If Gordon finds a
problem, he'll send an email through your GitHub user account:

![Gordon](images/gordon.jpeg)

Our build bot system starts building your changes while Gordon sends any emails.

The build system double-checks your work by compiling your code with Docker's master
code. Building includes running the same tests you ran locally. If you forgot
to run tests or missed something in fixing problems, the automated build is our
safety check.

After Gordon and the bots, Docker maintainers look at your pull request and
provide feedback. The shortest comment you might see is `LGTM` which means
"Looks Good To Me". If you get an `LGTM`, that is a good thing, you passed that
review.

For complex changes, maintainers may ask you questions or ask you to change
something about your submission. You are notified about all maintainer comments
on a PR, depending on the way you have configured Github to notify you. Any
GitHub user who participates in a PR receives an email. Participation includes
creating the PR, commenting on it, committing into someone else's PR, or being
at-mentioned in a comment. You can unsubscribe from notifications to a PR by
clicking the **Unsubscribe** button.

Our maintainers are experienced Docker users and open source contributors.
They value your time and will try to work efficiently with you by keeping
their comments specific and brief. If they ask you to make a change, you'll
need to update your pull request with additional changes.

## Update an existing pull request

To update your existing pull request:

1.  Checkout the PR branch in your local repository.

    This is the branch associated with your request.

2.  Change one or more files and then stage your changes.

    The command syntax is:
    
    ```bash
    $ git add <path_or_filename>
    ```

3.  Commit the change.

    ```bash
    $ git commit --amend
    ```

    Git opens an editor containing your last commit message.

4.  Adjust your last comment to reflect this new change.

    ```none

    Added a new sentence per Anaud's suggestion

    Signed-off-by: Mary Anthony <mary@docker.com>

    # Please enter the commit message for your changes. Lines starting
    # with '#' will be ignored, and an empty message aborts the commit.
    # On branch 11038-fix-rhel-link
    # Your branch is up-to-date with 'origin/11038-fix-rhel-link'.
    #
    # Changes to be committed:
    #		modified:   docs/installation/mac.md
    #		modified:   docs/installation/rhel.md
    ```

5.  Force-push the change to your origin.

    Force-pushing is necessary because you amended your commit, and effectively
    changed history. The command syntax is:
    
    ```bash
    $ git push -f origin <branch_name>
    ```

6.  Open your browser to your pull request on GitHub.

    You should see your pull request now contains your newly pushed code.

7.  Add a comment to your pull request.

    GitHub only notifies PR participants when you comment. For example, you can
    mention that you updated your PR. Your comment alerts the maintainers that
    you made an update.

A change requires LGTMs from an absolute majority of an affected component's
maintainers. For example, if you change `docs/` and `registry/` code, an
absolute majority of the `docs/` and the `registry/` maintainers must approve
your PR. Once you get approval, we merge your pull request into Docker's
`master` code branch.

## After the merge

It can take time to see a merged pull request in Docker's official release.
A master build is available almost immediately though. Docker builds and
updates its development binaries after each merge to `master`.

1.  Browse to [https://master.dockerproject.org/](https://master.dockerproject.org/){: target="_blank" class="_"}.

2.  Look for the binary appropriate to your system.

3.  Download and run the binary.

    You might want to run the binary in a container though. This
    will keep your local host environment clean.

Once you've verified everything merged, feel free to delete your feature branch
from your fork.
[See the GitHub help on deleting branches](https://help.github.com/articles/deleting-unused-branches/){: target="_blank" class="_"}.

## Where to go next

At this point, you have completed all the basic tasks in our contributors guide.
If you enjoyed contributing, let us know by completing another beginner
issue or two. We really appreciate the help.

If you are very experienced and want to make a major change, go on to
[learn about advanced contributing](advanced-contributing.md).
