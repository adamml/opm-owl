Markdown documentation created by [pyLODE](http://github.com/rdflib/pyLODE) 2.8.3

# Complex Property Model ontology
        

## Metadata
* **URI**
  * `http://purl.org/voc/cpm`
* **Ontology RDF**
  * RDF ([data_file.ttl](turtle))
### Description
<p>An OWL representation of the Complex Property Model (CPM).</p>
<p>The ontology here encodes the CPM defined in the INSPIRE guidelines for Observations &amp; Measurements and Sensor Web Enablement-related standards document.</p>

## Table of Contents
1. [Classes](#classes)
1. [Object Properties](#objectproperties)
1. [Datatype Properties](#datatypeproperties)
1. [Annotation Properties](#annotationproperties)
1. [Namespaces](#namespaces)
1. [Legend](#legend)


## Overview
![](cpm.png)
**Figure 1:** Ontology overview
## Classes
[Abstract Observable Property](#AbstractObservableProperty),
[Composite Observable Property](#CompositeObservableProperty),
[Constraint](#Constraint),
[Matrix](#Matrix1),
[Object of Interest](#ObjectOfInterest),
[Observable Property](#ObservableProperty),
[Phenomenon](#Phenomenon),
[Property](#Property),
[Statistical Measure](#StatisticalMeasure1),
[Substance](#Substance),
[Taxon](#Taxon),
### Abstract Observable Property
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#AbstractObservableProperty`
Description | <p>The AbstractObservableProperty class is the root of the ObservableProperty model. It is implemented  by two specialisations: ObservableProperty and CompositeObservableProperty.</p>
Super-classes |[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />
Sub-classes |[CompositeObservableProperty](CompositeObservableProperty) (c)<br />[ObservableProperty](ObservableProperty) (c)<br />
In range of |[component](component) (op)<br />
### Composite Observable Property
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#CompositeObservableProperty`
Description | <p>Usually, when performing multiple observations on one featureOfInterest, one provides a separate ObservableProperty element for each Phenomenon being observed. However, in certain cases where either a) there is a strong link between the Phenomena or b) the multiple phenomena are clearly observed as part of the same Observation, these Phenomena may be provided together in one Observation. In this case a CompositeObservableProperty can be defined that groups together multiple Phenomena (ObservableProperty) into one CompositeObservableProperty element. </p> <p>An example of a strongly linked pair of Phenomena is wind speed and wind direction</p>
Super-classes |[AbstractObservableProperty](AbstractObservableProperty) (c)<br />[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />
Restrictions |[count](count) (dp) **exactly** 1<br />[component](component) (op) **min** 2<br />
In domain of |[component](component) (op)<br />[count](count) (dp)<br />
### Constraint
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#Constraint`
Description | <p>In order to provide other constraints on ObservableProperties, the type Constraint has been created and can be associated with an ObservableProperty. Constraints may be specialised or the simple description attribute may be used to provide a free text description of the constraint. </p>
Super-classes |[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />
Restrictions |[constraintProperty](ConstrainedProperty) (op) **max** 1<br />[label](label) (dp) **min** 0<br />[label](label) (dp) **max** 1<br />[constraintProperty](ConstrainedProperty) (op) **min** 0<br />
In domain of |[label](label) (dp)<br />[constraintProperty](ConstrainedProperty) (op)<br />
In range of |[restriction](restriction) (op)<br />
### Matrix
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#Matrix`
Description | <p>The matrix is a special case of a feature-of-interest that provides the context (container feeaure or medium) for an observable property.</p>
Super-classes |[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />
In range of |[matrix](Matrix) (op)<br />
### Object of Interest
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#ObjectOfInterest`
Description | <p>The substance, taxon or other physical/chemical phenomenon of the Feature Of Interest that is being observed. E.g.  Waves, Rainfall, Calluna Vulgaris, Aluminium.</p>
Super-classes |[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />
Sub-classes |[Taxon](Taxon) (c)<br />[Phenomenon](Phenomenon) (c)<br />[Substance](Substance) (c)<br />
In range of |[objectOfInterest](ObjectofInterest) (op)<br />
### Observable Property
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#ObservableProperty`
Description | <p>At its simplest an ObservableProperty simply carries a reference to a phenomenon definition in a codelist with optional units of measure. However an ObservableProperty definition may be augmented using Constraints and/or Statistical Measures to create a more full definition of the observed property. </p>
Super-classes |[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />[AbstractObservableProperty](AbstractObservableProperty) (c)<br />
Restrictions |[statisticalMeasure](StatisticalMeasure) (op) **min** 0<br />[property](property) (op) **exactly** 1 [Property](Property) (c)<br />[opUnitOfMeasure](http://purl.org/voc/cpm#opUnitOfMeasure) **min** 0<br />[opUnitOfMeasure](http://purl.org/voc/cpm#opUnitOfMeasure) **max** 1<br />[restriction](restriction) (op) **min** 0<br />[objectOfInterest](ObjectofInterest) (op) **min** 1 [ObjectOfInterest](ObjectOfInterest) (c)<br />
In domain of |[unitOfMeasure](unitofmeasure) (op)<br />[objectOfInterest](ObjectofInterest) (op)<br />[restriction](restriction) (op)<br />[canonicalUnit](canonicalunit) (op)<br />[matrix](Matrix) (op)<br />[statisticalMeasure](StatisticalMeasure) (op)<br />[property](property) (op)<br />
### Phenomenon
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#Phenomenon`
Description | <p>A specialisation of ObjectOfInterest for use where the Object of Interest is a physical phenomen, such as "throughfall" or "waves"</p>
Super-classes |[ObjectOfInterest](ObjectOfInterest) (c)<br />[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />
### Property
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#Property`
Description | <p>The property of the environment which the ObservableProperty is describing.</p>
Super-classes |[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />
In range of |[property](property) (op)<br />
### Statistical Measure
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#StatisticalMeasure`
Description | <pre><code>        A description of some statistical measure e.g. "daily maximum". The measure is usually some function over some time (e.g. an hour, a day) or space (e.g. a length, area or volume). Other aggregation types can be supported by the 'otherAggregation' extension point. </code></pre>
Super-classes |[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />
Restrictions |[derivedFrom](derivedFrom) (op) **max** 1<br />[aggregationVolume](aggregationVolume) (op) **min** 0<br />[aggregationArea](aggregationArea) (op) **min** 0<br />[otherAggregation](otherAggregation) (op) **max** 1<br />[aggregationTimePeriod](aggregationTimePeriod) (op) **max** 1<br />[aggregationTimePeriod](aggregationTimePeriod) (op) **min** 0<br />[aggregationVolume](aggregationVolume) (op) **max** 1<br />[aggregationLength](aggregationLength) (op) **max** 1<br />[aggregationLength](aggregationLength) (op) **min** 0<br />[derivedFrom](derivedFrom) (op) **min** 0<br />[otherAggregation](otherAggregation) (op) **min** 0<br />[aggregationArea](aggregationArea) (op) **max** 1<br />[label](label) (dp) **max** 1<br />[label](label) (dp) **min** 0<br />
In domain of |[label](label) (dp)<br />[aggregation](aggregation) (op)<br />[derivedFrom](derivedFrom) (op)<br />
In range of |[derivedFrom](derivedFrom) (op)<br />[statisticalMeasure](StatisticalMeasure) (op)<br />
### Substance
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#Substance`
Description | <p>A specialisation of ObjectOfInterest for use where the Object of Interest is a chemical substance</p>
Super-classes |[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />[ObjectOfInterest](ObjectOfInterest) (c)<br />
Restrictions |[casNumber](CASNumber) (dp) **min** 0<br />
In domain of |[casNumber](CASNumber) (dp)<br />
### Taxon
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#Taxon`
Description | <p>A specialisation of ObjectOfInterest for use where the Object of Interest is an organism with a binomial classification</p>
Super-classes |[ObjectOfInterest](ObjectOfInterest) (c)<br />[skos:Concept](http://www.w3.org/2004/02/skos/core#Concept) (c)<br />

## Object Properties
[aggregation](#aggregation),
[aggregationArea](#aggregationArea),
[aggregationLength](#aggregationLength),
[aggregationTimePeriod](#aggregationTimePeriod),
[aggregationVolume](#aggregationVolume),
[canonical unit](#canonicalunit),
[component](#component),
[Constrained Property](#ConstrainedProperty),
[derivedFrom](#derivedFrom),
[Matrix](#Matrix),
[Object of Interest](#ObjectofInterest),
[otherAggregation](#otherAggregation),
[property](#property),
[restriction](#restriction),
[Statistical Measure](#StatisticalMeasure),
[unit of measure](#unitofmeasure),
[related](#related),
[](aggregation)
### aggregation
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#aggregation`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[StatisticalMeasure](StatisticalMeasure1) (c)<br />
Range(s) |[xsd:anyURI](http://www.w3.org/2001/XMLSchema#anyURI) (c)<br />
[](aggregationArea)
### aggregationArea
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#aggregationArea`
Super-properties |[aggregation](aggregation) (op)<br />[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
[](aggregationLength)
### aggregationLength
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#aggregationLength`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />[aggregation](aggregation) (op)<br />
[](aggregationTimePeriod)
### aggregationTimePeriod
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#aggregationTimePeriod`
Super-properties |[aggregation](aggregation) (op)<br />[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
[](aggregationVolume)
### aggregationVolume
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#aggregationVolume`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />[aggregation](aggregation) (op)<br />
[](canonicalunit)
### canonical unit
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#canonicalUnit`
Super-properties |[unitOfMeasure](unitofmeasure) (op)<br />[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[ObservableProperty](ObservableProperty) (c)<br />
[](component)
### component
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#component`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[CompositeObservableProperty](CompositeObservableProperty) (c)<br />
Range(s) |[AbstractObservableProperty](AbstractObservableProperty) (c)<br />
[](ConstrainedProperty)
### Constrained Property
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#constraintProperty`
Super-properties |[property](property) (op)<br />[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[Constraint](Constraint) (c)<br />
Range(s) |[xsd:anyURI](http://www.w3.org/2001/XMLSchema#anyURI) (c)<br />
[](derivedFrom)
### derivedFrom
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#derivedFrom`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[StatisticalMeasure](StatisticalMeasure1) (c)<br />
Range(s) |[StatisticalMeasure](StatisticalMeasure1) (c)<br />
[](Matrix)
### Matrix
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#matrix`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[ObservableProperty](ObservableProperty) (c)<br />
Range(s) |[Matrix](Matrix1) (c)<br />
[](ObjectofInterest)
### Object of Interest
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#objectOfInterest`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[ObservableProperty](ObservableProperty) (c)<br />
Range(s) |[ObjectOfInterest](ObjectOfInterest) (c)<br />
[](otherAggregation)
### otherAggregation
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#otherAggregation`
Super-properties |[aggregation](aggregation) (op)<br />
[](property)
### property
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#property`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[ObservableProperty](ObservableProperty) (c)<br />
Range(s) |[Property](Property) (c)<br />[xsd:anyURI](http://www.w3.org/2001/XMLSchema#anyURI) (c)<br />
[](restriction)
### restriction
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#restriction`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[ObservableProperty](ObservableProperty) (c)<br />
Range(s) |[Constraint](Constraint) (c)<br />
[](StatisticalMeasure)
### Statistical Measure
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#statisticalMeasure`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[ObservableProperty](ObservableProperty) (c)<br />
Range(s) |[xsd:anyURI](http://www.w3.org/2001/XMLSchema#anyURI) (c)<br />[StatisticalMeasure](StatisticalMeasure1) (c)<br />
[](unitofmeasure)
### unit of measure
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#unitOfMeasure`
Super-properties |[skos:related](http://www.w3.org/2004/02/skos/core#related) (op)<br />
Domain(s) |[ObservableProperty](ObservableProperty) (c)<br />
[](related)
### related
Property | Value
--- | ---
URI | `http://www.w3.org/2004/02/skos/core#related`

## Datatype Properties
[CAS Number](#CASNumber),
[count](#count),
[label](#label),
[value](#value),
[altLabel](#altLabel),
[prefLabel](#prefLabel),
[](CASNumber)
### CAS Number
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#casNumber`
Super-properties |[skos:altLabel](http://www.w3.org/2004/02/skos/core#altLabel) (dp)<br />
Domain(s) |[Substance](Substance) (c)<br />
Range(s) |[xsd:string](http://www.w3.org/2001/XMLSchema#string) (c)<br />
[](count)
### count
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#count`
Domain(s) |[CompositeObservableProperty](CompositeObservableProperty) (c)<br />
Range(s) |[xsd:nonNegativeInteger](http://www.w3.org/2001/XMLSchema#nonNegativeInteger) (c)<br />
[](label)
### label
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#label`
Super-properties |[skos:prefLabel](http://www.w3.org/2004/02/skos/core#prefLabel) (dp)<br />
Domain(s) |[StatisticalMeasure](StatisticalMeasure1) (c)<br />[Constraint](Constraint) (c)<br />
Range(s) |[xsd:string](http://www.w3.org/2001/XMLSchema#string) (c)<br />
[](value)
### value
Property | Value
--- | ---
URI | `http://purl.org/voc/cpm#value`
[](altLabel)
### altLabel
Property | Value
--- | ---
URI | `http://www.w3.org/2004/02/skos/core#altLabel`
[](prefLabel)
### prefLabel
Property | Value
--- | ---
URI | `http://www.w3.org/2004/02/skos/core#prefLabel`

## Annotation Properties
[definition](#definition),
[notation](#notation),
[](definition)
### definition
Property | Value
--- | ---
URI | `http://www.w3.org/2004/02/skos/core#definition`
[](notation)
### notation
Property | Value
--- | ---
URI | `http://www.w3.org/2004/02/skos/core#notation`

## Named Individuals
## Namespaces
* **:**
  * `http://purl.org/voc/cpm#`
* **owl**
  * `http://www.w3.org/2002/07/owl#`
* **prov**
  * `http://www.w3.org/ns/prov#`
* **rdf**
  * `http://www.w3.org/1999/02/22-rdf-syntax-ns#`
* **rdfs**
  * `http://www.w3.org/2000/01/rdf-schema#`
* **sdo**
  * `https://schema.org/`
* **skos**
  * `http://www.w3.org/2004/02/skos/core#`
* **vann**
  * `http://purl.org/vocab/vann/`
* **xsd**
  * `http://www.w3.org/2001/XMLSchema#`

## Legend
* Classes: c
* Object Properties: op
* Functional Properties: fp
* Data Properties: dp
* Annotation Properties: dp
* Properties: p
* Named Individuals: ni
