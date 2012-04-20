query-diary
===========

Queryable personal diary using lojban

Store simple predicates through a prompt in lojban and store your thoughts and feelings... machine readable!

## Predicates

A lojban sentence (in a "canonical form" of predicate-first) is the base unit of data storage. Three BAI-series cmavo are provided for further info (time, location, participants).

Canonical form:

    predicate [x1 .. x5] [TIHU time] [TUHI location] [RIHI participants]
    
where

* predicate (required)<br/>a valid lojban gismu
* x1 .. x5 (optional)<br/>up to five lojban-parsed sumti (for now, lo + oneword and pro-sumti like mi, do, ra)
* time (optional)<br/>time (i.e. "li mu", "7:00 PM" etc., defaults to current timestamp)
* location (optional)<br/>location sumti (i.e. "ckule", latlong coords, map url)
* participants (optional)<br/>names of others who took part in the experience

## Abbreviations

names (la*)

    > "One or multiple word name"
    la'o .gy. A multiple word name .gy.
    
    > 'oneowordname
    la'oi onewordname

descriptions (lo)

    > /judri
    lo judri
    
    > /work
    na gismu li work li'u

lists

    > a, b, c, d
    a .e b .e c .e d
    
    > 'jan, 'feb, 'mar

abbreviations expand to internally stored 'grammatical' lojban:

    > mencti mi /skina "Harry Potter" tu'i /zdani ri'i 'benny
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
    
Why not just write your diary in idiomatic english? Because now that it's stored in lojban, it's regular and parseable! Now later on you can ask things like "what were the last 10 occasions I spent with Benny?" or "how long has it been since I saw Harry Potter?" or even more statistically interesting questions about trends and habits!

## Persistent Storage

You can save attributes to things you describe with le/lo or give names to (with la*). For example:

basic types are "Animal" (danlu), "Place" (stuzi), and "Thing" (dacti).

### Named Animals (danlu)

    > remna 'benny
    remna la'oi benny
    -- danlu lo remna
    danlu la'oi benny
    
    > cmene "Benjamin Butler" 'benny
    cmene la'o .gy. Benjamin Butler .gy. la'oi benny
    
    > respa 'martin
    remna la'oi martin
    -- danlu lo respa
    danlu la'oi martin
    
### Named Locations (stuzi)
    
    > judri "123 Electric Ave, NY 12345" /zdani
    stuzi lo zdani
    -- stuzi lo se judri
    judri la'o .gy. 123 Electric Ave, NY 12345 .gy. lo zdani
    
    > judri "100 Main Street, NY 12345" /briju
    judri la'o .gy. 100 Main Street, NY 12345 .gy. lo zdani
    -- stuzi lo se judri
    stuzi lo briju
    
### Named Things (dacti)

    > skami 'newton
    skami la'oi newton
    -- dacti lo skami
    dacti la'oi newton
    
    > marce 'bessy
    marce la'oi bessy
    -- dacti lo skami
    dacti la'oi newton
    
## Recalling Stored Info

    > cmene ma 'benny
    -- djani
    "Benjamin Butler"
