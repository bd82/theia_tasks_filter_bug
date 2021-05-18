# theia_tasks_filter_bug

## Problem

Some VSCode tasks in tasks.json do not appear in Theia's `Task: Run Task...` command.
Specifically it seems to occur for tasks of types that have available task providers
yet do not match **perfectly** with an auto-provided task.

## Reproduce

- Clone this repo.
- Clone Theia.
- `cd theia`  
- `git checkout 1.13.0`
- `yarn`  
- `cd examples/browser`
- `yarn start`  
- in browser open: http://localhost:3000/  
- `File` -> `Open` -> `This repo's cloned folder`
- `View` -> `Find Command...` -> `Task: Run Task...`

Expected Results:
  - Both the `npm: build` and the `npm: bamba` tasks from the task.json would be displayed.

Actual Results:
  - Only the `npm: build` task is displayed.
  - Note that both tasks would be displayed inside VSCode (I checked on 1.56.2).


