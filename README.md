# reasoned

![dependencies via madge](./graph.svg)

Use `reasoned` to structure components and state when creating views.

## Example

Let's say we have a shopping cart view.

### Loose requirements

There's some stuff we know about what we want already:

1.  Items in the cart should present basic information, like:
    a. Name of item
    b. Special Status: `sale` | `combo` | `stale`
    c. Cost
    d. A picture, if there is one
2.  Active event keys, if provided, with a special status: `sale` | `discount` | `event`
3.  A cumulative cost view

### How `reasoned` works

#### It's mainly BEM

We're building atop a classic BEM structure, which, if you're unfamiliar, is:

- Base
- Element
- Modifier

These three consituent parts can the be combined with a useful but somewhat verbose unique selector for the page: `Base__element--modifier`

Any specific part of a view can be understood by its positional information: `Component__semantic-subsection--logic`

BEM affords both a solution for style but also a fundamental means of segmenting a component to constituent parts.

.Cart

- -> \_\_items
- -> \_\_item
  - --sale
  - --combo
  - --stale
  - -> \_\_item-name
  - -> \_\_item-cost
  - -> \_\_item-pic
- -> \_\_cost
  - --total

#### And a structure for logic
