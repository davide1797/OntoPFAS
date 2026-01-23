# Ontometrics Explanation and Comparison

This document explains four representative **ontometrics** used to characterize the structural properties of ontologies, and then reports their values for several example ontologies.

## 1. Attribute Richness (AR)

**Formula**
$`
\text{AR} = \frac{\text{ATT}}{\text{C}}
`$

 It is computed as the number of attributes for all classes (ATT) divided by the number of classes (C). 

**Meaning**
Attribute Richness measures how much *descriptive information* is attached to classes. A higher value indicates that classes are richly described with data properties (e.g., labels, measurements, identifiers, annotations).

**Problems with low values**

* Classes may be weakly described or overly abstract.
* The ontology may rely almost exclusively on class hierarchies rather than detailed class descriptions.
* Reduced usefulness for data annotation and instance-level reasoning.

## 2. Inheritance Richness (IR)

**Formula**
$`
\text{IR} = \frac{\sum_{C_i \in C}{|H^C(C_1, C_i)|}}{\text{C}}
`$

The inheritance richness of the schema (IR) is defined as the average number of subclasses per class. The number of subclasses of a class is defined as |$`H^C(C_1,C_i)`$|. H is the number of inheritance relationships. 

**Meaning**
Inheritance Richness reflects how classes are organized into a hierarchy. High values indicate deep or broad taxonomies, while low values suggest a flatter structure.

**Problems with low values**

* Limited conceptual specialization.
* Poor support for reasoning based on subsumption.
* Ontology may behave more like a controlled vocabulary than a taxonomy.

## 3. Relationship Richness (RR)

**Formula**
$`
\text{RR} = \frac{\text{|P|}}{\text{|H| + |P|}}
`$

The relationship richness (RR) of a schema is defined as the ratio of the number of (non-inheritance) relationships (P), divided by the total number of relationships defined in the schema (the sum of the number of inheritance relationships (H) and non-inheritance relationships (P)). 

**Meaning**
Relationship Richness measures the diversity of semantic relations beyond simple *is-a* links (e.g., part-of, regulates, causes). Higher values indicate richer semantic modeling.

**Problems with low values**

* Ontology semantics are dominated by subclass relations.
* Limited ability to represent complex domain interactions.
* Reduced expressiveness for querying and reasoning.

## 4. Class / Relation Ratio (CRR)

**Formula**
$`
\text{Class/Relation Ratio} = \frac{\text{Number of classes}}{\text{Number of relationships}}
`$

**Meaning**
This ratio indicates the balance between conceptual entities (classes) and their connections (relations). Lower values imply a more highly connected ontology.

**Problems with high values**

* Many isolated or weakly connected classes.
* Limited semantic integration.
* Harder to exploit graph-based reasoning or traversal.


## Ontometrics Comparison Table

| Ontology  | Attribute Richness | Inheritance Richness | Relationship Richness | Class/Relation Ratio |
| --------- | -----------------: | -------------------: | --------------------: | -------------------: |
| ExO<sup>1</sup>   |           0.000000 |             0.776978 |              0.255172 |             0.958621 |
| ENVO<sup>2</sup>  |           0.000142 |             1.663727 |              0.112528 |             0.533424 |
| ChEBI<sup>3</sup> |           0.000000 |                   NA |              0.000026 |             0.587754 |
| PKO<sup>4</sup>   |           0.810811 |             0.324324 |              0.851852 |             0.456790 |
| COVIDO<sup>5</sup>|           0.587156 |             0.834862 |              0.340580 |             0.789855 |
| OntoPFAS  |           0.738095 |             0.714286 |              0.739130 |             0.365217 |

**Note:** For *ChEBI*, Inheritance Richness is reported as *NA* because the computation required much computational power.

## 
<sup>1</sup>https://bioportal.bioontology.org/ontologies/EXO

<sup>2</sup>https://www.ebi.ac.uk/ols4/ontologies/envo

<sup>3</sup>https://www.ebi.ac.uk/chebi/

<sup>4</sup>https://github.com/perks-project/pk-ontology

<sup>5</sup>https://dl.acm.org/doi/10.1007/s11227-023-05509-4
