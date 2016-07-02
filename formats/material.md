# Material Definition Format Specification
## File
A material definition starts with the xml declaration and the map tag. 
```xml
<?xml version="1.0" ?>
<material>
[...]
</material>
```

## Example
```xml
<material name="boxes/dev00" fancyname="Dev box!">
	<diffuse path="dev00.png"/>
	<normal path="dev00n.png"/>
	<scale u="1" v="1"/>
	<kind>metal</kind>
</material>
```
