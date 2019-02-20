### With StatsD

To pipe metrics from an existing StatsD environment into Prometheus, configure
StatsD's repeater backend to repeat all received metrics to a `statsd_exporter`
process. This exporter translates StatsD metrics to Prometheus metrics via
configured mapping rules.

   +------------------+   +----------+                         +-------------------+                        +--------------+
   | Consul-telemetry | - |  StatsD  |---(UDP/TCP repeater)--->|  statsd_exporter  |<---(scrape /metrics)---|  Prometheus  |
   +------------------+   +----------+                         +-------------------+                        +--------------+
