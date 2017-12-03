# Map Format Specification
Proposal for Version 2 of the map format.

## Map
A map starts with the xml declaration and the map tag. 
```xml
<?xml version="1.0" ?>
<map>
[...]
</map>
```

## Authors

Optional tag that contains the map authors.
```xml
<authors>
  <author email="john.k@example.com">John Kent</author>
  <author>Bruce Obama</author>
</authors>
```

## Position
Denotes a position in 3D. 
Attributes float x, float y, float z.
```xml
<position x="2.5" y="1" z="5"/>
```

## Rotation
Attributes degree int x, int y, int z.
```xml
<rotation x="0" y="-90" z="0"/>
```

## Spawn Position
```xml
<spawn>
    <position x="2.5" y="1" z="5"/>
    <rotation x="0" y="-90" z="0"/>
</spawn>
```

## Materials

```xml
<materials>
  <material id="1" name="concrete/wall00"/>
  <material id="2" name="metal/tiles00x3"/>
</materials>
```

## Models
The map format needs to support to add models.

```xml
<model mesh="foo.obj" material="<material_id>">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</model>
```

In the editor show the mesh as it would look in the game.


## Walls
### Required attributes
position, scale

### Optional attributes
rotation
```xml
<wall material="<material_id>" name="<wall_name>">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</wall>
```

## Light
Define a point light.
### Required attributes
 - Position - float x, float y, float z
 - Color - float r, float g, float b
 - Distance - float distance
 - Energy - float energy

### Optional attributes
 - specular - int specular
```xml
<light distance="20" energy="5" specular="0"/>
  <position x="5.25" y="-3" z="5"/>
  <color r="0.9" g="0.9" b="0.9"/>
</light>
```
