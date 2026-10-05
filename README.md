# VisualSim Challenge 1 --- Innovate, Model and Explore a New System

## Project Title

**Design-Space Exploration of a Quad-Core ARM Cortex-A53 Memory
Subsystem Using VisualSim Architect**

## Challenge

**Challenge 1 --- Innovate, Model and Explore a New System**

## Overview

This project uses VisualSim Architect to model and explore a quad-core
ARM Cortex-A53 memory subsystem. The study evaluates how changes in
memory-system architecture affect measured workload performance.

The selected VisualSim model contains four ARM Cortex-A53 cores and a
shared memory subsystem consisting of an L2 cache, system
bus/interconnect, memory controller, cycle-accurate DRAM, DDR4 memory,
and AXI/bus arbitration infrastructure.

## Design-Space Exploration

The following architectural parameters were explored:

  Parameter             Configurations
  --------------------- --------------------------
  L2 Cache Size         256 KB, 1 MB, 2 MB
  System Bus Width      64-bit, 128-bit, 256-bit
  DDR4 Speed            3200 MHz, 4266 MHz
  Simulation Duration   2 ms

## Performance Metrics

The simulations were evaluated using:

-   L2 hit ratio
-   L2 miss ratio
-   L2 average latency
-   L2 utilization
-   L2 throughput
-   System Bus utilization
-   DRAM throughput
-   DRAM average delay
-   Maximum DRAM queue usage
-   Request overflow

## Key Results

The recorded simulations show that increasing memory-system resources
does not necessarily produce proportional workload-level performance
improvement.

### L2 Cache

The recorded 1 MB configuration produced an L2 hit ratio of **48.1891%**
and an average latency of **94.9896 ns**.

The recorded 2 MB / 64-bit / 3200 MHz configuration produced a hit ratio
of **43.51%** and an average latency of **103.67 ns**.

This indicates that increasing cache capacity did not automatically
improve the measured cache performance for the evaluated workload.

### System Bus

Recorded 128-bit and 256-bit configurations produced approximately
**66.3691 MB/s** DRAM throughput.

The recorded 256-bit configuration had approximately **4.8933%** bus
utilization and **0** request overflow.

The results indicate that raw bus width was not a dominant limitation
for the evaluated workload.

### DDR4

Increasing the nominal DDR4 speed from **3200 MHz to 4266 MHz** produced
only a marginal change in measured DRAM behavior.

Recorded throughput remained approximately **66.3--66.4 MB/s**, while
average DRAM delay remained around **14.19 ns**.

## Engineering Insight

The main engineering insight is that more hardware resources do not
automatically translate into better workload-level performance.

A wider bus or faster memory may provide greater theoretical bandwidth,
but if the workload does not generate enough traffic to use that
additional capability, the measured benefit can remain limited.

Therefore, architecture decisions should be based on measured workload
behavior rather than simply selecting larger or faster components.

## Repository Contents

-   `Online_Ultrascale_Trace.xml` --- modified VisualSim model
-   `arm_isa_a53_gem5.txt` --- required model dependency
-   `Trace_Input/` --- trace/input files required by the model
-   `Results/` --- simulation statistics and supporting results
-   `Documentation/` --- technical write-up and presentation, if
    included

## Tools

-   VisualSim Architect
-   ARM Cortex-A53 benchmark/trace model

## Reproducibility

The VisualSim model and supporting input/dependency files are provided
in this repository so that the model can be reviewed and, where the
required VisualSim environment is available, executed.

Simulation results reported in the technical write-up are based on
actual VisualSim Architecture Statistics generated during the project.

## Deliverables

This repository supports the Challenge 1 submission by providing the
project/model evidence. The presentation, technical write-up, and
demonstration video are provided through the submission form or their
respective links.
