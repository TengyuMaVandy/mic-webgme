# mic-webgme
## Installation
First, install the mic-webgme following:
- [NodeJS](https://nodejs.org/en/) (v4.x.x recommended)
- [MongoDB](https://www.mongodb.com/)

Second, start mongodb locally by running the `mongod` executable in your mongodb installation (you may need to create a `data` directory or set `--dbpath`).

Then, run `webgme start` from the project root to start . Finally, navigate to `http://localhost:8888` to start using mic-webgme!

## Petri Nets
A Petri Net is one of several mathematical modeling languages for the description of distributed systems. A Petri Net is a directed bipartite graph, in which the nodes represent transitions and places. The directed arcs describe which places are pre- and/or postconditions for which transitions.

In the mic-webgme server, you can genreate a new PetriNets project with my PetriNets seed (src/seeds/PatriNets). After you generate the project succesfully, you can see the following image of the root composition.  
![Alt text](https://github.com/TengyuMaVandy/mic-webgme/blob/master/readme-image/Root%20composition.PNG?raw=true "Root composition")
### MetalModel
