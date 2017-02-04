*TensorForce - modular deep reinforcement learning on tensorflow by reinforce.io*
=================================================================================

Introduction
------------

TensorForce is an open source reinforcement learning library focused on
providing clear APIs, readability and modularisation to deploy
reinforcement learning solutions both in research and practice.
TensorForce integrates seamlessly with Google TensorFlow.

The main difference to existing libraries (such as rllab) is a strict
separation of environments, agents and update logic that facilitates
usage in non-simulation environments (see our architecture overview page
for details). Further, research code often relies on fixed network
architectures that have been used to tackle particular benchmarks.
TensorForce is built with the idea that (almost) everything should be
optionally configurable and in particular uses value function template
configurations to be able to quickly experiment with new models. The
goal of TensorForce is to provide a practitioner's reinforcement
learning framework that smoothly integrates into modern software service
architectures.

TensorForce is actively being maintained and developed both to
continuously improve the existing code as well as to reflect new
developments as they arise (see roadmap for more). The aim is not to
include every new trick as quickly as possible but to adopt methods as
they prove themselves stable, e.g. as of early 2017 A3C and TRPO
variants are the basis of a lot of research. We also offer TensorForce
support through our Gitter channel.

Acknowledgements
----------------

The goal of TensorForce is not to re-implement existing algorithms, but
to provide clear APIs and modularisations, and later provide serving,
integration and deployment components. The credit for original open
source implementations, which we have adopted and modified into our
architecture, fully belongs to the original authors, which have all made
their code available under MIT licenses.

In particular, credit goes to John Schulman, Ilya Sutskever and Wojciech
Zaremba for their various TRPO implementations, Rocky Duan for rllab,
Taehoon Kim for his DQN and NAF implementations, and many others who
have put in effort to make deep reinforcement learning more accessible
through blog posts and tutorials.

Features
--------

TensorForce currently integrates with the OpenAI Gym API, OpenAI
Universe and DeepMind lab. The following algorithms are available: 1.
A3C 2. Trust Region Policy Optimization (TRPO) with generalised
advantage estimation (GAE) 3. Normalised Advantage functions 4.
DQN/Double-DQN 5. Vanilla Policy Gradients (also using with GAE)

Installation
------------

For the most straight-forward install via pip, execute:

::

    git clone https://github.com/tensorforce/tensorforce
    cd tensorforce
    pip install -e .

To update TensorForce, just run ``git pull`` in the tensorforce
directory.

Examples and documentation
--------------------------

For a quick start, you can run one of our example scripts using the
provided configurations, e.g. to run the TRPO agent on CartPole, execute
from the examples folder:

::

    python tensorforce/examples/openai_gym.py CartPole-v0 -a TRPOAgent -c tensorforce/examples/configs/trpo_agent.json -n tensorforce/examples/configs/trpo_network.json

Road map and contributions
--------------------------

TensorForce is still in alpha and hence continuously being updated.
Contributions are always welcome! We will use github issues to track
development. We ask that contributions integrate within the general code
style and architecture. For larger features it might be sensible to join
our Gitter chat or drop us an email to coordinate development. The
larger roadmap looks as follows:

1. Improve policy gradient internal state management and configurable
   policies
2. Execution configuration that abstracts away TensorFlow device
   configurations
3. Generic parallelisation API
4. Hybrid A3C/policy gradient algorithms - not clear yet which
   combination method will work best, but a number of papers showcasing
   different approaches have been submitted to ICLR 2017.
5. RL serving component. TensorFlow serving can serve trained models but
   is not suitable to manage RL lifecycles.

Support and contact
-------------------

tensorforce is maintained by reinforce.io, a new project focused on
providing open source reinforcement learning infrastructure. For any
questions or support, get in touch at contact@reinforce.io

You are also welcome to join our Gitter channel for help with using
TensorForce, bugs or contributions: