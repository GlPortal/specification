# Triggers

Rotation element is optional in every trigger element

```xml
<trigger type="<trigger_type>">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```
## Death
Player will die. 

```xml
<trigger type="death">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

## Win

    Deprecated in triggers 2.0 in favor of the screen trigger

Player will win current map and new (next) map will be loaded.

```xml
<trigger type="win">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

## Radiation
Decrease player health over time.

```xml
<trigger type="radiation" intensity="1">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

## Audio
Play a audio track, loop attribute of triger element is optional, by default it is false
* loop attribute (boolean) of element trigger is optional, by default it is false
* file attribute is the file path relative to the packages data path where /audio is implied
```xml
<trigger type="audio" loop="true" file="track1">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

## Map
Load new map
* file attribute is the file path relative to the packages data path where /maps is implied
```xml
<trigger type="map" file="map name">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

## Checkpoint
Respawns the player at position specified by spawn on death. Rotation subelement of trigger (optional) determines rotation of trigger box, rotation subelement of element <a href="https://github.com/senbar/specification/blob/RadixEngine/formats/map.md#spawn-position">spawn</a> determines rotation of spawn (optional)

```xml
<trigger type="checkpoint">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
  <spawn>
    <position x="2.5" y="1" z="5"/>
    <rotation x="0" y="-90" z="0"/>
  </spawn>
</trigger>
```

## Remove
Toggle means that triggering a second time will reverse the action.
When action is set to true the action key has to be pressed in order for the trigger to fire.

```xml
<trigger type="remove" toggle="true" action="true" ref="wall-name">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

## Teleport
* This trigger is still a draft
```
<trigger type="teleport" name="teleport1" destination="teleport2">
  <position x="5.25" y="-3" z="5"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

## Scripts
* This trigger is still a draft
```
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
