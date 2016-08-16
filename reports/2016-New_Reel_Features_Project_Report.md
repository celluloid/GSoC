# Project : [Adding New Reel Features](https://github.com/pulkit4tech/reel/tree/gsoc16)
> Celluloid, Google Summer of Code 2016

### Summary
Reel is Celluloid::IO native, evented server which serves as bare-bones for http and webSocket server providing functionality such as Connection Management and Multithreading , Fault Tolerance. 
This project aims to extend Reel by adding new important features such as:
* Session Handler
* Multi-part parser

## Session Handler
* [Session Handler Code](https://github.com/pulkit4tech/reel/tree/final_sessions)
* [Session Handler examples](https://github.com/pulkit4tech/reel/tree/final_sessions/examples)
* [Session Handler Tests](https://github.com/pulkit4tech/reel/blob/final_sessions/spec/reel/session_spec.rb)

**Abstract**

Session Handler can be turned `on` into Reel by requiring `reel/session` module in application.Custom Session Configuration can be passed during server initialization as shown in this [example](https://github.com/pulkit4tech/reel/blob/final_sessions/examples/custom_session.rb) or else `DEFAULT` Session configuration will be used like in this [example](https://github.com/pulkit4tech/reel/blob/final_sessions/examples/hello_world_session.rb). After Header from request have been parsed, `Session Hash Value` is exposed depending on uuid recieved from request which can be accessed using `request.session`. Session value is added/updated into `Store` during `response` and corresponding uuid is set into `Cookie`. `Celluloid::Timers` are used for cleaning Session Values from Store after expiry and are `reset` if Session Value is updated, keeping Store clean and consistent. 

**Extension**

Currently we are using `Celluloid Concurrent Hash` for `Store`, but plan is to extend it by implementing multiple stores/supporting drivers like `Hash with mutex`, `Redis`, `Yaml`, `Mongodb` etc which can be used based on Application context.

## Multipart Parser
TODO: Introduction

## Other Links :
* [Project Abstract](https://summerofcode.withgoogle.com/projects/#5868033230766080)
* [My Blog](https://pulkit4tech.wordpress.com/)
* [About Me](https://about.me/pulkit4tech)
