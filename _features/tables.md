---
title: Table Styling
---

## Table Styling ##

Not all style rules used in Latticworks can meaningfully apply to table cells.
Some actually cause issues with the way table cells are displayed.

Since this is a known problem, Latticeworks includes specific property resets
on cell classes specifically applied to td, th, and col elements.

Notably, table cells with `.lw-cell-$n-$i`
do not resize based on media queries
unless you mark the new width as `!important`.
Tables also do not have ::before and ::after pseudo-elements attached to them.

With this in place you can use the same width-setting classes on tables,
so you can have fewer CSS classes that essentially do the same thing.

<div class="example colored-example">
  <table class="ex-lw-cells">
    <caption>Widths specified in colgroup</caption>
    <colgroup>
      <col class="lw-cell-12-3">
      <col class="lw-cell-12-3">
      <col class="lw-cell-12-5">
      <col class="lw-cell-12-1">
    </colgroup>

    <tbody>
      <tr>
        <td>3</td>
        <td>3</td>
        <td>5</td>
        <td>1</td>
      </tr>
      <tr>
        <td>3</td>
        <td>3</td>
        <th colspan="2">6</th>
      </tr>
    </tbody>
  </table>

  <table class="ex-lw-cells">
    <caption>Widths specified on table cells</caption>
    <thead>
      <tr>
        <td class="lw-cell-12-3">3</td>
        <td class="lw-cell-12-3">3</td>
        <td class="lw-cell-12-5">5</td>
        <td class="lw-cell-12-1">1</td>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>3</td>
        <td>3</td>
        <th colspan="2">6</th>
      </tr>
    </tbody>
  </table>
</div>

<div class="example colored-example">
  <table class="lw-box">
    <caption>`table.lw-box`</caption>

    <colgroup>
      <col class="lw-cell-12-4">
      <col class="lw-cell-12-4">
      <col class="lw-cell-12-4">
    </colgroup>

    <tbody>
      <tr>
        <td>4</td>
        <td>4</td>
        <td>4</td>
      </tr>
    </tbody>
  </table>

  <table class="lw-group">
    <caption>`table.lw-group`</caption>

    <colgroup>
      <col class="lw-cell-12-4">
      <col class="lw-cell-12-4">
      <col class="lw-cell-12-4">
    </colgroup>

    <tbody>
      <tr>
        <td>4</td>
        <td>4</td>
        <td>4</td>
      </tr>
    </tbody>
  </table>
</div>
