#  Check EX_geographicboundingbox node

**Purpose**: Geographic Bounding Box shall be mapped to the EX_GeographicBoundingBox element of Layer elements.

**Prerequisites**

* Test for the existence of default element namespace.
* Test for the existence of the namespaces for INSPIRE View Services inspire_vs and inspire_common.

**Test method**

* Check if there is a EX_GeographicBoundingBox node in each Layer section of the Capabilities section.


**Reference(s)**:
* [TG VS](README.md#ref_TG_VS), Chapter 4.2.3.3.1.7

**Test type:** Automated

**Notes**

## Contextual XPath references

The namespace prefixes used as described in [README.md](README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
EX_GeographicBoundingBox <a name="EX_GeographicBoundingBox"></a> | /wms:WMS_Capabilities/wms:Capability/wms:Layer/wms:EX_GeographicBoundingBox
Layer <a name="Layer"></a> | /wms:WMS_Capabilities/wms:Capability/wms:Layer
Capabilities <a name="Capabilities"></a> | /wms:WMS_Capabilities/wms:Capability