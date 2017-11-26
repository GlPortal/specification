# Material Definition Format Specification
## File
A material definition starts with the xml declaration and the map tag. The file extension is xml.
```xml
<?xml version="1.0" ?>
<material>
[...]
</material>
```
## Structure
Element material may contain following subelements:
```xml 
<diffuse path=string/>
<normal path=string/>
<height path=string/>
<scale u=integer v=integer/>
<surface portalable=boolean/>
<specular path=string shininess=integer/>
<tiles scale=integer/>
<kind> string </kind>
<tags> string </tags>
```
It also contains following attributes:
```xml
<material name=string(required) fancyname=string(optional)>
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
