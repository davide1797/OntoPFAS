# Ontometrics Explanation and Comparison

This document explains four common **ontometrics** used to characterize the structural properties of ontologies, and then reports their values for several example ontologies.

---

## 1. Attribute Richness (AR)

**Formula**
\[
\text{Attribute Richness} = \frac{\text{Number of attributes (data properties)}}{\text{Number of classes}}
\]

**Meaning**
Attribute Richness measures how much *descriptive information* is attached to classes. A higher value indicates that classes are richly described with data properties (e.g., labels, measurements, identifiers, annotations).

**Problems with low values**

* Classes may be weakly described or overly abstract.
* The ontology may rely almost exclusively on class hierarchies rather than detailed class descriptions.
* Reduced usefulness for data annotation and instance-level reasoning.

---

## 2. Inheritance Richness (IR)

**Formula**
[
\text{Inheritance Richness} = \frac{\text{Number of subclass relations}}{\text{Number of classes}}
]

**Meaning**
Inheritance Richness reflects how classes are organized into a hierarchy. High values indicate deep or broad taxonomies, while low values suggest a flatter structure.

**Problems with low values**

* Limited conceptual specialization.
* Poor support for reasoning based on subsumption.
* Ontology may behave more like a controlled vocabulary than a taxonomy.

---

## 3. Relationship Richness (RR)

**Formula**
[
\text{Relationship Richness} = \frac{\text{Number of non-inheritance relationships}}{\text{Total number of relationships}}
]

**Meaning**
Relationship Richness measures the diversity of semantic relations beyond simple *is-a* links (e.g., part-of, regulates, causes). Higher values indicate richer semantic modeling.

**Problems with low values**

* Ontology semantics are dominated by subclass relations.
* Limited ability to represent complex domain interactions.
* Reduced expressiveness for querying and reasoning.

---

## 4. Class / Relation Ratio (CRR)

**Formula**
[
\text{Class/Relation Ratio} = \frac{\text{Number of classes}}{\text{Number of relationships}}
]

**Meaning**
This ratio indicates the balance between conceptual entities (classes) and their connections (relations). Lower values imply a more highly connected ontology.

**Problems with high values**

* Many isolated or weakly connected classes.
* Limited semantic integration.
* Harder to exploit graph-based reasoning or traversal.

---

## Ontometrics Comparison Table

| Ontology | Attribute Richness | Inheritance Richness | Relationship Richness | Class/Relation Ratio |
| -------- | -----------------: | -------------------: | --------------------: | -------------------: |
| ExO      |           0.000000 |             0.776978 |              0.255172 |             0.958621 |
| ENVO     |           0.000142 |             1.663727 |              0.112528 |             0.533424 |
| ChEBI    |           0.000000 |                   NA |              0.000026 |             0.587754 |
| PKO      |           0.810811 |             0.324324 |              0.851852 |             0.456790 |
| COVIDO   |           0.587156 |             0.834862 |              0.340580 |             0.789855 
| OntoPFAS |           0.761905 |             0.738095 |              0.655556 |             0.466667 |

**Note:** For *ChEBI*, Inheritance Richness is reported as *NA* because the computation required much computational power.
