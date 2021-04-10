# commit_manager
Manage commits like a BOSS

Repo: https://github.com/xypnox/commit_manager

Auto commit script

- Should Commit every 10 minutes to daily branch
- Should Squash Merge Daily branch to main once every day
- Should push daily branch to github
- Should push main branch to github
- Should keep pruning the daily branches from both github and local git
- Should auto switch daily branches when next day

## TODO

- [ ] Handle skipped days.
- [ ] Add buffer before deleting day branches.
- [x] Figure out a way to push stuff.
- [x] Add squash commit.
- [x] Add loop every 10 minutes

## Notes

### Logic

For every 10 minutes do:

- Check if the previous day's branch is merged
  - If not do so
  - After merge, push master and delete yesterday's branch
    - Remote and local
- Check if the main after prev merge is pushed
  - If not do so
- Create today's branch if it doesn't exist
- If there are any changes
  - Commit and push changes on today's branch

