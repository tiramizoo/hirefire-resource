## v0.7.4/Master

* Attempt to fix an issue where the STDOUT IO Stream has been closed for an unknown reason.
  * This resulted in errors in an application with `log_queue_metrics` enabled after a random period of time.

## v0.7.3

* Added priority queue support for bunny message count.
  * Allows for passing in the `x-max-priority` option when opening up a queue to check the messages remaining.
  * Usage: `HireFire::Macro::Bunny.queue(queue, amqp_url: url, "x-max-priority": 10 )`

## v0.7.2

* Changed Que macro to query take into account scheduled jobs.

## v0.7.1

* Made entire library threadsafe.

## v0.7.0

* Made `HireFire::Resource.log_queue_metrics` optional. This is now disabled by default.
  * Enable by setting `log_queue_metrics = true`.
  * Required when using the `Manager::Web::Logplex::QueueTime` autoscaling strategy.
