# Performance Improvement and Benchmarking
> Celluloid provides a simple and natural way to build fault-tolerant concurrent programs in Ruby.

>Mentors : [@chuckremes](https://github.com/chuckremes), [@digitalextremist](https://github.com/digitalextremist)

##Summary
The primary goal of the project was to improve the performance of the underlying [Celluloid framework](https://github.com/celluloid/celluloid), explore future areas for performance improvement and create a benchmarking suite to lay the foundation for measuring future performance improvements.

---
###Celluloid
[Benchmarks & Test Suite](https://github.com/prathmeshranaut/celluloid/commits/multiplex?author=prathmeshranaut)

[Celluloid Pool](https://github.com/celluloid/celluloid-pool/pull/16) - Increased performance by upto 3 times.

[Instruction to Clone and run Celluloid](https://github.com/celluloid/celluloid/pull/721)


####Abstract
The benchmarking suite was created to measure the performance improvements done while making tweaks to the code. Changes made in pool resulted in the performance increase of about 3x times.

#### Before	
	Rehearsal ----------------------------------------------
	pool - 10    0.060000   0.000000   0.060000 (  0.065491)
	pool - 100   0.050000   0.000000   0.050000 (  0.058047)
	------------------------------------- total: 0.110000sec
                user     system      total        real
	pool - 10    0.140000   0.000000   0.140000 (  0.145850)
	pool - 100   0.040000   0.000000   0.040000 (  0.040523)

#### After
	Rehearsal ----------------------------------------------
	pool - 10    0.060000   0.000000   0.060000 (  0.061735)
	pool - 100   0.050000   0.000000   0.050000 (  0.058645)
	------------------------------------- total: 0.110000sec

                 user     system      total        real
	pool - 10    0.040000   0.000000   0.040000 (  0.043268)
	pool - 100   0.040000   0.010000   0.050000 (  0.041099)
	
![Method Profile of Actor](http://i.imgur.com/0WDvAbV.png)

---
###Reel
[Tests - Pull Request](https://github.com/celluloid/reel/pull/227)

[Individual Commits](https://github.com/prathmeshranaut/reel/commits/master?author=prathmeshranaut)

####Abstract
Reel is Celluloid::IO native, non-blocking evented server. The main aim here was to improve the test suite which can be seen in the above link and create a benchmarking suite, which couldn't be completed. This is something I plan on doing after the completion of GSoC.

##Tools Used
1. [RubyProf](https://github.com/ruby-prof/ruby-prof)
2. [StackProf](https://github.com/tmm1/stackprof)
3. [Method Profiler](https://github.com/change/method_profiler)
4. [QCacheGrind](https://kcachegrind.github.io/html/Home.html)

#Challenges
1. Understanding meta-programming
2. Working with profiling tools in a concurrent environment.
3. Developing consistent benchmark results.

# Scope for future improvements
1. Based on the benchmark results, Sidekiq 4 calls a method called `safe_thread` for creating new Threads whereas Celluloid deals with `mutex` and suspending `Threads`.
2. Method Profiler reported that Fiber being called 10000 for only 2000 job in the Mutex profile. This might a place where we could further explore and make tweaks to make improvements. ![Method Profile of Fiber](http://i.imgur.com/NJf4VqM.png)
3. Celluloid is using thread per actor so the `pool` benchmark is creating about `n` native threads. [Concurrent Ruby Actor](http://ruby-concurrency.github.io/concurrent-ruby/Concurrent/Actor.html) is using constant number of threads. 
4. There could be a possible bottleneck in the architecture of how Celluloid is written. We could definitely consider making architectural changes. [https://github.com/celluloid/celluloid/blob/master/architecture.md](https://github.com/celluloid/celluloid)blob/master/architecture.md)

# Commits

###Celluloid Pool
[Removed redundant code, improves performance by upto 3 times](https://github.com/prathmeshranaut/celluloid-pool/commit/b4e42515cfe6095372ce436fd9a2a991b7f3ea5e)

###Celluloid

[Fixed issues with RuboCop](https://github.com/prathmeshranaut/celluloid/commit/8b0ebefaece96d4d00593c7ffca2d30d3d1b2dc8)

[Added comments to the pool benchmark](https://github.com/prathmeshranaut/celluloid/commit/8575b64d75416c39779d075ef51ed9c987d2f3f4)

[updated the results of the pool benchmark](https://github.com/prathmeshranaut/celluloid/commit/fb795163aa035ff8f29419f9134403555bbd6401)

[Updated pool benchmark code](https://github.com/prathmeshranaut/celluloid/commit/c5e50e28437c87079079051ad21d19e8abe5e70d)

[Added Mailbox benchmark](https://github.com/prathmeshranaut/celluloid/commit/1f185b3fbee9827bd9149d1f0b8741529aa24dc2)

[Benchmarking various pool sizes](https://github.com/prathmeshranaut/celluloid/commit/9d888c303502d2cfbb1ca449180e7d076e3057fb)

[Added Async countdown latch benchmark](https://github.com/prathmeshranaut/celluloid/commit/72787ac19d963c77e5d5cdd30bb2a6e4fd4ef910)

[Added results for ring benchmark](https://github.com/prathmeshranaut/celluloid/commit/792b50c500e01fc475da2cdb1aae2676b11d3851)

[Added results for actor benchmarks](https://github.com/prathmeshranaut/celluloid/commit/d954074714ac93321a13673ddc221920c1956887)

[Added benchmark results in the future benchmark results](https://github.com/prathmeshranaut/celluloid/commit/94811fe9a74b4ff4a7f901be9669e895b3a81b5e)

[Added Async Spawn benchmark](https://github.com/prathmeshranaut/celluloid/commit/92d19d38e4db1ad3465e74ad1f6bdb5cdf058d50)

[Added benchmark for futures](https://github.com/prathmeshranaut/celluloid/commit/bbe55e21999043392c3191de22b02892391d022a)

[Fixed Actor test](https://github.com/prathmeshranaut/celluloid/commit/94cacc6bb0d86f6426e02f46200af6f27a321589)

[Re-Added spec helper](https://github.com/prathmeshranaut/celluloid/commit/dec2e0a5239c2a1a15d2ceade4c5c8fc3bd86ac8)

[Converted all the fail exceptinos to raise for convention and testing](https://github.com/prathmeshranaut/celluloid/commit/b6e99e2a639034602d0a92e85de8b301c6ece1ba)

[Added test for mailbox example](https://github.com/prathmeshranaut/celluloid/commit/69eb36779170904c82d83069111e5de78f9453d9)

[Instruction for cloning Celluloid via github](https://github.com/prathmeshranaut/celluloid/commit/f403f59a5b2a671537bfa3af5a4069e3b0ac8ce5)

[Merge branch 'multiplex' of https://github.com/celluloid/celluloid](https://github.com/prathmeshranaut/celluloid/commit/d96ea3699d0a
---41583ade963a512b81a7f31a3dd1)

###Reel
[Extracted the example request string](https://github.com/prathmeshranaut/reel/commit/9a8ed5fb91935ab8c90c2f1f47b9194d30057ac9)

[Added test for array and non-string websocket messages](https://github.com/prathmeshranaut/reel/commit/bd7f592c4f54a8269b96aaaa031ffe737af2c511)

[Spec to write array messages](https://github.com/prathmeshranaut/reel/commit/ff9047a52c817fae4b2f1628d43530ea9d5e7606)

[Refactored a test](https://github.com/prathmeshranaut/reel/commit/1dfca6bcdd7ad9d986bc665b1648bb2eb87a1873)

[Added a test to make sure that the connection detaches successfully](https://github.com/prathmeshranaut/reel/commit/09afb91c1242bb1b7d74615bbb721c00242bfce0)

[Added tests for Reel::Request](https://github.com/prathmeshranaut/reel/commit/f36f4cf2e58d3314addbbc7a552a24f8c7cc1043)

[Updated web socket specs to new Celluloid internal APIs](https://github.com/prathmeshranaut/reel/commit/60e408ae0b31abd5ce757da4d4bc87e5a8bd3a2e)

##Other Links
* [Github](https://github.com/prathmeshranaut)
* [Blog](http://blog.prathmeshranaut.com)
* [Celluloid](https://github.com/celluloid/celluloid)
* [Reel](https://github.com/celluloid/reel)