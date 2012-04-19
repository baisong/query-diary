query-diary
===========

Queryable personal diary using lojban

Store simple predicates in lojban for easy analysis, calculation, reporting, etc.

## Predicates

A lojban sentence (in a "canonical form" of predicate-first) is the base unit of data storage. Three BAI-series cmavo are provided for further info (time, location, participants).

For example, using <code>:

    predicate [x1 .. x5] [TIHU time] [TUHI location] [RIHI participants]
    
where

* predicate (required) := a valid lojban gismu
* x1 .. x5 (optional) := up to five lojban-parsed sumti (for now, lo + oneword and pro-sumti like mi, do, ra)
* time (optional) := time (i.e. "li mu", timestamp, "7:00 PM" etc.)
* location (optional) := location sumti (i.e. "ckule", latlong coords, map url)
* participants (optional) := names of others who took part in the experience

## Expanding Names

    "One or multiple word name" => la'o .gy. A multiple word name .gy.
    'oneowordname => la'oi onewordname

input:

    mencti mi lo skina "Harry Potter" tu'i zdani ri'i 'benny

expanded into grammatical lojban:

    mencti mi lo skina po'u la'o .gy. Harry Potter .gy. tu'i lo zdani ri'i la'oi benny

fully parsed:

    bridi: mencti (to mentally consume i.e. read/watch/experience)
    x1: mi (I)
    x2: lo skina po'u la'o .gy. Harry Potter .gy. (the movie "Harry Potter")
    time: (default now)
    location: lo zdani (at home)
    participants: benny
    
english gloss:

    I watched the movie "Harry Potter" at home with Benny.
    
## Persistent Definitions

You can save attributes to things you describe with le/lo or give names to (with la*). For example:

basic types are "Animal" (danlu), "Place" (stuzi), and "Thing" (dacti).

### Named Animals (danlu)

    remna 'benny
    // infers danlu la'oi benny lo remna
    cmene 'benny "Benjamin Butler"

    respa 'martin
    // infers danlu la'oi martin lo respa
    
### Named Locations (stuzi)

Locations have addresses (judri).

    judri "123 Electric Ave, NY 12345" lo zdani // infers stuzi lo zdani
    judri "100 Main Street, NY 12345" lo briju // also infers stuzi lo zdani
    
### Named Things (dacti)

    skami 'newton
    marce 'bessy