# Inclusion-Exclusion Principle

## Two Sets

`|A ∪ B| = |A| + |B| - |A ∩ B|`

### Why subtract the intersection?

Elements in `A ∩ B` are counted twice when `|A| + |B|` is calculated.

Therefore subtract the intersection once.

---

## Three Sets

`|A ∪ B ∪ C|`
`= |A| + |B| + |C|`
`- |A ∩ B| - |B ∩ C| - |A ∩ C|`
`+ |A ∩ B ∩ C|`

### Pattern

```text
+ single sets
- pair intersections
+ triple intersection
```

## Typical Numerical Method

For a class/collection problem:

1. Draw the Venn diagram.
2. Put the triple intersection first.
3. Find each pair-only region.
4. Find each single-only region.
5. Add all regions inside the union.
6. Subtract from the universal total to find "none", if required.

## Important

If a pair intersection is given and a triple intersection also exists:

`Pair-only = Pair intersection - Triple intersection`
