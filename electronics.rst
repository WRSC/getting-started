Electronics
===========

You'll need a computer, at least two motors, and a handful of sensors.

Computer
--------

Several teams have successfully used a Raspberry Pi as the brains of their
boats. Microcontrollers such as Arduinos are another option: these make it
easier to work with low-level hardware interfaces like PWM control for servos,
but are less flexible for writing high-level control code.
What sensors you choose may also affect the kind of computer you need.

Motors
------

You'll need to move the sails and the rudder to control the boat.
For the micro-sailboat class, a typical hobby-grade servomotor can move the
rudder, but more force is needed for the sails: sail winch servos are available
for remote-controlled sailing.

If you have multiple sails or multiple rudders, you may want extra motors
to control them independently.

Positioning
-----------

GPS - and its cousins generically known as GNSS - are amazing.
With an inexpensive receiver you can tap into a network of satellites
and get an accurate position.

Making sense of the data can take a bit of effort.
You'll probably get a latitude and longitude in a coordinate system called
WGS-84 - at this level of accuracy, getting the right reference system
matters.
For the small distances involved in WRSC, it's convenient to convert positions
to coordinates in metres and assume a flat plane. This is what the UTM
coordinate system does; you'll need to find which of the 60 UTM zones you're
sailing in to get the calculations right.

Wind sensors
------------

You need to measure the wind direction, and you may also want to know the speed.
The simple approach is a physical wind vane and some way of measuring its
position, such as a rotary encoder or a magnetic field sensor.
Ultrasonic wind sensors measure the direction and speed of the wind with
no moving parts, by comparing how sound waves move in different directions.

Wind sensors are typically placed at the top of the mast or near the front of
the boat, to minimise interference from the sails.

Orientation sensors
-------------------

Sensing which way the boat is pointing is surprisingly tricky.
The obvious approach is to measure the earth's magnetic field,
like a handheld compass. But the earth's field is weak, and your electronics
can interfere with it. If your boat can heel over in the wind, you also need
to account for the third dimension.

Combining gyroscopes and magnetic field readings can give more accurate
estimates of direction. Inexpensive 'IMUs' combining gyroscopes, magnetic field
sensors and accelerometers are readily available. But combining multiple sources
of data can also make it harder to understand when things go wrong.

Other ideas, of varying practicality:

- Use only a gyroscope, along with knowledge of which way the boat was pointing
  when it was started. Relies on having a gyroscope with low enough drift.
- Infer the boat's orientation based on its movements tracked by GPS.
- Have two GPS antennae, one at each end of the boat, and find the difference
  between their positions.
- Use the position of the sun, along with the local time.
  It may be possible to use polarised light to estimate the sun's position
  through clouds; there are suggestions that 'sunstones' were used to navigate
  this way in mediaeval times.
- Use computer vision to recognise landmarks, in combination with position
  from GPS.
