## You don't need to learn another language to do high-performance programming in Ruby.

Instead of pulling out Erlang, Elixr, Rust, Go, and frameworks like Akka to use the [Actor Model](https://goo.gl/YuzMrv) or do [Event-driven Programming](https://goo.gl/hs231Y). With Celluloid, anyone can write their own server applications, using Ruby. But it doesn't stop at server applications...

### Celluloid is a Ruby gem that lets you turn any object into an Actor.

The joy of writing Ruby code doesn't end at high-performance concurrent, parallel, asynchronous, and distributed programming. Using the beautiful Ruby language and Celluloid, any kind of application can take full advantage of modern CPU's, and cloud computing platforms. There are several gems in the Celluloid suite, and together they provide a complete toolset for multi-threaded, multi-core programming in Ruby.

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
