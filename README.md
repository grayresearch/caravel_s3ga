# S3GA
By Jan Gray. Copyright (C) 2022, Gray Research LLC.
Licensed under the Apache License, Version 2.0.

[S3GA](https://fpga.org/2022/11/30/s3ga-part-1-beginnings/)
is a *Simple Scalable Serial field programmable Gate Array* fabric targeting the
[caravel_user_project](https://github.com/efabless/caravel_user_project)
of [efabless](https://efabless.com)
[MPW-8](https://platform.efabless.com/shuttles/MPW-8) Open MPW shuttle.

This serial FPGA evaluates N logical LUTs using N/M real LUTs,
over M cycles.  Thus it trades off latency (logical clock period)
for greater capacity by amortizing the gate and wiring area of
lookup table input and output multiplexers (muxes) and
routing switches.

It provides a pipelined, hierarchical (recursive B=4-way cluster
partitions) fat-tree interconnect, routing serial input and output nets
amongst logic blocks and IOs, enabling a simple place and route using
recursive min-cut 4-partitions of the input netlist hypergraph.

...
