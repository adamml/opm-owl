## Observable Property Model in OWL
The observedProperty [1] of an OGC Observations & Measurements Observation [2] is the property of the featureOfInterest that is observed during the act of observation. For example, if the temperature of the featureOfInterest is measured, then the observedProperty is 'temperature'.
 
The observedProperty in O&M must be a reference to some definition of that property. So typically this would be to an item in a published vocabulary. However, it is quite common in practice that definitions of observed properties in published vocabularies are not specific enough to allow end users to interpret exactly which property was observed. 
 
For example, the observedProperty may be 'radiance', and this may be defined in a vocabulary. However the actual property observed is radiance at a particular wavelength or wavelength range e.g. between 300-400 nm. Another example is temperature. It may not be sufficient to simply state that an Observation has the observedProperty 'temperature'. It may be important to know that it is 'Daily Maximum Temperature'. 
 
The Observable Property Model [1] provides a framework for extending a pre-defined term in a vocabulary with additional information, such as constraints (e.g. the earlier wavelength example), or statistical measures (e.g. the earlier temperature example). 



### References
[1] Draft Guidelines for the use of Observations & Measurements and Sensor Web Enablement-related standards in INSPIRE Annex II and III data specification development [v2.0 rc3](http://inspire.jrc.ec.europa.eu/documents/Data_Specifications/D2.9_O&M_Guidelines_v2.0rc3.pdf)

[2] Open Geospatial Consortium Standards: [Observations & Measurements](http://www.opengeospatial.org/standards/om)
