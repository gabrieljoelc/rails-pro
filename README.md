# Rails Pro
Rails is known for being able to go from zero to a running application in minutes. Howerver, it does not give you the same low-friction experience for shipping a production-ready application. Many times you end up having to add lots of boilerplate configuration and organization just to get a real-world MVP app into production. This is especially applicable when designing a microservice architecture.

Here are some practical ingredients this library will include out-of-the-box (yes, it's very opinionated):
- Backend
  - Single-sign on authentication and authorization (i.e. JWT)
  - Email set up for prod (i.e. pluggable smtp) and development (i.e. letter opener)
  - Admin dashboard (i.e. ActiveAdmin)
  - Disable ActiveRecord callbacks
  - Disable ActionController callbacks
  - Make ActiveRecord setters private
  - Add unit-of-work helper or wrapper (i.e. in ActionController and workers)
- Cross-service communication
  - Versioned pub/sub (i.e. Kafka framework or [`la_gear`](https://github.com/giftcardzen/la_gear))
  - [Zipkin](https://zipkin.io/)
  - API infrastructure including swagger support
- Frontend
  - View models / decorators (i.e. [Draper](https://github.com/drapergem/draper))
  - [Vue.js](https://vuejs.org/) or React.js
  - Task-based 
- DevOps
  - Continuous Delivery / Continuous Integration
  - 12-Factor apps (i.e. no `staging.rb`)
    - ENV configuration (i.e. [`ENVied`](https://github.com/eval/envied))
    - Docker for production and development
  - Cluster orchestration (Kubernetes)
- Testing
  - TODO

## Design Philosophy

TL;DR: This framework favors strong opinions over "flexibility".

This may seem anti-Rails or maybe even anti-Ruby, but I don't think it is. You are still getting to:
- Write readable and expressive Ruby code
- Be responsible for the ease and danger of chaining collection methods
- Define service boundaries and design a microservice architecture with a framework you are familiar with

### Other principles included
- Smaller focused services over all-the-things services (TODO: define reek-style lint at the service level?)
- 12-factor over `Rails.env.development?` checks
- Favor task-based user interaction over RESTful (i.e. pub/sub async over API calls)
  - Favor widgets over JSON
- Favor integration tests over unit tests (if the whole application behaves as expected, then it works)
- Favor Ruby over JavaScript
- Dependency injection as first-order pattern
- Unit-of-work as first-order pattern
- Favor custom code over libraries
  - Libraries are allowed if they are battle tested (TODO define specific library requirements)

### Analogy

A monolithic application is like a dictionary or encyclopedia--you will never read the whole thing but you shouldn't need to because you can use the reference tools. Dynamic languages don't have the reference tools needed for monolithic applications to make a developer productive. You end-up having secrets in the codebase where you need human compilers. *You should use a statically-typed lanague for monolithic apps.*

A microservice application is like a short novel--you should be able to read the whole thing in about a day and pretty much get the story. Dynamic languages like Ruby are easy to read and reason about if the codebase is clean and focused whereas many statically-typed langauages are needlessly verbose for microservices. *You should use dynamically-typed lanagues for microservices.*

The challenge with the latter is the friction required in spinning up new services as needed. This library attempts to lower that friction.
