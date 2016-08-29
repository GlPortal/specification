# Material Definition Format Specification
## File
A material definition starts with the xml declaration and the map tag. 
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
It also must contain attribute
```xml
<material name=string (..)
```
and may contain attribute:
```xml
<material fancyname=string (..)
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
