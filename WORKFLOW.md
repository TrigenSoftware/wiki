# Workflow

### Sprints

Each sprint developing should goes in `dev` branch. Merge to master should be in the end of sprint.

### Task creating

Template:

> [Task description]
>
> Working branch: [[branch-prefix]/branch-name]

Branch prefixes:

- `component/*`
- `feature/*`
- `enhancement/*`
- `fix/*`

Steps:

1) Create task (issue) with given template;
2) Add lables;
3) Add project;
4) Add assignees.
5) After PR merge: comment and close with `"Done in #{PR_NUMBER}"`

### Task execution

Steps:

1) Create branch with given name;
2) Create PR with same name as task name;
3) Add reference to the task in PR description;
4) Add lables;
5) Add project;
6) Add reviewers.
