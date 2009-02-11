datum
=====
- each 'object' has data
- data themselves also can have data
- any missing data on an object or datum 'proxies' to that object's datum
  - PROBLEM: which of the object's many data do we query the meta-datum from?
    latest one created? declare "undefined behaviour" and leave it be? combine
    all appropriate meta-datum using some sort of logic?
- each datum can have sub-data
  - not to be confused with meta-data: meta-data are a normal data that is on
    a datum object; sub-data are to differentiate otherwise identical data at
    the same "level"

terminology
===========
- **Object**:
  Whatever we're applying Data to. Whatever we're applying the Datum system on 
  top of already has it's own definition of object - this could be a Ruby 
  object, a relational DB's row of data, a file - anything.
- **Datum** (plural *Data*):
  A pair of Key and Value, that can be applied to either an Object or another
  Datum. Any two Data with identical Keys and Values are, themselves, the same
  object in the system (a new Datum may not be created with the same content
  as an existing Datum; instead, said existing Datum is connected to whatever 
  was attempting to associate with an existing Datum). Data with the same keys 
  and values may still be differentiable due to Sub-data (see below).
- **Key**:
  A string of characters and numerals (`/[a-zA-Z_][a-zA-Z0-9_]*/`) denoting
  the 'type' or purpose of a Datum.
- **Value**:
  Either:
    - A reference to an Object
    - Optionally, if the implementation allows, a basic type: String or
      Numeric
- **Meta-datum** (plural *Meta-data*):
  A Datum that is attached to another Datum - indistinguishable from a Datum 
  applied to an Object. Not special in any way other than terminology (think 
  Class and Meta-class)
- **Sub-datum** (plural *Sub-data*):
  A special Datum that only makes sense in the context of its "Super-datum".
  May not have normal Data applied to it, may have Sub-data applied to it
  ("Sub-sub-data"?). The only situation when two Data will exist in the Datum
  system with the same key and the same value, is when they have different
  Sub-data. (Example: `{album: "Awesome" type: "Single"}` and `{album:
  "Awesome" type: "EP"}`)