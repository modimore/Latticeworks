---
title: Core Features
---

## Core Layout Classes ##

There are three core layout definers in Latticeworks:
boxes, groups, and cells.

### Cells ###

A cell class provides a percentage-based width to an element, determined by the class.

Cells line up next to each other
up until they exceed the width of the containing element,
at which point the next cell will wrap around to the following line.


The class name format is `.lw-cell-$n-$i`,
and that class would have a width property of `$i/$n * 100%`.
Here's an example.

#### Example ####

Green elements are cell elements.

<div class="example colored-example">
  <span class="lw-cell-12-12">12</span>
  <span class="lw-cell-12-1">1</span>
  <span class="lw-cell-12-2">2</span>
  <span class="lw-cell-12-3">3</span>
  <span class="lw-cell-12-3">3</span>
  <span class="lw-cell-12-2">2</span>
  <span class="lw-cell-12-1">1</span>
</div>

<div class="example colored-example">
  <span class="lw-cell-12-11">11</span>
  <span class="lw-cell-12-2">2</span>
  <span class="lw-cell-12-10">10</span>
</div>

### Groups ###

A group class is by default 100% of the width of its parent element.

It is intended to be used to separate groups (hence the name) of elements
from other elements in the flow of the page.


#### Example ####

Red elements are group elements.

<div class="example colored-example">
  <span class="lw-cell-12-6">Before Groups</span>
  <div class="lw-group">
    <span class="lw-cell-12-6">First Group</span>
    <span class="lw-cell-12-6">First Group</span>
    <span class="lw-cell-12-3">First Group</span>
  </div>
  <div class="lw-group">
    <span class="lw-cell-12-9">Second Group</span>
    <span class="lw-cell-12-3">Second Group</span>
    <span class="lw-cell-12-6">Second Group</span>
  </div>
  <span class="lw-cell-12-6">After Groups</span>
</div>

### Boxes ###

A box is another type of self-contained section in the flow of the page,
but is not intended to always take up the whole width.

Boxes are suited for use as centered elements with an explicitly set width.
A common use for this would be to center all content on a page
by wrapping it in one of these boxes.

#### Example ####

Blue elements are box elements.

<div class="example colored-example">
  <div class="lw-box">
    <span class="lw-cell-12-3">3</span>
    <span class="lw-cell-12-3">3</span>
    <span class="lw-cell-12-6">6</span>
  </div>
  <div class="lw-box">
    <div class="lw-group">
      <span class="lw-cell-12-4">4</span>
      <span class="lw-cell-12-4">4</span>
    </div>
    <span class="lw-cell-12-4">4</span>
  </div>
</div>
