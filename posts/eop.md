
## Notes on _Elements of Programming_

### Chapter 1 - Foundations

A value type is _uniquely represented_ if and only if at most one value corresponds
to each abstract entity.

A value type is _unambiguous_ if and only if every value of the type has at most
one interpretation.

Values are pairs of a datum and its interpretation (i.e. the abstract entity to
which the datum corresponds). The two properties of value types listed above allow
us to make certain conclusions about values that are representationally equal (i.e.
have identical datums) or equal (i.e. correspond to the same entity).

__Lemma 1.1__ If a value type is uniquely represented, equality implies representational equality.

Suppose a given value type is uniquely represented. Seeking contradiction, assume
two values of this type are equal, but _not_ representationally equal. Then, two or
more values correspond to the same abstract entity. This contradicts the value type
being uniquely represented, so we conclude the two values must be representationally
equal.

__Lemma 1.2__ If a value type is not ambiguous, representational equality implies equality.

Suppose a given value type is not ambiguous. Seeking contradiction, assume that
two values of the type are representationally equal, but _not_ equal. Then, there
is a value of the type whose datum has more than one interpretation. This contradicts
the value type being unambiguous, so we conclude that the two values must be equal.

---

An object is _well formed_ if and only if its state is well formed, where well formed
state means the datums comprising it all correspond to abstract entities (i.e. it
contains no "garbage" or uninitialized values).

An object is _partially formed_ if it can only be assigned to or destroyed.

__Lemma 1.3__ A well formed object is partially formed.

This statement can be proven by its contrapositive. If an object is not partially
formed, it cannot be assigned to, nor can it be destroyed, so it is certainly not
well formed. (I think the main idea here is that well formed is a stronger condition
than partially formed).
