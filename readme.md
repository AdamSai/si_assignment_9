# Assignment 9: The Twelve-Factor App

[Assignment description](https://datsoftlyngby.github.io/soft2020fall/resources/80748096-A9-12-Factor-App.pdf)

At first I thought about reordering the points by portability, but I noticed that the order would pretty much stay the same.
Re-ordering by importance is also hard, as it seems like the current order makes a lotof sense.

1. Codebase
   One codebase tracked in revision control, many deploys
2. Dependencies
   Explicitly declare and isolate dependencies
3. Config
   Store config in the environment
4. Backing services
   Treat backing services as attached resources (The current production database could be detached, and the new database attached – all without any code changes.)
5. Build, release, run
   Strictly separate build and run stages
6. Processes
   Execute the app as one or more stateless processes
7. Port binding
   Export services via port binding
8. Concurrency
   Scale out via the process model
   (Twelve-factor app processes should never daemonize or write PID files. Instead, rely on the operating system’s process manager (such as systemd, a distributed process manager on a cloud platform, or a tool like [Foreman](http://blog.daviddollar.org/2011/05/06/introducing-foreman.html) in development) to manage output streams, respond to crashed processes, and handle user-initiated restarts and shutdowns.)
9. Disposability
   Maximize robustness with fast startup and graceful shutdown
10. Dev/prod parity
    Keep development, staging, and production as similar as possible
11. Logs
    Treat logs as event streams
    (A twelve-factor app never concerns itself with routing or storage of its output stream. It should not attempt to write to or manage logfiles. Instead, each running process writes its event stream, unbuffered, to stdout. During local development, the developer will view this stream in the foreground of their terminal to observe the app’s behavior.)
12. Admin processes
    Run admin/management tasks as one-off processes
    Sources used:  
    https://12factor.net
