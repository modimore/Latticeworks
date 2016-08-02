---
title: Form Styling
---

## Form Styling

Latticework layout elements can be used directly on form, label, and input elements.

In addition to the usual classes, one extra class is provided in _\_forms.scss_, `lw-form-field`. It is intended to group a label and an input element. Inside it the input will take up the full width of the box with the label above it.

#### Example

<div class="example">
  <form class="lw-box">
    <div class="lw-group">
      <div class="lw-cell-12-6 lw-form-field">
        <label for="name">Name</label>
        <input name="name" type="text">
      </div>
      <div class="lw-cell-12-6 lw-form-field">
        <label for="email">Email Address</label>
        <input type="text" pattern="[\w\.]+@\w+\.\w{2,4}" placeholder="user@example.com">
      </div>
    </div>

    <div class="lw-group">
      <label for="password" class="lw-cell-12-3">Password</label>
      <input name="password" type="password" class="lw-cell-12-9">
      <label for="password-check" class="lw-cell-12-3">Confirm Password</label>
      <input name="password-check" type="password" class="lw-cell-12-9 lw-float-right">
    </div>

    <div class="lw-cell-12-12 lw-form-field">
      <label for="comment">Bio</label>
      <textarea name="comment"></textarea>
    </div>

    <div class="lw-cell-12-2 lw-form-field">
      <label for="check">Check Box</label>
      <input name="check" type="checkbox">
    </div>
    <div class="lw-cell-12-10 lw-form-field">
      <input name="button" type="button" value="Button" alt="button">
    </div>
  </form>
</div>
