Whatnext
========

Whatnext is a lightweight tool to keep you on track. It is a simple shell layer
over the file system designed for use from the command line or in scripts.
Combined with source control, it allows for powerful tracking of what you
should do next.

Usage
-----

```
whatnext [echo]
```
Displays the path of the current task and its contents, if it exists. If there
is no current task, the tasks in the queue will be display. If no tasks are
queued, all open tasks will be displayed.

```
whatnext add <project> <task_name>
```
Creates a new task under the heading `<project>` and opens the underlying file
for editing. `<project>` is created if is does not exist.

```
whatnext queue <project> <task_name>
```
Marks a task as ready to be worked on. A task that does not exist will be
created as with `whatnext add`. Finished tasks can be added back to the queue
by prepending a `.` to their names.

```
whatnext start <project> <task_name>
```
Marks a task as the current one being worked on and opens the underlying file
for editing. It must be in the queue before it can be started. Started tasks
remain in the queue until they are complete and can be preempted at any time.

```
whatnext finish
```
Marks a task as complete and opens the underlying file for editing. This
removes it from the queue and renames the underlying file with a `.` at the
front, so it is does not clutter up searches (unless you are looking for it)

```
whatnext open [<project> <task_name>]
```
Opens the underlying file for editing. It defaults to the current task if none
is specified.

```
whatnext ls
```
Lists all tasks that are queued. If no tasks are queued, all open tasks will be
displayed.

```
whatnext tree
```
Runs `tree` on the whatnext directory for examination. Requires the `tree`
program to be installed.
