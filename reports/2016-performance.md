# Performance Improvement and Benchmarking
	Celluloid provides a simple and natural way to build fault-tolerant concurrent programs in Ruby.
##Summary
The primary goal of the project was to improve the performance of the underlying [Celluloid framework](https://github.com/celluloid/celluloid), explore future areas for performance improvement and create a benchmarking suite to lay the foundation for measuring future performance improvements.


###Celluloid
[Benchmarks & Test Suite](https://github.com/prathmeshranaut/celluloid/commits/multiplex?author=prathmeshranaut)

[Celluloid Pool](https://github.com/celluloid/celluloid-pool/pull/16) - Increased performance by upto 3 times.

[Instruction to Clone and run Celluloid](https://github.com/celluloid/celluloid/pull/721)

---
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
	

###Reel
[Tests - Pull Request](https://github.com/celluloid/reel/pull/227)

[Individual Commits](https://github.com/prathmeshranaut/reel/commits/master?author=prathmeshranaut)

---
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
2. Method Profiler reported that Fiber being called 10000 for only 2000 job in the Mutex profile. This might a place where we could further explore and make tweaks to make improvements.
3. Celluloid is using thread per actor so the `pool` benchmark is creating about `n` native threads. [Concurrent Ruby Actor](http://ruby-concurrency.github.io/concurrent-ruby/Concurrent/Actor.html) is using constant number of threads. 
4. There could be a possible bottleneck in the architecture of how Celluloid is written. We could definitely consider making architectural changes. [https://github.com/celluloid/celluloid/blob/master/architecture.md](https://github.com/celluloid/celluloid/blob/master/architecture.md)

##Other Details
[Github](https://github.com/prathmeshranaut)
[Blog](http://blog.prathmeshranaut.com)
[Celluloid](https://github.com/celluloid/celluloid)
[Reel](https://github.com/celluloid/reel)