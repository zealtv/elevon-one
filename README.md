# ELEVON-ONE 🛩

Elevon One is a spatial metacomposition writen in Pure Data, intended to musically express the dynamics of gliding flight.  The patch receives motion data in the format specified below, and leverages the Pure Data libraries [Bop 🐦](https://github.com/zealtv/bop), and [Elevon](https://github.com/zealtv/elevon).

Elevon is responsible for structuring the piece against n-dimensions of incoming data, whilst Bop provides musical content by way of synthesis, sequencing, sample playback, and audio processing.

The patch expects data in the following format to be sent as OSC to port 4813.

```
/telemetry float[24] A condensed form of all data points used for logging. Elements are ordered as described below from top to bottom.

/time float Time in seconds since start.
/sync int(0-1) A value of 0 or 1 acting as a flag for synchronising video footage.
/pos float[3] The position in metres of the sensor relative to its location at start, in east, up, and north directions.
/latlonalt float[3] The latitude, longitude and altitude of the sensor. Altitude is described as metres above mean sea level (ASL).
/rot float[4] A quaternion describing the orientation of the sensor. Relative to the sensor facing north, level with the horizon.
/vel float[3] The velocity of the sensor unit in metres/second, in right, up, and forwards directions.
/acc float[3] The local linear acceleration in metres/second2, in right, up, and forwards directions.
/angvel float[3] The angular velocity in revolutions/second, in pitch, yaw, and roll.
/angacc float[3] The local angular acceleration in revolutions/second2, in pitch, yaw, and roll.
```

Alternatively, a switch is provided to instead receive a subset of data from the iOS application [GyrOSC](https://www.bitshapesoftware.com/instruments/gyrosc/) on port 9999.  When using GyrOSC position and velocity data are not available.

Samples from Cay Borthwick and Ian McCurdy.
