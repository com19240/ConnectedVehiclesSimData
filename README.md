# ConnectedVehiclesSimData
This repository shares the simulated false information, DoS, and impersonation attack data on connected vehicles from SUMO on the South Carolina connected vehicle testbed (SC-CVT) Perimeter Rd, Clemson, SC. Details are published as preprint and can be found in "Comert, Gurcan, Mizanur Rahman, Mhafuzul Islam, and Mashrur Chowdhury. "Change Point Models for Real-time Cyber Attack Detection in Connected Vehicle Environment." https://arxiv.org/abs/2003.04185, arXiv preprint arXiv:2003.04185 (2020)." 

Using the generated trace file from the SUMO simulation, three different cyber-attack scenarios are generated (description to be updated with data shared from toher scenarios): 

Denial of service (DoS) attack: For generating DOS attack data in our experiment, vehicle with ID 6 is flooding at 1000 Hz while other vehicles are sharing data at 10Hz to mimic the real-world CV environment where each CV is broadcasted BSMs every one-tenth of a second. The total simulation time is 200 seconds (s) for generating DOS attack data.

False information attack: For fake (or false) information attack, false GPS location information (i.e., longitude and latitude) of vehicle ID 2 are generated simply using random variable generation library from python. We have crafted the attack such way that it creates random location within a given geo-fenced region so that it seems normal geolocation to human. This false information is also broadcasted by the attacker vehicle at 10 Hz or 10 packets/s. The total simulation time is 200 s for false information attack.

Impersonation attack To emulate the data for impersonation attack, a false ID for vehicle number 3 is used as vehicle ID 2. Two different GPS location and speed information for the vehicle ID 2 are simultaneously generated. In the trace file, the vehicle id of vehicle 3 was replaced by the vehicle id 2 to craft an impersonation attack, where we assume that both of the vehicle 2 and vehicle 3 are in the same region. Thus two different GPS location and speed information are being broadcasted containing the same vehicle id simultaneously. Both of the vehicles is broadcasting the data at 10 packets/s, and simulation was run for 200 s.

