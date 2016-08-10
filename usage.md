---
title: Usage
---

Latticeworks is a new project, and currently only has a Sass version.
You can use this or take the provided [example CSS file][l12] from the project.

[l12]: https://github.com/modimore/Latticeworks/blob/master/css/lattice-12.css

## Sass

Latticeworks is meant to be used by `@include`ing its mixins.

As a general note, Latticeworks encourages you to use your own style of selector naming that will end up in your CSS.
How that should play out depends on the types of elements you are trying to affect.
For out purposes, there are two categories of mixin to consider.

### Categories

#### Simple
A simple class is almost a ready-to-go style for an set of elements.
The only thing it's missing is a name. Groups and Boxes fall under this category.

For instance, if we wanted to create a box class and a group class,
we might put this in our `main.scss` file:

{% highlight scss %}
.lw-box {
  @include lw-box;
}

.lw-group {
  @include lw-group;
}
{% endhighlight %}

#### Generated
A generated class requires you to provided a base class name to the mixin as a string.
It should be the first argument to the mixin.
The resultant classes will start with this base class name.

Here's how you could go about generating Latticeworks cells:

{% highlight scss %}
@include lw-cells(3, $class-basename: 'lw-cell');
{% endhighlight %}

The result would look something like this:

{% highlight css %}
.lw-cell-3-1, .lw-cell-3-2, .lw-cell-3-3 { }

.lw-cell-3-1 { width: 33.33%; }
.lw-cell-3-2 { width: 66.67%; }
.lw-cell-3-3 { width: 100%; }
{% endhighlight %}

### Components

This section shows the mixin signatures for Latticework components,
and a description of the mixin's arguments as they appear for the first time.
Some components use extra mixins, usually for generating media-queries.

#### Cells
Generate cells. $n is the number of classes generated, and also the denominator
of the fractions used in width generation.

```
@mixin lw-cells($n, $class-basename)
```

Pad specified cells

```
@mixin lw-cells-pad($n, $padding, $class-basename)

- $padding: valid CSS padding specification
```

Resize segments when document.width drops below `$screen-width`

```
@mixin lw-cells-adjust-at($n, $screen-width, $class-basename)

- $screen-width: adjustment breakpoint
```

#### Groups
Create group class

```
@mixin lw-group()
```

#### Boxes
Create box class

```
@mixin lw-box()
```

### Special Cases
There are some situations in which Latticewoks has a solution
to a likely issue that would arise during use.
These are detailed here, noting the elements they apply to.

#### Tables and Table Cells
Some of the Latticeworks components can cause unexpected behaviour when
used with tables. The following problems are known and have been addressed.

table::before and table::after elements can become visible
if you apply the latticeworks %clearfix class to a table
and then color it. The following will stop them from rendering.

```
@mixin lw-tablefix()
```

Table cells can't float and have a size properly,
and the way lw-cell classes resize with media queries does not work well in a table.
Use this to make table cells appear consistent at any page size,
and make sure they are not floated in any way.

```
@mixin lw-tablecells($n)
```

#### Lables and Input Groups
This mixin, called in a class, will cause all inputs in a container
element of that class to take up its full with
and appear under a label in that container.
It applies styles to label, input, and textarea elements to achieve this.

```
@mixin lw-form-field()
```
