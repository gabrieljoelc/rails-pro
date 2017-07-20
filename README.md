# Rails Pro
Rails is known for being a for going from zero to running application in minutes. Howerver, this isn't useful for getting the same low-friction experience for production-ready applications. Many times you end up having to add lots of boilerplate configuration and organization just to a real MVP app in production. This especially applicable when designing a microservice infrastrcture.

Here are some concepts that this library includes (in a very opionated way):
- Continuous Delivery / Continuous Integration
- Cluster orchestration (Kubernetes)
- 12-Factor apps (i.e. no `staging.rb`)
- View models / decorators (i.e. Draper)
- Single-sign on authentication and authorization (i.e. JWT)
- Admin dashboard (i.e. ActiveAdmin)
