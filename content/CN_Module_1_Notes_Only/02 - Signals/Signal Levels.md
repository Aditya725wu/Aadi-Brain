# Signal Levels

A digital signal can use multiple signal levels.

If a signal uses `L` levels, the number of bits represented by each signal level is:

> **FORMULA**
>
> `bits per level = log2(L)`

## Example: 2 Levels

`L = 2`

`log2(2) = 1`

Therefore, each level represents **1 bit**.

## Example: 4 Levels

`L = 4`

`log2(4) = 2`

Therefore, each level represents **2 bits**.

The possible 2-bit combinations are:

`00, 01, 10, 11`

## Example: 8 Levels

`L = 8`

`log2(8) = 3`

Therefore, each level represents **3 bits**.

## Example: 9 Levels

`log2(9) ≈ 3.17`

In practice, the number of bits per level must be an integer. Therefore, **4 bits** are required to represent 9 levels.

## Important Relationship

More signal levels can represent more bits per signal element, but increasing levels can reduce reliability because the difference between levels becomes smaller.
