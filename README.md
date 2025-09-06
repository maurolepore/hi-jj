# hi-jj

Jujutsu (jj) is a version control system that provides a flexible alternative to Git. Unlike Git's commit-based model, jj uses "changes" that can be edited at any time, with automatic rebasing of subsequent changes. Key features include working copy management, bookmarks, conflict resolution, and operation logging.

## Workflows

Jujutsu supports multiple workflow patterns, each suited to different development styles and team structures. The flexibility comes from jj's change-based model where work can be reorganized retroactively.

### Dev Branch Strategy

For jj beginners coming from git and PRs, the **dev branch strategy** is easier to work with:

- Creates familiar mental model (like git feature branches off develop)
- Clear hierarchy: main → dev → feature branches  
- Each PR comes from a clean branch off dev
- Simple workflow: create branch, work, PR, repeat

#### Setup
1. **Create dev branch**: `jj new -m "dev"` (creates empty commit)
2. **Position it**: The dev branch sits on top of main as your local base
3. **Keep it empty**: The dev change itself contains no code changes

#### Daily Usage
```bash
# Start new work from dev
jj new dev -m "feature: new component"

# When main updates, rebase dev
jj rebase -b dev -d main

# All your feature branches automatically follow
```

#### Benefits
- **Local changes isolation**: Put config tweaks, debug code, etc. in dev
- **Clean PRs**: Feature branches off dev exclude your local modifications  
- **Automatic updates**: When dev rebases, all descendant changes follow
- **Organized workspace**: Clear hierarchy shows what's local vs. shareable

The dev branch gives you git-like structure while letting you gradually learn jj's more powerful features.

### Alternative Workflows

**Stacked PRs Workflow:**
- Changes don't require immediate branch association
- Create branches retrospectively after completing work
- Automatically propagate changes across interdependent PRs
- Ideal for complex features requiring multiple related changes

**Anonymous Branching:**
- Work directly on changes without named branches
- Organize work by content rather than branch structure
- Perfect for experimental development and quick fixes

**Squash/Edit Workflows:**
- Modify changes after creation with automatic rebasing
- Clean up history through squashing and splitting changes
- Maintain readable commit history without complex rebasing

## Resources 

- [`jj`](https://jj-vcs.github.io/jj/latest/) CLI.
- [Tutorial](https://steveklabnik.github.io/jujutsu-tutorial/).
- [Strategy Guide](https://reasonablypolymorphic.com/blog/jj-strategy/).



