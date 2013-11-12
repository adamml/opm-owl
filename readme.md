## Observable Property Model in OWL
The [observedProperty][1] of an OGC [Observations & Measurements Observation][2] is the property of the featureOfInterest that is observed during the act of observation. For example, if the temperature of the featureOfInterest is measured, then the observedProperty is 'temperature'.
 
The observedProperty in O&M must be a reference to some definition of that property. So typically this would be to an item in a published vocabulary. However, it is quite common in practice that definitions of observed properties in published vocabularies are not specific enough to allow end users to interpret exactly which property was observed. 
 
For example, the observedProperty may be 'radiance', and this may be defined in a vocabulary. However the actual property observed is radiance at a particular wavelength or wavelength range e.g. between 300-400 nm. Another example is temperature. It may not be sufficient to simply state that an Observation has the observedProperty 'temperature'. It may be important to know that it is 'Daily Maximum Temperature'. 
 
The [Observable Property Model][1] provides a framework for extending a pre-defined term in a vocabulary with additional information, such as constraints (e.g. the earlier wavelength example), or statistical measures (e.g. the earlier temperature example). 

This repository presents an OWL representaion of the Observable Property Model.

## Classes
### Comparison Operator Value
An enumeration of comparison operators
#### Individuals
##### equalTo
##### greater Than
##### greaterThanOrEqualTo
##### lessThan
##### lessthanOrEqualTo
##### notEqualTo
### Constraint
In order to provide other constraints on ObservableProperties, the type Constraint has been created and can be associated with an ObservableProperty. Constraint types have been provided for scalar, range and category constraints, as well as a generic OtherConstraint data type. The following list provides examples for the constraint types defined: 
#### Category Constraint
A constraint based on some qualifying category. e.g. colour = 'Red'. The value ('Red') of the constraint ('colour') can be any string, although it may be desirable to constrain this in particular application domains.
#### Range Constraint
A numerical range constraint on some property e.g. wavelength >=300nm  and wavelength <=600nm. To be used when data is observed in particular bands or groupings based on a numerical quantity.
#### Scalar Constraint
A numerical scalar constraint on some property e.g. length >= 1m 
#### Other Constraint
Any other constraint type not easily expressed using the other Constraint types.This type may be specialised or the simple description attribute may be used to provide a free text description of the constraint.
### Abstract Observable Property
The AbstractObservableProperty class is the root of the ObservableProperty model. It is implemented by two specialisations: ObservableProperty and CompositeObservableProperty.
#### CompositeObservableProperty
Usually, when performing multiple observations on one featureOfInterest, one provides a separate  ObservableProperty element for each Phenomenon being observed. However, in certain cases where either:
- there is a strong link between the Phenomena or
- the multiple phenomena are clearly observed as part of the same Observation, 

these Phenomena may be provided together in one Observation. In this case a CompositeObservableProperty can be defined that groups together multiple Phenomena (ObservableProperty) into one CompositeObservableProperty element. 
            
An example of a strongly linked pair of Phenomena is wind speed and wind direction
#### ObservableProperty
At its simplest an ObservableProperty simply carries a reference to a phenomenon definition in a codelist with optional units of measure. However an ObservableProperty definition may be augmented using Constraints and/or Statistical Measures to create a more full definition of the observed property.
### Range Bounds
The start and end bounding values of a numerical range (e.g. start >=50, end <=99).
### Statistical Measure
A description of some statistical measure e.g. "daily maximum". The measure is usually some function over some time (e.g. an hour, a day) or space (e.g. a length, area or volume). Other aggregation types can be supported by the 'otherAggregation' extension point.

<!-- References -->
[1]: http://inspire.jrc.ec.europa.eu/documents/Data_Specifications/D2.9_O&M_Guidelines_v2.0rc3.pdf
[2]: http://www.opengeospatial.org/standards/om
