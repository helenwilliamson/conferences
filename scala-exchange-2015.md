# Count-Min sketch

## Problem
* sketch - summary of data structure
* hugh data max peak 143k per second
* want real time analytics of this data

## Count-Min sketch
* d (depth = rows) - probability
* w (width = columns) - error
* uniform hash functions so average inaccurancy is low
* start with an error tolerance, using that, apply function to determine width and depth required

## Usage
* eps = depth
* delta = width

# Towards Functional Programming with Finagle

* Instead of just saying "Scala", described it as wanting to use Functional programming (maintainability) 
* Twitter Future vs Scala Future = Twitter future can be cancelled
* Stacks = groups of factories (things that evalutate to a function). stack configured with set of configuration to build a set of filters for that configuration
* performance testing using gatling (service to be tested using spray)# 
* finagle modules written in same style (one of 2 styles)
* HOCON

# With Resilience - nothing else matters

* complicated isn't complex (complex more about rules => can't actually understand the whole system, complicated you can)
* complex systems mostly run broken - and people make things worse
* operating at the edge of failure - operate inside accident, economic fialure and unacceptable workload
* what's the force pushing it back away from accident boundary? devs push back from workload, business bushes back from economic. 
* operate around marginal boundary, then decide that as everything is ok, move marginal boundary closer to accident boundary. then more likely to cross it
* puppies! now i have your attention, complexity theory
* anti-fragile systems - grow stronger rather than just get back to where you were
* how to get distribution / decoupling in space? (i.e. distributed over multiple nodes)
** start with weak consistency guareentees around boundaries, but inside boundary have strong consistency
** strong consistency leads to strong coupling
* ACID 2.0 - associative (batch insensitive, group how you want), commuative (ordering insensitive), idempotent (duplication is ok), distributed

# A purely functional apporach to building large applications

* what did you use for your slides?
* monad transformers - think of them as being able to work on the inner type, e.g. Future[Option[Int]], OptionT[Future, Int] can work on the Int inside the Option
* kleisli - extracts out types , e.g. String => Future[Int] gives ReaderT[Future, String, Int] 

# Optimising Scala for Fun & Profit
