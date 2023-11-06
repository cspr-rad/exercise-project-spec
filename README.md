# Introduction

Creative coding exercises permit an engineer and by extension a wider team, to be **immediately** productive in terms of coding and upskilling.  Via a playful exploration of a problem domain for which a production system is to be built, an organic solution discovery process is thereby set in motion.  In addition and perhaps most importantly, they permit healthy team dynamics to emerge via a collegiate approach to collaboration and solution sharing in a non zero-sum process.

It is highly recommended that engineers discover a solution space with as little input from other engineers as possible.  I.E. they ought to minimise short-cuts so as to more fully understanding the nuances of the problem space.  An exception to this soft rule applies when an engineer finds themselves blocked to the extent that they are losing momentum, in this case a burst of communication and support will typically resolve the impasse.  If regaining momentum is still elusive, then refinement of the problem domain will be required. 

From a quality perspective, each engineer's solution must be as close as possible to a production grade system as possible.  This will force the engineer to address cross-cutting concerns such as testing, serialisation, logging, instrumentation, security, dev-ops.  Testing should thus be at varying degrees of granularity, i.e. unit, functional, integration.  A successful exercise will result in a battery of standardised tests running within a CI/CD process. 

At certain milestones in the process, each engineer's solution is to be publically peer reviewed by other team members, typically via a code tour.  The objective of such reviews are to introduce a transparent feedback loop leading to a deeper collective understanding and an improved set of solutions. Junior engineers should be able to solicit informal reviews at any moment. 

Above all a creative coding exercise should be genuinely fun.  Engineers should find themselves engaged, enthused and in the flow.  Whilst the more experienced team members should take a real pride in showing off their skills, the less experienced team members should find a real joy in playful upskilling.  Collectively the team should observe the emergence of a healthy collaborative dynamic.  

# Exercise Overview

The purpose of this particular exercise is to progressively introduce engineers, potentially new to Rust and/or ZK cryptography, to various elements of a complex problem domain.  Each domain element will ultimately play a role in a production system designed to support servicing portfolios of financial contracts issued in conformance to the ACTUS standard.   

The exercise will initially focus upon implementing a backend system along with a CLI utility for interacting with the system.  Overtime the exercise focus will pivot to front-end development.  The end result will be a full stack solution enabling a customer to issue an ACTUS compliant financial contratc.    

The sytem is composed of 5 nodes, each node being a single process that runs an identical binary.  The node software exposes some form of API surface that will accept computational payloads.  For each received computational payload, the node returns a compute identifier and routes the payload to a ZK proving sub-system for processing.  Once processed the resultant proof is shared with the other nodes, each node will retain a local copy of the proof.

A client facing CLI program will allow a user to dispatch a computation payload to a random node.  The CLI program will report to the user the compute identifier.  The user subsequently interrogates a random node for the generated computational proof.  Optionally, the proof itself can subsequently be dispatched to a random node for verification purposes.

