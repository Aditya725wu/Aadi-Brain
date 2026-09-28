# Data Flow

## Three modes

### Simplex

Communication is one-way only.

``` text
A ─────────→ B
```

Example: traditional one-way broadcast.

### Half-duplex

Both directions are possible, but not simultaneously.

``` text
A ─────→ B
A ←───── B
```

Example: walkie-talkie style communication.

### Full-duplex

Both directions operate simultaneously.

``` text
A ⇄ B
```

Example: telephone conversation.

## Exam comparison

  Mode          Direction         Simultaneous?
  ------------- ----------------- ---------------
  Simplex       One-way           No
  Half-duplex   Both directions   No
  Full-duplex   Both directions   Yes

## Sample

**Q. Explain simplex, half-duplex and full-duplex with diagrams and
examples.**
