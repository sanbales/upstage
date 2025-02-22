# UPSTAGE

UPSTAGE is a **U**niversal **P**latform for **S**imulating
**T**asks and **A**ctors with **G**raphs and **E**vents built atop
[*SimPy 4*][simpy].

## What is UPSTAGE for?

The Universal Platform for Simulating Tasks and Actors with Graphs and Events (**UPSTAGE**) library is a Python framework for creating robust, behavior-driven Discrete Event Simulations (DES). The primary goal of UPSTAGE is to enable the quick creation of simulations at any desired level of abstraction with built-in data recording, simulation integrity and runtime checks, and assistance for the usual pitfalls in custom discrete-event simulation: interrupts and cancellations. It is designed is to simplify the development process for simulation models of *complex systems of systems*.

UPSTAGE - which is built on the `SimPy`_ library - contains two primary components that are assembled to create a broad array of simulations.

The components are `Actor` - which contain `State` - and `Task`, which can be assembled into a `TaskNetwork`. Actors can have multiple networks running on them, their states can be shared, and there are features for interactions between task networks running on the same actor. Those tasks modify the states on their actor, with features for
real-time states that update on request without requiring time-stepping or modifying the existing events.

![image](docs/source/_static/upstage-flow.png)

Additional features include:

1. Context-aware `EnvironmentContext`, accessed via `UpstageBase`, enabling thread-safe simulation globals for the Stage and Named Entities (see below).
1. Active States, such as `LinearChangingState` which represent continuous-time attributes of actors at discrete points.
1. Spatial-aware data types like `CartesianLocation`, and states like the waypoint-following `GeodeticLocationChangingState`.
1. Geodetic and cartesian positions, distances, and motion - with ranged sensing.
1. `NamedEntity` in a thread-safe global context, enabling easier "director" logic creation with fewer args in your code
1. The stage: a global context variable for simulation properties and attributes. This enables under-the-hood coordination of motion, geography, and other features.
1. Rehearsal: Write planning and simulation code in one place only, and "rehearse" an actor through a task network using planning factors to discover task feasibility.
1. All States are recordable
1. Numerous runtime checks and error handling for typical DES pitfalls: based on years of custom DES-building experience.
1. And more!

See the [documentation](https://gtri.github.io/upstage) for tutorials and details.

## Requirements

UPSTAGE only requires Python 3.11+ and Simpy 4+.

## Installation

**Pending:**

```console
pip install upstage
```

### Installation from source

Alternatively, you can download UPSTAGE and install it manually. Clone, or download the archive and extract it. From the extraction location (and within a suitable Python environment):

```console
python -m pip install .
```

(or just `pip install .`)

### Installation for tests

To run the tests: clone locally, install into a fresh environment, and run using:

```console
pip install -e .[test]
pytest
```

## Documentation

See the [documentation](https://JamesArruda.github.io/upstage) for tutorials and additional details.

## How do I report an issue?

Using the issue feature, please explain in as much detail as possible:

1. The Python version and environment
2. How UPSTAGE was installed
3. A minimum working example of the bug, along with any output/errors.

## How do I contribute?

To set up a suitable development environment, see [CONTRIBUTING](CONTRIBUTING.md).

For style, see [STYLE_GUIDE](STYLE_GUIDE.md).

[simpy]: https://gitlab.com/team-simpy/simpy/
