# timelinechart

This is a utility to make a timeline chart (Gantt chart?) in matplotlib from any file.

Entries are lines in the file with the format

```
<end-date> <start-date> <label>
```

with dates written YYYY-MM-DD.

For example, some entries might look like

```
:::::::::: 2025-07-18 Ongoing task
2025-07-22 2025-07-20 Finished task #4
2025-07-21 2025-07-08 Finished task #1
2025-07-19 2025-07-13 Finished task #2
2025-07-16 2025-07-14 Finished task #3
```

If a thing hasn't ended yet, the end date is written `::::::::::`.

You can create the chart by passing the filename of the file to the script, e.g. `./timelinechart xyz.txt`.

The script only looks for lines that match that pattern, so the file can contain any other things and it will not interfere with the script.

The syntax is designed so that sorting the lines in reverse (e.g. `:sor!` in vim) places unfinished entries at the top and sorts the rest by when they were finished, with the most recent entries first.
