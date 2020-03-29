# COVID-19 SIR simulation in Python
This repository contains the simulation code used to simulate the 'flatten the curve' figure along with some other figures. We used the SIR (susceptible, infectious, recovered) model, one of the typical compartmental models in epidemiology.
**The accompanying article (PDF file) discusses the results of the model and explains the physics behind the model.**

### Simulation method
Instead of using rate equations, we place 100 people in a confined grid and let them move randomly (in straight lines) throughout the grid. They can scatter via the walls or when they collide with other people. In the latter case, they transfer the virus if one of the two persons is ill. The grid looks like the figure below:
![Initialised 10x10 grid with 100 people](https://raw.githubusercontent.com/DaanWielens/covid19-python/master/PersonsFrame.png)

Social distancing is simulated by having a percentage of the people not moving. Without a finite velocity, they can't actively participate in spreading the virus and hence will help in slowing down the rate. However, they can be infected when another person collides with them and can also still transfer the virus upon colliding people when they are ill themselves.

### Main results
When the duration of the illness is finite, the result of social distancing is the 'flatten the curve' figure as shown below. Here, we plot the number of cases versus time. Note that the number of cases is not the total number of people that is infected, but rather the number of people being ill at the same time. This number is much more important for hospitals, having a fixed amount of beds for people to take care of.
![Flatten the curve simulation results](https://raw.githubusercontent.com/DaanWielens/covid19-python/master/covid19_v2_socdist_data5.png)

When people stop social distancing too early, the simulations clearly show that the number of cases increases when the initial percentage of social distancing was high. The main message from the figure below is that we should take care not to stop too early with the social distancing for that matter. 
![Temporary social distancing](https://raw.githubusercontent.com/DaanWielens/covid19-python/master/covid19_v2_socdist35s.png)

To see the effects of (temporary) social distancing on the maximum number of people that could end up in the hospital simultaneously, we plot the maxima of all simulated curves in the figure below. 
![Maxima of simulated curves](https://raw.githubusercontent.com/DaanWielens/covid19-python/master/covid19_v2_tempsocdist.png)
