# Default language

**Purpose**: The default language for the service must be provided in order the user to be able to know which
language can be expected to be used if the capabilities document when no language is explicitly requested. 

**Prerequisites**

* [Schema validation](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/schema-validation)
* [Supported and response languages node](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/supported-and-response-languages-node)

**Test method**

* Let the value of [GetCapabilities OnlineResource](#getcap-href) be ```getcapabilities-url```.
* Let the [default language code](#default-language) be ```lang-code```.
* Create a GetCapabilities HTTP request by adding the parameters ```SERVICE=WMS```, ```REQUEST=GetCapabilities```, ```VERSION=1.3.0``` to the ```getcapabilities-url```.
* Execute the request. If the returned resource can be parsed as a valid XML document and if the document passes tests [Schema validation](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/schema-validation) and [supported and response languages node](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/supported-and-response-languages-node):
  * Check that the [response language code](#response-language) equals the ```lang-code```.
  * Check that all elements gmd:Language equals the ```lang-code```. If it does not, fail the test for this language.
  

* Let ```unsupported-lang``` be a language code that is not included in the supported languages or is empty.
* Create a GetCapabilities HTTP request by adding the parameters SERVICE=WMS, REQUEST=GetCapabilities, VERSION=1.3.0 and LANGUAGE=unsupported-lang to the getcapabilities-url.
* Execute the request. If the returned resource can be parsed as a valid XML document and if the document passes tests [Schema validation](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/schema-validation) and [supported and response languages node](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/supported-and-response-languages-node):
  * Check that [response language](#response-language) correspond to the service [default language code](#default-language). If it does not, fail the test for this language.
  
**Reference(s)**:

* [TG VS](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/README#ref_TG_VS), chapter 4.3.1, Requirement 68, 69, 70, 71 , 73
* [lang-code ISO 639-2](https://www.loc.gov/standards/iso639-2/php/code_list.php)
**Test type**: Automated

**Notes**

## Contextual XPath references

The namespace prefixes used as described in [README.md](http://inspire.ec.europa.eu/id/ats/view-service/3.11/iso-19128/README#namespaces).

Abbreviation                                               |  XPath expression (relative to wms:WMS_Capabilities)
---------------------------------------------------------- | -------------------------------------------------------------------------
GetCapabilities OnlineResource <a name="getcap-href"></a> | /wms:WMS_Capabilities/wms:Capability/wms:Request/wms:GetCapabilities/wms:DCPType/wms:HTTP/(wms:Get&#124;wms:Post)[1]/wms:OnlineResource/@xlink:href
DefaultLanguage <a name="default-language"></a>   | ./wms:Capability/inspire_vs:ExtendedCapabilities[1]/inspire_common:SupportedLanguages/inspire_common:DefaultLanguage/inspire_common:Language
OnlineResource <a name="getcap-href"></a> | ./wms:Capability/wms:Request/wms:GetCapabilities/wms:DCPType/wms:HTTP/(wms:Get&#124;wms:Post)[1]/wms:OnlineResource/@xlink:href
ResponseLanguage <a name="response-language"></a>   | ./wms:Capability/inspire_vs:ExtendedCapabilities[1]/inspire_common:ResponseLanguage/inspire_common:Language
