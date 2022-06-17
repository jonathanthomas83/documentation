# Find a filename with a partial match

When looking for file `202206081000-dwp-relationships-appointee-prototype-presentation.md`, I didn't want to type in the long, laborious number or name, so I looked for "presentation", that brought up two files that were presentations, but you can refine further, using two or more wildcards.

```
cat *relationships*presentation*
```

Then press 'tab'.

_Note:_ The words need to be in the same order as they appear in the filename.
