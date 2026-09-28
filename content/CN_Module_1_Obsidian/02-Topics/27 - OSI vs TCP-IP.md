# OSI vs TCP/IP

## Comparison

  -----------------------------------------------------------------------
  Basis                   OSI                     TCP/IP
  ----------------------- ----------------------- -----------------------
  Nature                  Reference model         Protocol suite + model

  Layers                  7                       Commonly 4

  Practical use           Mainly                  Internet networking
                          reference/teaching      

  Session/Presentation    Separate layers         Usually handled within
                                                  Application

  Network layer           Network                 Internet

  Transport               Transport               Transport
  -----------------------------------------------------------------------

## Mapping

``` text
OSI                         TCP/IP

Application ┐
Presentation├────────────→ Application
Session     ┘

Transport ───────────────→ Transport

Network ─────────────────→ Internet

Data Link ┐
Physical  ┘──────────────→ Link / Network Access
```

## Sample

**Q. Compare OSI reference model and TCP/IP protocol suite with respect
to layer structure, functions and practical use. Show the mapping.**
