# Screen format

## File
A screen starts with the xml declaration and the screen tag. 
```xml
<?xml version="1.0" ?>
<screen>
[...]
</screen>
```

## Elements
### Text
```xml
<text size=integer top=integer(optional) align=string(optional) z=integer(optional)> string </text>
```
### Image
```xml
<image right=string bottom=string> string </image>
```
### Button
```xml
<button trigger=string> string </button>
```
### Item
```xml
<item> string </item>
```
### List
```xml
<list> string </list>
```

### Trigger
On keypress switch to another screen or game state.
Target is the target screens name and with the gamestate: prefix a game state.

```xml
<trigger key="esc" target="gamestate:running"/>
```

## Container
### Page
```xml
<page timeout=integer(optional) key=string(optional)>
  may contain following elements: container, text, image
</page>
```
### Container
```xml
<container width=string(optional) height=string(optional) top=string(optional) left=string(optional)>
  may contain following elements: page, text, image, list
</container>
```

### Canvas
Area to render graphics on

```xml
<canvas></canvas>
```

## Examples
```xml

<screen>
  <page timeout="10">
    <container width="100%" height="100px" top="1px" left="0px">
      <text size="1" align="center">Some Text</text>
    </container>
    <image right="0px" bottom="0px">test/hud.png</image>
  </page>
  <page key="enter">
    <container width="100%" height="100px" top="1px" left="0px">
      <text size="1" align="center">Some Text</text>
    </container>
    <image right="0px" bottom="0px">test/hud.png</image>
  </page>
</screen>
```

```xml

<screen name="menu">
  <container>
    <list>
      <item><button trigger="start-game">Start</button></item>
      <item><button trigger="end-game">End</button></item>
    </list>
  </container>
</screen>
```

```xml

<screen>
  <trigger key="esc" target="pause"/>
  <container>
    Press escape to pause
  </container>
</screen>
```

```xml

<screen>
  <trigger key="esc" target="gamestate:running"/>
  <container>
    Game paused hit escape again to go back to the game.
  </container>
</screen>
```
