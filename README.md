# Modularity_Branching_Vessel
(A function for connecting any number of "branching vessels" together via BondGraphTools)


This function requires a CellML file as an input. The CellML file must contain all the required parameters and initial conditions for the  state variables.

Note that the function is not sensitive to the order of the parameters/state variables indicated in the CellML file but it is sensitive to the names of the foresaid values. The names of the parameters/state variables must always be the same without any changes to be readable by the function. 

The models which the user wants to connect, shall be separated as different "components" in the CellML file.

The inputs of the function would be the “CellML file name”, “arbitrary name for the BG model”, and the “connections”. The connections must be inserted as groups of 4. It means that the function considers each connection by 4 constitutive inputs in the form of (Model_name_1, Port_1, Model_name_2, Port_2). The next 4 inputs will automatically considered as another connection. The Models’ names must be the name of any component which is defined in the CellML file. The name of the ports can be either “Se”, “Sf1”, or “Sf2”. These components were considered as input ports because it is assumed that the user just knows the single branching vessel model and for connecting one model to the other one, he prefers to mention the connection ports by the outer components of each sub-system. When the model name is inserted, the function automatically determines that the next input must be the port corresponding to that model. So there is no need to specify the ports by editing their names such as “Se_1”, “Sf_2”, ... . So for example if the user inserts the phrase (‘model_a’, ‘Sf1’, ‘model_b’, ‘Se’) to the function, it means that he wants to connect the ‘Sf1’ port in ‘model_a’ to ‘Sf2’ port in ‘model_b’. Since ‘Sf1’ & ‘Sf2’ are boundary conditions, the function automatically removes these boundary conditions and connects the related junctions together. This also is true when the connection port is from the ‘Se’ direction (obviously this connection cannot happen in the first model because the model needs a source of potential to operate).

In this file, 4 models are connected together as an instance.
