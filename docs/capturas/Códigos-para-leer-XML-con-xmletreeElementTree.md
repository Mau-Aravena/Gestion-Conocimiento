# Códigos para leer XML con xml.etree.ElementTree
---
## Fuente 
[Parse XML Files with Python - Basics in 10 Minutes](/docs/bibliografia/Parse_XML_Files_with_Python_-_Basics_in_10_Minutes)

## Archivo XML
``` xml
<data date="2022-10-10">
	<stock>
		<name>Microsoft</name>
		<ticker>MSFT</ticker>
		<price>234.24</price>
		<currency>USD</currency>
	</stock>
	<stock>
		<name>Apple</name>
		<ticker>APPL</ticker>
		<price>140.09</price>
		<currency>USD</currency>
	</stock>
</data>
```
## Código en Python 
``` python
import xml.etree.ElementTree as ET

# Parse XML into Element Tree
tree = Et.parse('xml_file.xml')
root = tree.getroot()

# Root
# print(root.tag)
# print(len(root))

# Access Root Child
print(root[0].tag)
# print(len(root[0]))

# Loop over Root Children
# for child in root:
#     print(child[0].tag)
#     print(child[0].text)

# Root Grandchildren
# print(root[0][0].tag) # name
# print(root[0][0].text)
# print(root[0][1].tag) # ticker
# print(root[0][1].text)
# print(root[1][2].tag) # price
# print(root[1][2].text)

# Get an Attribute
print(root.attrib)

# Loop over 'Ticker' Tag
# for ticker in root.iter('ticker'):
#     print(ticker.text)

# Find Children with 'price' Tag
# print(len(root[0].findall('price')))
# print(root[0].findall('price')[0].text)

# Change Price & Remove Currency
# root[0][2].text = "233"
# root[1].remove(root[1][3])
# tree.write('xml_file.xml')
```
