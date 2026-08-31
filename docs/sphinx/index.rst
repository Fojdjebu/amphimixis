Amphimixis Documentation
========================

.. raw:: html

   <p class="hero-tagline">Slogan goes here</p>

.. container:: hero

   Amphimixis is an automated project intelligence and evaluation tool for
   performance and migration readiness. It helps inspect a project for existing
   infrastructure such as CI, tests, benchmarks, dependencies, and build scripts,
   then runs builds and collects performance data for further comparison.

   Amphimixis uses ``perf`` for profiling and produces a cross-table with two
   builds per CPU event for comparison.

Workflow
--------

.. grid:: 1 1 4 4

   .. grid-item-card:: Analyze
      :text-align: center

      Inspect CI, tests, benchmarks, build config and dependencies.

   .. grid-item-card:: Build
      :text-align: center

      Build with configured recipes and platforms.

   .. grid-item-card:: Profile
      :text-align: center

      Run executables and collect timing and ``perf`` statistics.

   .. grid-item-card:: Compare
      :text-align: center

      Produce a cross-table per CPU event.

Requirements
------------

- Python 3.12 or later
- Linux
- ``rsync`` on each machine
- ``sshpass`` on the machine that connects to remote hosts with passwords
- ``perf`` and ``perf archive`` on each ``run_machine``
- Target project must support CMake as the build system and Make or Ninja as the low-level runner

See :doc:`troubleshooting` for installation commands and the ``perf archive`` setup.

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

.. toctree::
   :maxdepth: 2
   :caption: Getting Started
   :hidden:

   usage_guide
   config_instruction
   input

.. toctree::
   :maxdepth: 2
   :caption: For Users
   :hidden:

   methodology
   user_stories

.. toctree::
   :maxdepth: 2
   :caption: Support
   :hidden:

   troubleshooting

.. toctree::
   :maxdepth: 1
   :caption: Technical
   :hidden:

   api/index
