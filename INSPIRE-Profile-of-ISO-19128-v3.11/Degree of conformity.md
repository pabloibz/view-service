# Degree of conformity

**Purpose**: The INSPIRE Metadata Regulation INS MD requires that metadata shall include information on the degree of conformity with the implementing rules provided in Art. 7.1 (Interoperability of spatial data sets and services) of the INSPIRE Directive Directive 2007/2/EC.

**Prerequisites**

* Test for the existence of default element namespace.
* Test for the existence of the namespaces for INSPIRE View Services inspire_vs and inspire_common.
* No metadata URL is given in test case [MetadataURL reference INSPIRE service metadata](MetadataURL reference INSPIRE service metadata.md)

**Test method**

* Check if there is a [Conformity](#Conformity) node in the [ExtendedCapabilities](#ExtendedCapabilities) section.
* If yes, check that it has a [Deegree](#Degree) node with one of these values: notEvaluated, conformant, notConformant.


**Reference(s)**:
* [TG VS](README.md#ref_TG_VS), Chapter 4.2.3.3.1.11

**Test type:** Automated

**Notes**

## Contextual XPath references

The namespace prefixes used as described in [README.md](README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
Conformity <a name="Conformity"></a> | /wms:WMS_Capabilities/wms:Capability/inspire_vs:ExtendedCapabilities/inspire_common:Conformity
ExtendedCapabilities <a name="ExtendedCapabilities"></a> | /wms:WMS_Capabilities/wms:Capability/inspire_vs:ExtendedCapabilities
Degree <a name="Degree"></a> | /wms:WMS_Capabilities/wms:Capability/inspire_vs:ExtendedCapabilities/inspire_common:Conformity/inspire_common:Degree