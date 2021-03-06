## Do multi-threaded multi-core programming in Ruby.

Instead of resorting to Erlang, Elixr, Rust, Go, and Akka to use the [Actor Model](https://goo.gl/YuzMrv) or do [Event-driven Programming](https://goo.gl/hs231Y), keep writing more and more powerful Ruby code in new ways. With Celluloid, anyone can write their own high-performance, light-weight server applications. But it doesn't stop at server applications...

### Celluloid is a Ruby gem that lets you turn any object into an Actor.

The joy of writing Ruby code doesn't end at high-performance concurrent, parallel, asynchronous, and distributed programming. Using the beautiful Ruby language and Celluloid, any kind of application can take full advantage of modern CPU's and cloud computing platforms, using the Actor model and Evented programming.

There are several gems in the Celluloid suite, and together they provide a complete toolset for actor-based evented multi-threaded, multi-core programming in Ruby:

* [Celluloid](https://github.com/celluloid/celluloid)
* [Celluloid::IO](https://github.com/celluloid/celluloid-io)
* [Celluloid::ZMQ](https://github.com/celluloid/celluloid-zmq)
* [Reel](https://github.com/celluloid/reel)
* [DCell](https://github.com/celluloid/dcell)
* Several [more](https://github.com/celluloid)...

## Some examples of Celluloid uses...

* HTTP/S and WebSocket Servers like those based on [Reel](https://github.com/celluloid/reel).
* Custom Domain Specific Languages like [Angelo](https://github.com/kenichi/angelo), for the web.
* Background processing backends like Sidekiq and [Sucker Punch](https://github.com/brandonhilkert/sucker_punch).
* High-performance protocol servers like [Celluloid::DNS](http://github.com/celluloid/celluloid-dns).
* Distributed computing systems like [DCell](https://github.com/celluloid/dcell).
* Telephone systems like [Adhearsion](https://github.com/adhearsion/adhearsion).
* Process monitoring tools like [Eye](https://github.com/kostya/eye).
* Countless uses outside server applications, like:
  * [IRC](https://github.com/tbuehlmann/vetinari)/Slack Bots, linking API Integrations.
  * Controlling multiple aerial drones and [robots](https://github.com/hybridgroup/artoo) simultaneously.
  * High-fidelity transaction data and financial information processing using [ZeroMQ](https://github.com/celluloid/celluloid-zmq).
  * Turning any program into a multi-threaded, evented, multi-core actor system.
