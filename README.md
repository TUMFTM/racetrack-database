# Introduction
This repository contains center lines (x- and y-coordinates), track widths and race lines for 25 race tracks (F1 and
DTM) all over the world. We are open for comments, suggestions and extensions!

Contact person: [Alexander Heilmeier](mailto:alexander.heilmeier@tum.de).

# Data Source and Processing
The original center lines were fetched as GPS points from the OpenStreetMap project (https://www.openstreetmap.org).
The track widths were extracted from satellite images using an image processing algorithm. The race lines were
calculated using our minimum curvature optimization algorithm, which is also available as open source software on GitHub
(https://github.com/TUMFTM/global_racetrajectory_optimization).

# Content and Data Format
- centerlines: [x_m, y_m] (smoothed, therefore not lying perfectly in the middle anymore)
- tracks (centerline (smoothed) + track widths): [x_m, y_m, w_tr_right_m, w_tr_left_m]
- racelines: [x_m, y_m]
- The racelines folder contains a plot of the optimized race line and a plot of the according curvature profile for
every track.

The quality of the source data varies greatly depending on the location. Accordingly, the quality of the results varies
as well. Please bear this in mind and check whether the accuracy is sufficient for the desired application.

# Acknowledgement
The image processing algorithm to extract the track widths was developed by Andressa de Paula Suiti during her semester
thesis at the Chair of Automotive Technology of the Technical University of Munich.
