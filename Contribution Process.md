# Contributing

Our project use ![GitHub Flow](https://help.github.com/articles/github-flow/) for contributions. In short, Fork, Create a branch, submit a pull request from that branch.

## Suggested repo setup
1. Clone your fork (your fork will be `origin`)
2. `git remote add upstream git@github.com:sevenwestmedia/processes.git`

## Workflow
1. `git checkout master`
2. `git pull upstream master --ff-only` - pulls the lastest changes from the main repository into your local master
3. `git checkout -b task/task-description`
4. ... do work
5. `git commit -m "SEMANTIC RELEASE COMMIT"` - see [Semantic Release commit format](https://github.com/semantic-release/semantic-release#commit-message-format)
    * eg. `fix: Some bug fix`, `feat: Some feature description`, `docs(readme): Improved readme`.
    * You can also put an extended description in a multiline commit message on line 3
6. `git push -u origin HEAD` - This will push your current branch to your fork
7. Open a pull request from your fork to the main repository (if you navigate to the main repository, GitHub will detect you have pushed a branch and suggest to open a pull request)
