# Irmo

_Metagraph store._

## Atoms

An Irmo _atom_ has an _ID_, two _endpoints_, and some _data_.

On my whiteboard, I like to represent them like this:

    <---------+--------->

That's actually a bad example, because atom's endpoints _cannot_ be _null_,
but bear with me.

Atoms are the Irmo core. There's nothing else. Literally _nothing_ else. I call
that nothing "the Irmo space" or "the void".

## Patterns

Patterns are combinations or usages of atoms that serve a particular purpose,
and a few are listed here so you don't have to figure them out yourself, and
so you know their name, because coordinated communication is important.

### Units

    /----\
    |    v
    \----+----\
         ^    |
         \----/

A _unit_ is a single _atom_ which points to itself. This is the only way that
a single atom can exist by itself in the Irmo void.

### Linked lists

    /----\     /----\
    |    v     |    |
    \----+---->+<---/
               |     /----\
               v     |    |
          /----+---->+<===x
          |    ^     |    |
          \----/     \----/

This is starting to get a bit confusing... Essentially, linked lists are
constructed by atoms that have one endpoint pointing to themselves, and the
other pointing to the next atom in the list. The last atom in a linked list is
a unit.

### Doubly linked list

    /----\
    |    v
    \----+----\
         ^    v
         \----+----\
              ^    v
              \----+----\
                   ^    |
                   \----/

Now each atom in the doubly linked list points to the next atom in the list
_and_ to the previous one, except for the first and last atoms which have one
endpoint each pointing to themselves.
