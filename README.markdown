metadati
========

- each 'object' has metadati
- metadati themselves also can have metadati
- any missing metadati on an object or metadati 'proxies' to that object's metadati
  - PROBLEM: which of the object's many metadati do we query the metametadati
    from? latest one created? declare "undefined behaviour" and leave it be?
    combine all appropriate metametadati using some sort of logic?
- each metadati can have sub-metadati
  - not to be confused with metametadati: metametadati are a normal metadati
    that is on a metadati object; sub-metadati are to differentiate otherwise
    identical metadati at the same "level"

terminology
===========
Object:
  Whatever we're applying Metadati to. Whatever we're applying the Metadati
  system on top of already has it's own definition of object - this could be
  a Ruby object, a relational DB's row of data, a file - anything.
Metadati:
  A non-object pair of Key and Value, that can be applied to either an Object
  or another Metadati. Any two Metadati with identical keys and values are
  themslves the same object in the system (a new Metadati may not be created
  with the same content as an existing Metadati; instead, said existing
  Metadati is connected to whatever was creating the new Metadati). Metadati
  with the same keys and values may still be differentiable due to
  Sub-metadati (see below).
Meta-metadati:
  A Metadati that is attached to another Metadati - indistinguishable from a
  Metadati applied to an Object.
Sub-metadati:
  A special Metadati that only makes sense in the context of its
  Super-metadati. May not have normal Metadati applied to it, may have
  Sub-metadati applied to it ("Subsubmetadati"?). Two identical (same object
  in the storage system) Metadati may be differentiated by the content or
  presence of a given sub-metadati.