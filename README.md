# A5-Final-Project-Reflection-Report

## Workflow experiences
Our code works and it provides the output that was intented from the beginning. However, many simplifications regarding the calculations have been made along the way. We had to start simple and then add more details later. Our code hasn't been tested to other ifc files, but it will probably need some adjustment, since the code is very file specific. 

## Area geometry
In our calculation we extracted the area of the walls from the floor area and height of the room. The height is in the program given by floor-to-floor and we subtracted with 0.5 to get the height in floor-to-ceiling. This could be done more accurately and generalizable by subtracting with the slab thickness. The walls are calculated assuming it is a square room, since we don't have room dimensions. Using Sabine's equation this is not a big issue since this equation doesn't differentiate on the room geometry, but in acoustics the geometry has an important impact on the calculations and auralizations (how a room sounds). For future work it would be useful to include scattering and room diffraction in the calculation, this is however something current softwares are still struggling with and is highly advanced.

## Surface materials
In this model the surfaces are uniform for all walls and the materials don't change. In reality it is possible that the walls in a space have different surface materials. This would require specific wall areas as described in the previous section. Windows and doors should also be implemented for further developement. 
Also the material order varied from structure to structure in the ifc file. It wasn't always the first or the last material in the list, that was the surface material. That took some time to adjust our code to this and it also made it very file specific. Therefore, the material order should be generalized for all ifc files, so codes will work more generally. 

## Furniture or not?
Furniture in a room has a large impact on the reverberation time in a room. Just think of the huge difference it makes to the room acoustics in an empty room contra a furnitured room. Therefore, it would of course be nice to implement this to the code. Our idea is that the user should be able to hear both examples i.e. a furnitured room and a non-funitured room. 

## Comparisons to the SBI instructions
It could be added to the code if the chosen room with its corresponding reverberation time matches the SBI-instructions. This would give the code output more value for the user since meeting the SBI instructions should be an aim for the building design. 

## An html file as output would be nice
For future work the code could be even more userfriendly by making the output as an html file with a nice and easy understandable interface. If the SBI-instructions are implemented to the code, this could also be shown by color in the html interface, meaning that if the instructions are met, the reverberation time will be green and if not, then it will turn red.  

## Process improvements for furture students

### For future students working with same or similar use case
It is helpful to get simple coding in space extraction and help /code examples for area, volume and height extraction (perhabs also level) so they don't waste a lot of time on this and can start closer to where our group ended. 
Help to navigate with dir and introduction to python in terms of what are objects, tuples, attributes etc.
The hardest part in our code is the material extraction for each space (more specifically defining what is the surface material, since it is not always the first or last material layer). We did this part by basically going through the excel file and using dir in python, where an introduction could be useful for speeding up the workflow.

### Creating samples based on reverberation times
In this project a matlab script is used for creating impulse responses (IRs) based on the reverberation time. The IRs are, once again, depended on room geometry, but in this case they are simply made based on a decay equivalent to the reverberation times possible (from 0.1 - 1 s for this file). 
Matlab is used due to an advanced ITA-toolbox which is good for handling audio files, and is known to our group. It would be interesting to seek opportunities to make the acoustic signal processing directly in python.
If the group have no knowledge in IRs and signal convolution it would be helpful with a short introduction to the matlab script as a tool, not a implemented code. That is, if they want to work with auralizations.

### General for all future students 
The productivity in the beginning is quite low, we are introduced to the program and blender as well as the excel file to understand the IFC file.
The actual use of python and producing the code in python happened in our case after help from the TAs after approximately 1,5 months and it wasn't until November we started getting comfortable in using the excel sheet to develop the code, as well asa asking more targeted questions to the TAs for more efficient help.
A suggestion is to have a couple of code examples in the beginning of the course. This could be examples in navigation in loops (specific/useful for this course), commands (cmd), dir, property sets, spaces, material extraction etc. An classroom task could be to add instructions (comments) to what a code example does and then in plenum go through the correct answers. This is a good way of learning the code commands and language.
