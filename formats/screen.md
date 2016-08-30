# Screen format
## Elements
Element text has following structure:
```xml
<text size=integer top=integer(optional) align=string(optional)
 z=integer(optional)> string </text>
```
Element image has following structure:
```xml
<image right=string bottom=string> string </image>
```
Element button has following structure:
```xml
<button trigger=string> string </button>
```
Element item has following structure:
```xml
<item> element button </item>
```
Element list has following structure:
```xml
<list> element item </list>
```
## More complex elements
Element page has following structure:
```xml
<page timeout=integer(optional) key=string(optional)>
  may contain following elements: container, text, image
</page>
```
Element container has following structure:
```xml
<container width=string(optional) height=string(optional) top=string(optional) left=string(optional)>
  may contain following elements: page, text, image, list
</page>
```
##Screen element
Element screen has following structure:
```xml
<screen name=string(optional)>
  may contain following elements: text, image, container, page
</screen>
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
