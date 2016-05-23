# Map Format Specification {#map-format-spec}
## File
A map starts with the xml declaration and the map tag. 
```xml
<?xml version="1.0" ?>
<map>
[...]
</map>
```

## Authors

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

## End Position
End position is deprecated and will be replaced by the end_map trigger in the future.
```xml
<end>
    <position x="25" y="0" z="5"/>
    <rotation x="0" y="90" z="0"/>
</end>
```

## Materials

```xml
<materials>
  <mat mid="1" name="concrete/wall00"/>
  <mat mid="2" name="metal/tiles00x3"/>
</materials>
```

## Models
The map format needs to support to add models.

Proposed tag

```xml
<model mesh="foo.obj" mid="<material_id>">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</model>
```

In the editor show the mesh as it would look in the game.


## Walls

```xml
<wall mid="<material_id>">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</wall>
```

## Light
Define a point light.
### Required attributes:
 - Position - float x, float y, float z
 - Color - float r, float g, float b
 - Distance - float distance
 - Energy - float energy

### Optional attributes:
 - specular - int specular
```xml
<light x="10" y="6" z="5" r="0.9" g="0.9" b="1" distance="20" energy="5" specular="1"/>
<light x="10" y="6" z="5" r="0.9" g="0.9" b="1" distance="20" energy="5" specular="0"/>
<light x="10" y="6" z="5" r="0.9" g="0.9" b="1" distance="20" energy="5"/>
```

## Triggers
```xml
<trigger type="<trigger_type>">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```
### Death
Player will die

### Win
Player will win current map and new map will be loaded

### Radiation
Decrease player health over time.

### Music
Play a music track.  
```xml
<trigger type="music" loop="true" track="track1">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

### Checkpoint
Respawns the player at position specified by spawn on death.

```xml
<trigger type="checkpoint">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
  <spawn x="0" y="0" z="0"/>
</trigger>
```

### Remove
Toggle means that triggering a second time will reverse the action.
When action is set to required the action key has to be pressed in order for the trigger to fire.

```xml
<trigger type="remove" toggle="true" action="required" ref="wall-name">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

### Scripts

```xml
<script>
  function jump(){
    smooth(player.position.y, 3);
  }
</script>
<trigger type="script" callback="jump()">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```
