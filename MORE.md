# reasoned

`reasoned` - It's like BEM plus a design for logical outcomes.

Ok, so BEM was originally for structuring CSS and related kin.
It gives you possible structure for otherwise ad-hoc conventions.

Each node in the tree can defined in uniquely addressable manner, including logical application status.

## BEM - Base Element Modifier
 * *B* - `Base`: The entity that this component represents
 * *E* - `Element`: The substructure that is a part of this `Base`
 * *M* - `Modifier`: The status(es) that might be applied to this `Base` or `Element`

With the above any node is specified (by convention) with `${Base}__${element}--${modifier}`

* For every `Base` or `Element` with a `Modifier`, there is an implied Modifier-less version of that `Base` or `Element`, that is:
  + `Alpha__beta--gamma` implies that `Alpha__beta` is a valid and defined `Element`, even if not explicitly specified otherwise.
  + `User--is-customer` implies that `User` is a valid and defined `Base`, even if not explicitly specified otherwise.

### BUT BUT BUT BUT

If'n there's a structure for "all the stuff" that also has logic status, can't we give that a set of rules?

## Rules for Mods

BEM is loose. It could be chaos if you had some rogues naming things: `Feature__Button--mike-is-a-jerk`. Technically I know some stuff now, but not necessarily about your page.

I want something that expresses page state succinctly and in a way where you can slice out _logical_ domains in addition to addressing stylistic concerns.

Let's start with a stack of semantically named selectors:

```
.User--is-customer
.Feature--mode-alien .Form__button--id-area-51
.User--is-first-time-buyer .Cart--has-sale .CartItem--sale
.Table__seat--chair-a
```

We need a checklist that is not based on our local conventions but instead a set of rules that organize choices in the BEM choices.

Since this is hard and it's more complex based on what you're trying to accomplish, let's list some possible use-cases:

 - Can I have a tool for checking a given structure has been adhered to? (Tool: Linting)
 - Can I have a tool for validating the structure of a given BEM string? (Tool: Linting)
 - Can I have a logical segmentation between "props that have a visual effect" vs. "`props` that do not have a visual effect"? (Convention: Pattern)
 - Can I have a means of providing a contract between the "where this thing is styled" vs. "where this thing is logically defined"? (Tool : Development)
   Downstream effects:
   - Verification of a quantifiable design
   - Verification of a logical domain
   <!--- If I can define that a known user group has a vested interest in some feature, then the -->


