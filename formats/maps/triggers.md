# Triggers
```xml
<trigger type="<trigger_type>">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```
## Death
Player will die

## Win
Player will win current map and new map will be loaded

## Radiation
Decrease player health over time.

## Map
Load new map

## Music
Play a music track.  
```xml
<trigger type="music" loop="true" track="track1">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

## Checkpoint
Respawns the player at position specified by spawn on death.

```xml
<trigger type="checkpoint">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
  <spawn x="0" y="0" z="0"/>
</trigger>
```

## Remove
Toggle means that triggering a second time will reverse the action.
When action is set to required the action key has to be pressed in order for the trigger to fire.

```xml
<trigger type="remove" toggle="true" action="required" ref="wall-name">
  <position x="5.25" y="-3" z="5"/>
  <rotation x="0" y="0" z="0"/>
  <scale x="0.5" y="4.0" z="4.0"/>
</trigger>
```

## Scripts

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
