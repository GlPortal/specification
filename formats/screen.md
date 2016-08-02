# Screen format
## Title
The title of a screen.
## Text
## Class
Used for applying style sheets.
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
    <button trigger="start-game">Start</button>
    <button trigger="end-game">End</button>
  </container>
</screen>
```
