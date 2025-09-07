# hi-jj

Jujutsu (jj) is a version control system that provides a flexible alternative to
Git. Unlike Git's commit-based model, jj uses "changes" that can be edited at
any time, with automatic rebasing of subsequent changes. Key features include
working copy management, bookmarks, conflict resolution, and operation logging.

## Workflows

Jujutsu supports multiple workflow patterns, each suited to different
development styles and team structures. The flexibility comes from jj's
change-based model where work can be reorganized retroactively.

### Dev Branch Strategy

- Create this hierarchy: main → dev → feature branches  
- Describe it however you like but leave the diff empty.
- When PRs land on main rebase dev on top of main: 
```
jj git fetch
jj rebase -b dev -d main
```

## Resources 

- [`jj`](https://jj-vcs.github.io/jj/latest/) CLI.
- [Tutorial](https://steveklabnik.github.io/jujutsu-tutorial/).
- [Strategy Guide](https://reasonablypolymorphic.com/blog/jj-strategy/).

