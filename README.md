# mic-webgme
## Installation
First, install the mic-webgme following:
- [NodeJS](https://nodejs.org/en/) (v4.x.x recommended)
- [MongoDB](https://www.mongodb.com/)

Second, start mongodb locally by running the `mongod` executable in your mongodb installation (you may need to create a `data` directory or set `--dbpath`).

Then, run `webgme start` from the project root to start . Finally, navigate to `http://localhost:8888` to start using mic-webgme!

## Petri Nets
A Petri Net is one of several mathematical modeling languages for the description of distributed systems. A Petri Net is a directed bipartite graph, in which the nodes represent transitions and places. The directed arcs describe which places are pre- and/or postconditions for which transitions. Graphically, places in a Petri net may contain a discrete number of marks called tokens. Any distribution of tokens over the places will represent a configuration of the net called a marking. 

In the mic-webgme server, you can genreate a new PetriNets project with my PetriNets seed (src/seeds/PatriNets). After you generate the project succesfully, you can see the following image of the root composition.  
![Alt text](https://github.com/TengyuMaVandy/mic-webgme/blob/master/readme-image/Root%20composition.PNG?raw=true "Root composition")
## MetaModel
### MetaModel Composition
In the PetriNetMetaModel composition, there are 7 instances.
  1. PetriNetDeiagramFolder is the folder for exapmles of PetriNet. 
  2. PetrNetDiagram is the example itself. In my case, it will be Vending Machine example.
  3. Place represent for something like conditions, represented by circles.
    * The non-default icon for Place is a circle in MetaModel
  4. Transition represent for something like events that may occur, represented by bars.
    * The non-default icon for Transition is a Rectangle in MetaModel
  5. Arc is the directed arcs between Place and Transition.
    * The non-default icon for Arc is an arrow in MetaModel.
  6. PtoT inherits form Arc, which specify the direction as from Place to Transition.
  7. TtoP inherits from Arc, which specify the direction as from Transition to Place.
![Alt text](https://github.com/TengyuMaVandy/mic-webgme/blob/master/readme-image/PetriNetMetalModel%20composition.PNG?raw=true "PetriNetMetalModel composition")

### MetaModel META META
  1. The FCO is the basic Meta for any other Metas. PetriNetDiagramFolder, since it is a folder, it can contain any type object of itself.PetriNetDiagram is an example inside of the folder, so it can contain any type of object of the folder.
  2. PetriNetMetaModel is the top-level of the whole MetaModel, which can encapsulate all instances of PetriNet.
  3. The core parts of the META META is the Place, Transition and Arc, and Arc also has 2 children, PtoT and TtoP. Place is the META for Place in the PetriNet. Similarly, Transition is the META for Transition in the PetriNet. PtoT, with the direction from place to Transition, describe that a Place can move to its next Transition, so the source of the blue arrow is Place and the destination of the blue arrow is Transition. TtoP, with direction from Transition to Place, describe that a Transition can move to its next Place, so the source of the blue arrow is Transition and the destination of the blue arrow is Place.
  4. Place has three attributes:
    * Capacity: The most token it can take with default value of 1.
    * InitialMarking: The initial number of token, which should be smaller than the capacity.
    * TokenColor: The color for the token with default valut of red.
![Alt text](https://github.com/TengyuMaVandy/mic-webgme/blob/master/readme-image/META%20META.PNG?raw=true "META META")

### MetaModel META Connections
No more new information for the META connections. This is the META to specifically represent for the connection of the PetriNet, which comprises P, T, Arc, PtoT and TtoP.
![Alt text](https://github.com/TengyuMaVandy/mic-webgme/blob/master/readme-image/META%20Connections.PNG?raw=true "META Connections")

## Example
Inside of the PetriNetExample folder is the Example for PetriNet, Vending Machine.

![Alt text](https://github.com/TengyuMaVandy/mic-webgme/blob/master/readme-image/PatriNetExample%20composition.PNG?raw=true "PatriNetExample composition")

### Vending Machine
In the real world, the Vending Machine takes lots of convenient for people. How to depoist money and give back the merchandise to the customer is the main function of the Vending Machine, which can usually be easy to design by a State Machine or a PetriNet.

I set up some rules for the using of Vending Machine, which is also happened in the real world.
  1. The machine dispenses two kinds of snack bars for 20 cents and 15 cents.
  2. Only two types of coins can be used, 10 cent coins and 5 cent coins.
  3. The machine does not return any change, which menas customer should deposit the exact same number of one kind of snack bars into the machine.

In the Vending Machine composition, we could regard the 0c Place as the start state, and then we can follow the arrows which connected to the 0c Place moving to the next possbile Transition, which is Deposit 5c or Deposit 10c. We can do the same process along the whole diagram, and finally the customer get his snack bar as well as the Vending Machine comes back to the initial Place.
![Alt text](https://github.com/TengyuMaVandy/mic-webgme/blob/master/readme-image/VendingMachine%20Composition.PNG?raw=true "VendingMachine Composition")

### Scenario of Vending Machine
Suppose there is a customer who wants to buy a 20c snack bar. He comes to my Vending Machine and deposit 5c, 10c and 5c into the machine, and finally he is so happy with the delicious snack bar. How could we describe such a scenario use my PetriNet model?

The red filled circle is the token and the red arrow is for the process of the scenario we mentioned above. Follow the arrows to move the token and take those specific Transitions with red bar. When the process comes back to the 0c place, the complete scenario will be done.
![Alt text](https://github.com/TengyuMaVandy/mic-webgme/blob/master/readme-image/VendingMachine%20Composition%20Scenario.png?raw=true "VendingMachine Scenario")

## Plugin
The MiniProject2 plugin implements two main functions.
  1. Creates a hierarchical structure of my MiniProject1 in a json file.
  2. Creates an array of all the meta-nodes.

Please find the json files of the plugin results in the 'project-data.zip'.

Thank you!
