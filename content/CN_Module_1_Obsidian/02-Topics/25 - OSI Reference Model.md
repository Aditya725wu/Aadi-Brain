# OSI Reference Model

## Why it matters in PYQs

The provided 2026 CN paper asks how data is encapsulated while moving
down the OSI layers at the sender and decapsulated while moving up at
the receiver.

## Seven layers

``` text
7 Application
6 Presentation
5 Session
4 Transport
3 Network
2 Data Link
1 Physical
```

## Encapsulation

At sender, data moves from upper layers toward Physical layer. Each
relevant layer adds its control information/header.

## Decapsulation

At receiver, data moves upward and the corresponding control information
is processed/removed.

## Role asked in the 2026 paper

### Network layer

Responsible for logical addressing and routing/forwarding packets across
networks.

### Transport layer

Provides end-to-end transport services; reliability/flow control
mechanisms depend on the transport protocol.

## Answer structure

1.  Draw 7-layer stack.
2.  Show sender downward flow.
3.  Show receiver upward flow.
4.  Mention encapsulation/decapsulation.
5.  Explain Network and Transport roles.

## Sample

**Q. A student opens a web page from a remote server. Explain
encapsulation at the sender and decapsulation at the receiver. State the
roles of Network and Transport layers.**
