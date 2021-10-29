# Soul-Reaver-.dae-merge-into-.blend
A short script I wrote to merge Spectral and Material realm .dae files, extracted using Soul Spiral, into a .blend file with the keyframe animation to "shift" between the realms. This is achieved using Shape Keys in the 3D software Blender.

After extracting your desired spectral realm and material realm files using Soul Spiral you will notice that the two realms are separate .dae files and animating between the two is more costly in terms of time and technical skills. This script merges the two by using shape keys, modification to the original mesh that allows you to animate between the two states. The reason this works out is because the two .dae's have the same mesh count between like objects, this being a requirement of shape keys to work.

The first part of the code imports the .dae files

The for loop is where the batch processing occurs. The objects within the Spectral Realm.dae are used as the iterator, and we select the Materal realm dae objects accordingly

Using material nodes we merge the materials and textures, The Mix RGB and Vertex Color Nodes are key here, and we then insert keyframes to animate material.
Following that we merge the two objects using blender's join_shapes function to merge as shape keys. finally we insert keyframes to animate the shape.

Afterwards, we delete the mesh without shape keys.


Note: that while this object is animated with the correct textures and shape keys in blender, exporting the object as FBX does not export the material animation in the same way. 

Future Work:

Integrating Soul Spiral and ModelEx and this Blender script or Unreal Engine into one seemlessly workflow instead of having to open multiple applications to perform this task. 
