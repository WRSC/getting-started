Control system
==============

Your control system is the code that will monitor your sensors,
keep track of what the boat needs to do, and move the motors.

It's useful to have some separation between the parts of code that talk to
hardware, and the sailing and navigation logic, so you can test the logic
without all the hardware connected.

There are some frameworks that might help you structure your code.
Using a framework is more work when you're getting started, but can make
it easier for multiple people to understand and work on the same code.

* `boatd <https://boatd.readthedocs.io/en/latest/>`_ is specifically designed
  for robotic sailing boats. It uses a Python-based 'driver' to talk to the
  hardware, while a separate process controls the behaviour using an HTTP API.
* `ROS <http://www.ros.org/>`_ is a more general robotics framework. Your code
  is divided into nodes, which each perform one function, such as reading a
  particular sensor. Nodes can be written in different languages, and
  communicate by sending messages using a ROS-specific protocol.

Open source examples
--------------------

Several teams have published their control systems as open source software,
so you can examine them and even reuse them (making sure to follow the
appropriate licenses).

`Abersailbot <https://github.com/abersailbot>`_
  Python code built around their boatd framework.
`Åland Sailing Robots <https://github.com/AlandSailingRobots/sailingrobot>`_
  C++ code (TODO: brief summary of code structure)
`Southampton Sailing Robot Team <https://github.com/Maritime-Robotics-Student-Society/sailing-robot>`_
  Python code using the ROS 1.x framework.

If your team has an open source codebase, please add it to the list by
`opening a pull request <https://github.com/WRSC/getting-started/pulls>`_,
or send us the details and we can add it.
