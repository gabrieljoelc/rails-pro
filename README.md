# Rails Pro
Rails is known for being able to go from zero to a running application in minutes. Howerver, it does not give you the same low-friction experience for shipping a production-ready application. Many times you end up having to add lots of boilerplate configuration and organization just to get a real-world MVP app into production. This is especially applicable when designing a microservice infrastrcture.

Here are some concepts that this library includes (in a very opionated way):
- Continuous Delivery / Continuous Integration
- Cluster orchestration (Kubernetes)
- 12-Factor apps (i.e. no `staging.rb`)
- View models / decorators (i.e. Draper)
- Single-sign on authentication and authorization (i.e. JWT)
- Admin dashboard (i.e. ActiveAdmin)
- Email set up for prod (i.e. pluggable smtp) and development (i.e. letter opener)
