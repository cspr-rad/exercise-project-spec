# Introduction

Creative coding exercises permit an engineer and by extension a wider team, to be **immediately** productive in terms of coding and upskilling.  Via a playful exploration of a problem domain for which a production system is to be built, an organic solution discovery process is thereby set in motion.  In addition and perhaps most importantly, they permit healthy team dynamics to emerge via a collegiate approach to collaboration and solution sharing in a non zero-sum process.

In such exercises, it is highly recommended that engineers **discover** a solution space with as little input from other engineers as possible.  I.E. they ought to minimise short-cuts so as to more fully understanding the nuances of the problem space.  An exception to this soft rule applies when an engineer finds themselves blocked to the extent that they are losing momentum, in this case a burst of communication and support typically resolves the impasse.  If regaining momentum still proves elusive, then refinement of the problem domain itself will be required. 

From a quality perspective, each engineer's solution must be as close as possible to a **production grade** system as possible.  This requirement forces the engineer to address cross-cutting concerns such as testing, serialisation, logging, instrumentation, security, dev-ops.  Testing should thus be at varying degrees of granularity, i.e. unit, functional, integration.  A successful exercise will result in a battery of standardised tests running within a CI/CD process. 

At certain milestones in the process, each engineer's solution is to be publically **peer reviewed** by other team members, typically via a code tour.  The objective of such reviews are to introduce a transparent feedback loop leading to a deeper collective understanding and an improved set of solutions. Junior engineers should be able to solicit informal reviews at any moment. 

Above all a creative coding exercise should be genuinely fun.  Engineers should find themselves engaged, enthused and in **the flow**.  Whilst the more experienced team members should take a real pride in showing off their skills, the less experienced team members should find a real joy in playful upskilling.  Collectively the team should observe the emergence of a healthy collaborative dynamic.  

# Project Overview

The purpose of this particular exercise is to progressively introduce teams, potentially new to Rust and/or ZK cryptography, to various elements of a complex problem domain.  Each domain element plays a role in a production system designed to have a real **social impact** in communities where access to simple financial services maybe constrained.  

The system will be a white-labelled **micro-finance** platform.  Via the platform's front-end application(s), *liquidity providers* will be able to bootstrap loan books, *loan agents* will be able to utilize liquidity so as to issue micro-loans to members of the communities served by the agent(s), and eligible *customers* will be able to take out mico-loans to spend as they see fit. 

Loans issued via the platform will conform to the [ACTUS standard](https://www.actusfrf.org/taxonomy), specifically the [ANN](http://demo.actusfrf.org/form/ANN) contract type.  Each loan will be associated with a **zero-knowledge proof** that can be used to verify the integrity of loan payments.  

From an **implementation** perspective, the project will initially focus upon implementing the system's backend.  Once the backend is in place, the project pivots to a white-labelled front-end.  The front-end should simple to use and support real-time notifications.
