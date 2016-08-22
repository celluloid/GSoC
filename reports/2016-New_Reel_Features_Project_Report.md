# [Adding New Reel Features](https://github.com/pulkit4tech/reel/tree/gsoc16)
> Celluloid, Google Summer of Code 2016

> Mentors : [@kenichi](https://github.com/kenichi) , [@digitalextremist](https://github.com/digitalextremist)

> **[Project Commits](https://github.com/pulkit4tech/reel/commits/gsoc16?author=pulkit4tech)**

### Summary
Reel is Celluloid::IO native, evented server which serves as bare-bones for http and webSocket server providing functionality such as Connection Management and Multithreading , Fault Tolerance. 
This project aims to extend Reel by adding new important features such as:
* **Session Handler**
* **Multipart Parser**

## Session Handler
* [Session Handler Code](https://github.com/pulkit4tech/reel/tree/final_sessions)
* [Session Handler examples](https://github.com/pulkit4tech/reel/tree/final_sessions/examples)
* [Session Handler Tests](https://github.com/pulkit4tech/reel/blob/final_sessions/spec/reel/session_spec.rb)

**Abstract**

Session Handler can be turned `on` into Reel by requiring `reel/session` module in application.Custom Session Configuration can be passed during server initialization as shown in this [example](https://github.com/pulkit4tech/reel/blob/final_sessions/examples/custom_session.rb) or else `DEFAULT` Session configuration will be used like in this [example](https://github.com/pulkit4tech/reel/blob/final_sessions/examples/hello_world_session.rb). After Header from request have been parsed, `Session Hash Value` is exposed depending on uuid recieved from request which can be accessed using `request.session`. Session value is added/updated into `Store` during `response` and corresponding uuid is set into `Cookie`. `Celluloid::Timers` are used for cleaning Session Values from Store after expiry and are `reset` if Session Value is updated, keeping Store clean and consistent. 

**Extension**

Currently we are using `Celluloid Concurrent Hash` for `Store`, but plan is to extend it by implementing multiple stores/supporting drivers like `Hash with mutex`, `Redis`, `memcached`, `Mongodb` etc which can be used based on Application context.

## Multipart Parser
* [Multipart Parser Code](https://github.com/pulkit4tech/reel/tree/multipart-0.0.1)
* [Multipart Parser examples](https://github.com/pulkit4tech/reel/blob/multipart-0.0.1/examples/hello_world_multipart.rb)
* [Multipart Parser Tests](https://github.com/pulkit4tech/reel/blob/multipart-0.0.1/spec/reel/multipart_spec.rb)

**Abstract**

Multipart Parser is built on using this parser [gem](https://github.com/danabr/multipart-parser). Multipart Parser can be included by requiring `reel/request/multipart` into application. Methods that are provided by `Multipart` module includes:
* multipart? : Checks for `Multipart Type` request (initialize parser engine if request is of multipart type).
* multipart : Parses `streaming request body` and returns : 
```
if multipart type
      return Hash :
      {
       key1 => {
         :data => Tempfile object (contains parsed data),
         :complete => true/false,
         :part => part object (header info etc)
       },
       key2 => {...}
     }
    if not multipart type
       return nil

Here keys are part.name for different file upload
```

**Extension**

Maintainance and updation of parser gem as per current need. Most of test are covered but still more to be added. 

## Other Links :
* [Project Abstract](https://summerofcode.withgoogle.com/projects/#5868033230766080)
* [Blog](https://pulkit4tech.wordpress.com/)
* [About Me](https://about.me/pulkit4tech)
