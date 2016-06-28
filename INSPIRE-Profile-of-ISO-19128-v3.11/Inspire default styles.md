# Inspire default styles

**Purpose**: To make combining of layers from different INSPIRE data providers possible, the layers portraying
harmonized particular INSPIRE datasets must be made available with the same harmonized INSPIRE rendering styles
as specified in the Data Specification documents for each theme.

**Prerequisites**

* [Schema validation](Schema validation.md)
* [Harmonised layer name](Harmonised layer name.md)

**Test method**

For each [Layer](#Layer) qualified as presenting an INSPIRE harmonized dataset during the previously run test [Harmonised layer name](Harmonised layer name.md):
* For each [Style element](#style) within the Layer:
  * If no required default style for this layer is given in the INSPIRE Data Specification in which this harmonized layer name is introduced, pass the test for this layer. Otherwise:
    * Check if the [Style Name](#style-name) equals the name of the default style name for this layer as defined by the Portrayal section of the INSPIRE Data Specification of the INSPIRE theme.
* If none of the [Style Name](#style-name) elements match, repeat the test recursively for any [Parent Layers](#parent_layer) until a match is found or there is no parent layer (1). If no match was found in the end, fail the test for the original layer.
* All layers not qualified as presenting INSPIRE harmonized datasets must be ignored in running this test.

**Reference(s)**:

* [TG VS](README.md#ref_TG_VS), chapter 4.2.3.3.4.8 Styles

**Test type**: Automated

**Notes**

1. Note that the parent layers do not have to be qualified as INSPIRE harmonized layers to be included in the recursive style name matching.

## Contextual XPath references

The namespace prefixes used as described in [README.md](README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
Layer <a name="layer"></a> | /wms:WMS_Capabilities/wms:Capability//wms:Layer
Style element <a name="style"></a> | ./wms:Style
Style Name <a name="style-name"></a> | ./wms:Style/wms:Name
Parent Layer <a name="parent_layer"></a> | ../../wms:Layer