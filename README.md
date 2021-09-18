# Introduction
This repository contains center lines (x- and y-coordinates), track widths and race lines for over 20 race tracks
(mainly F1 and DTM) all over the world. We are open for comments, suggestions and extensions!

Contact person: [Alexander Heilmeier](mailto:alexander.heilmeier@tum.de).

# Included race tracks
* Austin, USA (F1)
* Brands Hatch, UK (DTM)
* Budapest, Hungary (F1)
* Catalunya, Spain (F1)
* Hockenheim, Germany (F1, DTM)
* IMS Indianapolis Motor Speedway, USA (IndyCar)
* Melbourne, Australia (F1)
* Mexico City, Mexico (F1)
* Montreal, Canada (F1)
* Monza, Italy (F1)
* Moscow Raceway, Russia (DTM)
* Norisring, Germany (DTM)
* Nuerburgring, Germany (DTM)
* Oschersleben, Germany (DTM)
* Sakhir, Bahrain (F1)
* Sao Paulo, Brazil (F1)
* Sepang, Malaysia (F1)
* Shanghai, China (F1)
* Silverstone, UK (F1)
* Sochi, Russia (F1)
* Spa, Belgium (F1)
* Spielberg, Austria (F1)
* Suzuka, Japan (F1)
* Yas Marina, Abu Dhabi (F1)
* Zandvoort, Netherlands (DTM)

# Data Source and Processing
The original center lines were fetched as GPS points from the OpenStreetMap project (https://www.openstreetmap.org).
We applied a smoothing algorithm to the center lines. The track widths were extracted from satellite images using an
image processing algorithm. The race lines were calculated using our minimum curvature optimization algorithm, which is
also available as open source software on GitHub (https://github.com/TUMFTM/global_racetrajectory_optimization).

# Content and Data Format
- tracks: [x_m, y_m, w_tr_right_m, w_tr_left_m] These files contain the center line (x, y) and the track widths to the
right (w_tr_right) and left (w_tr_left). The center lines were smoothed. Therefore, they do not lie perfectly in the
middle of the track anymore.
- racelines: [x_m, y_m] The provided race lines were calculated minimizing the summed curvature. They lie within the
track boundaries. The racelines folder also contains a plot of the optimized race line and a plot of the according
curvature profile for every track.

The quality of the source data (GPS points and satellite images) varies greatly depending on the location. Accordingly,
the quality of the results varies as well. Please bear this in mind and check whether the accuracy is sufficient for the
desired application.

# Working with the supplied format
If you want to work with the data in this repository we suggest to have look into our helper functions repository on
GitHub: https://github.com/TUMFTM/trajectory_planning_helpers. For example, it contains functions to calculate splines
and normal vectors such that the track data can be used in further algorithms or for plotting.

# Acknowledgement
The image processing algorithm to extract the track widths was developed by Andressa de Paula Suiti during her semester
thesis at the Chair of Automotive Technology of the Technical University of Munich.

# Related open-source repositories
* Lap time simulation: https://github.com/TUMFTM/laptime-simulation
* Lap-discrete race simulation: https://github.com/TUMFTM/race-simulation
* Time-discrete race simulator: https://github.com/heilmeiera/time-discrete-race-simulator
* Formula 1 timing database: https://github.com/TUMFTM/f1-timing-database
