# Starlink Beam Planning
# Python Notebook
To provide internet to a user, a satellite needs to form a "beam" towards that user, and the user needs to form a beam towards the satellite. If they are both
pointing at each other, they can form a high-bandwidth wireless link.
The Starlink satellites are designed to be very flexible. For this problem, each satellite is capable of making up to 32 independent beams simultaneously.
Therefore, one satellite can serve up to 32 users. Each beam is assigned one of 4 "colors" (which correspond to the particular frequency used to serve that
user), which is necessary to allow a single satellite to serve users that are close to one another without causing interference.
There are a few constraints which limit how those beams can be used:
On each Starlink satellite, no two beams of the same color may be pointed within 10 degrees of each other, or they will interfere with each other.
Other non-Starlink satellites (interferers) might be trying to provide service in the same location we are. To protect them, beams from our satellites
must not be within 20 degrees of a beam from any non-Starlink satellite (from the user's perspective).
For simplicity, we assume that every non-Starlink satellite is providing blanket service to all users all the time.
From the user's perspective, the beam serving them must be within 45 degrees of vertical. Assume a spherical earth, so all user normals pass
through the center of the earth (0,0,0).
Given a list of users, Starlink satellites, and non-Starlink satellites, the code figures out how to place the beams to serve the most users, respecting the constraints
above. The code applies all constraints, however, it may not be possible to cover all users in some of the provided input files.
The inputs to this program will come from a text file. The program will receive the name of that text file on the command-line as a single argument.
