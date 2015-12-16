# Scaling Intelligence: moving ideas forward 

* Be kind to learners - README, use imports, blog about it, stackoverflow

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

* lions share - automated tool for capturing allocation sources
* gc tenurary? if creating lots of objects, garbage will be pushed into old gen (only collected once full gc occurs)

# Idiomatic Scala: Your Options Do Not Match

* fold safe than getOrElse - compile safe
* Option.contains, e.g. Some("banana") contains "a" == true
* using HOF means you can evolve your codebase -> e.g. if Option moves to Seq

# Evolution, revolution, revelation... Trench stories in moving a team to Scala

* picking a project - independant from external services

# Lessions from Clojure

* things for state - ref, agent, atom (all non-blocking for reads)
* akka agents?
* protocols - add in behaviour to existing Types

# Securing Microservices using Play and Akka HTTP

* could split auth into each service, but then duplication, compilcation
* API gateway 
* basic auth
* oauth2 - is there enough support?
* json web token

# Why Scala for Hadoop

* Mapper - big, static, enterprisy

# Reactive in practice: web services with Scala and AWS 

* defaults - think about what will fit in memory on specific aws instance size
* Deploying to AWS - console, cli, sdk
* nohup sbt run & - not going to work if you scale elastically - use AMI
* slick db pool - HikariCP

# Inappropriate applications for Scala

## mpd decoding
* mutability - inside loops without letting state be exposed outside due to performance benefits

## game boy emulator
* seems simple, but old systems = tightly coupled monsters

# Typelevel - the benefits of collaboration

* http://non.github.io/

# Shapeless for mortals

* trait, implementation and implicits
* Singleton types - "bar".narrow = subclass of String, which is checked at compile time and erased back to String at runtime
* Witness - way to get at the singleton type from the value ? Typelevel to ValueLevel ??
* HList (Hetrogeneous List) - at compile type, know length and type of content
* LabelledGeneric - allows you to convert between HList and Case Class
* Coproduct - represents sealed trait with multiple implementations. generalised options.
** coproduct reading and writing. think of it as checking current format for name, if matches apply. otherwise go onto the next one. continue until find match
* trait A { type: T} - if you want to have implicit A and implicit T, need HipsterAux
* implicit resolution - for recurisve types. use laxy implicit to hint to the compiler that it will eventually be resolved
* keep formatters in separate package (scalac gets confused)

