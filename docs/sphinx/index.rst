Amphimixis Documentation
========================

Amphimixis is an automated project intelligence and evaluation tool for
performance and migration readiness. It helps inspect a project for existing
infrastructure such as CI, tests, benchmarks, dependencies, and build scripts,
then runs builds and collects performance data for further comparison.

Amphimixis uses ``perf`` for profiling and produces a cross-table with two
builds per CPU event for comparison.

Who Is This For
---------------

.. grid:: 1 1 3 3

   .. grid-item-card:: Performance analysis
      :text-align: center

      Compare toolchains, compiler flags, and architectures.
      Precise cross-table deltas for every CPU event.

   .. grid-item-card:: One-click profiling
      :text-align: center

      Containerized runs via Podman.
      Overnight batch analysis with morning reports.
      LLM-assisted project investigation.

   .. grid-item-card:: Students & hobbyists
      :text-align: center

      Accessible entry point for porting projects to RISC-V.
      Step-by-step guidance without deep build system expertise.

   .. grid-item-card:: Enterprise readiness
      :text-align: center

      Evaluate application migration readiness for RISC-V at scale.
      Assess buildability, tests, and performance across platforms.

   .. grid-item-card:: Contributing
      :text-align: center

      Easy patch workflow for open-source contributors.
      CI validates changes automatically on every push.

Quick Run
---------

If you want to try Amphimixis right away, create a virtual environment, install
the package from GitHub, and run the full pipeline on a target project:

.. code-block:: bash

   python3 -m venv .venv
   source .venv/bin/activate
   pip install git+https://github.com/Amphimixis/amphimixis.git@stable
   amixis init local
   amixis run /path/to/project --config local.yml

Requirements
------------

- Python 3.12 or later
- Linux
- ``rsync`` on each machine
- ``sshpass`` on the machine where you run Amphimixis if you connect to remote
  machines with passwords
- ``perf`` on each ``run_machine``
- ``perf archive`` on each ``run_machine``
- a supported build setup in the target project: CMake as the build system and
  Make as the low-level runner

What Amphimixis Does
--------------------

Amphimixis can:

- analyze a project for CI, tests, benchmarks, build system configuration, and
  dependencies;
- build the project with configured recipes and platforms;
- profile executable runs and collect timing and ``perf``-based statistics;
- compare profiling outputs produced for different builds and put them into a
  cross-table for each CPU event.

.. toctree::
   :maxdepth: 2
   :caption: Getting Started

   usage_guide
   config_instruction
   input
   troubleshooting

.. toctree::
   :maxdepth: 1
   :caption: Technical

   api/index
