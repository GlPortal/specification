# Map Format Specification {#map-format-spec}
## Triggers
### Remove
Toggle means that triggering a second time will reverse the action.
When action is set to required the action key has to be pressed in order for the trigger to fire.

```xml
<removeTrigger toggle="true" action="required" ref="wall-name">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</removeTrigger>
```

### Scripts

```xml
<script>
  function jump(){
    smooth(player.position.y, 3);
  }
</script>
<scriptTrigger callback="jump()">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</scriptTrigger>
```

## Materials

```xml
<materials>
  <mat mid="1" name="concrete/wall00"/>
  <mat mid="2" name="metal/tiles00x3"/>
</materials>
```

## Objects
The map format needs to support to add objects.

Proposed tag

```xml
<object mesh="foo.obj" mid="<material_id>">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</object>
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
