# Check Conformity node

**Purpose**: An extension shall be used to map this to an `<inspire_common:Conformity>` element within an ` <inspire_vs:ExtendedCapabilities>` element.

**Prerequisites**

* [Schema validation](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/schema-validation)

**Test method**

This test only applies to [scenario 2](#scenario-2). Otherwise the test case is skipped.

Check, if there is a [Conformity](#Conformity) node in the [ExtendedCapabilities](#ExtendedCapabilities) section.

**Reference(s)**:
* [TG VS](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/README#ref_TG_VS), Chapter 4.2.3.3.1.11

**Test type**: Automated

**Notes**

## Contextual XPath references

The namespace prefixes used as described in [README.md](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/README#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
Conformity <a name="Conformity"></a> | /wms:WMS_Capabilities/wms:Capability/inspire_vs:ExtendedCapabilities/inspire_common:Conformity
scenario 2 <a name="scenario-2"/> | /wms:WMS_Capabilities/wms:Capability/inspire_vs:ExtendedCapabilities[inspire_common:ResourceLocator or inspire_common:ResourceType or inspire_common:TemporalReference or inspire_common:Conformity or inspire_common:MetadataPointOfContact or inspire_common:MetadataDate or inspire_common:SpatialDataServiceType or inspire_common:MandatoryKeyword or inspire_common:Keyword]