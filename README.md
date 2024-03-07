<div class="section" about="#" typeof="owl:Ontology">

Author  
<a href="https://doriantaylor.com/person/dorian-taylor#me"
rel="dct:creator"><span property="foaf:name">Dorian Taylor</span></a>

Version  
0.14

Created  
January 23, 2012

[Updated](https://vocab.methodandstructure.com/content-inventory#sec-changelog)  
November 2, 2022

Namespace URI  
[`https://vocab.methodandstructure.com/content-inventory#`](https://vocab.methodandstructure.com/content-inventory#)

Preferred Namespace Prefix  
`ci`

Imports  
<a href="https://www.w3.org/TR/owl2-overview/" about="#"
rel="owl:imports" resource="http://www.w3.org/2002/07/owl#">OWL</a>

<a
href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/"
about="#" rel="owl:imports" resource="http://purl.org/dc/terms/">Dublin
Core Terms</a>

<a href="https://www.w3.org/TR/xmlschema-2/" about="#" rel="owl:imports"
resource="http://www.w3.org/2001/XMLSchema#">XML Schema Part 2:
Datatypes</a>

<a
href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/"
about="#" rel="owl:imports" resource="http://purl.org/dc/terms/">Dublin
Core Terms</a>

</div>

<div class="section">

This vocabulary defines a number of concepts peculiar to
<a href="http://en.wikipedia.org/wiki/Content_strategy"
rel="dct:references" title="Content strategy — Wikipedia">content
strategy</a> which are not accounted for by other vocabularies.

Such vocabularies include, but are far from limited to:

-   <a href="http://purl.org/dc/terms/" rel="owl:imports">Dublin Core
    Terms</a> provide basic bibliographic metadata,
-   The
    <a href="http://purl.org/ontology/bibo/" rel="owl:imports">Bibliography
    Ontology</a> provides additional bibliographic metadata plus dozens
    of useful document types,
-   FRBR <a href="http://vocab.org/frbr/core" rel="dct:references"
    title="Expression of Core FRBR Concepts in RDF">Core</a> and
    <a href="http://vocab.org/frbr/extended" rel="dct:references"
    title="Expression of Extended FRBR Concepts in RDF">Extended</a>
    provides terms for modeling even more sophisticated intertextual
    relations,
-   <a href="https://www.w3.org/TR/skos-reference/" rel="owl:imports"
    resource="http://www.w3.org/2004/02/skos/core#">SKOS</a> provides a
    rich substrate for concept schemes and taxonomies,
-   <a href="http://xmlns.com/foaf/0.1/" rel="owl:imports">Friend of a
    Friend</a> and
    <a href="https://www.w3.org/TR/vocab-org/" rel="owl:imports">The
    Organization Ontology</a> give us models of people and business
    entities,
-   The <a href="http://purl.org/NET/c4dm/event.owl#" rel="owl:imports"
    title="The Event Ontology">Event Ontology</a> enables the modeling
    of processes, factors, and outcomes,
-   <a href="https://www.w3.org/TR/prov-o/" rel="dct:references">The
    Provenance Ontology</a> gives us a vocabulary for recording the
    handling of content over time,
-   The
    <a href="http://purl.org/linked-data/cube#" rel="owl:imports">Data Cube
    Vocabulary</a> organizes quantitative and statistical data.

This document is organized in terms of
[Classes](https://vocab.methodandstructure.com/content-inventory#sec-classes),
[Properties](https://vocab.methodandstructure.com/content-inventory#sec-properties),
[Individuals](https://vocab.methodandstructure.com/content-inventory#sec-individuals),
and an appendix for the [Data Structure
Definition](https://vocab.methodandstructure.com/content-inventory#sec-dsd)
for quantitative content analytics. Terms are organized topologically
first, and alphabetically second.

### Reading the Examples

Examples are given in [the Turtle
syntax](https://www.w3.org/TR/turtle/). The basic syntax reads like so:

    <subject> <predicate> <object> .

    <subject> <predicate> <object> ; <predicate> <object> .

    <subject> <predicate> <object> , <object> .

That is, complete statements are separated by periods, predicate-object
pairs are collated by semicolons, and sets of objects are separated by
commas. Turtle also provides for <span class="dfn">prefix
mappings</span> to shorten the terms. This is denoted by:

    @prefix p: <https://example.club/long/uri/> .

and thus would map `p:some-term` to
`https://example.club/long/uri/some-term`. Note that these strings are
just concatenated together, in contrast to conventional relative URI
resolution. Terms belonging to this specification have been emphasized
to make them easier to pick out.

</div>

<div id="sec-classes" class="section" about="#">

## Classes

There are currently many extant vocabularies that deal with documents
and related entities. The classes here are those that aren't otherwise
accounted for.

![This diagram shows the classes and properties defined in this document
using solid lines, and third-party classes and properties using dashed
lines.](https://vocab.methodandstructure.com/content-inventory-classes)

<div class="section">

### Editorial Action

These classes enable the assignment of specific things to *do* to a
document.

<div id="Action" class="section" about="[ci:Action]" typeof="owl:Class">

#### `Action`

An action, as its name implies, is meant to represent something a person
or other agent ought to do to a document.

Being a subclass of an event, a `ci:Action` can have agents, factors,
products, places and times ascribed to it.

Subclass of:  
<a href="http://motools.sourceforge.net/event/event.html#term_Event"
rel="rdfs:subClassOf"
resource="http://purl.org/NET/c4dm/event.owl#Event"><code>ev:Event</code></a>

Currently defined:  
-   [`keep`](https://vocab.methodandstructure.com/content-inventory#keep)
-   [`split`](https://vocab.methodandstructure.com/content-inventory#split)
-   [`tentative-merge`](https://vocab.methodandstructure.com/content-inventory#tentative-merge)
-   [`update-metadata`](https://vocab.methodandstructure.com/content-inventory#update-metadata)
-   [`proofread`](https://vocab.methodandstructure.com/content-inventory#proofread)
-   [`revise`](https://vocab.methodandstructure.com/content-inventory#revise)
-   [`rewrite`](https://vocab.methodandstructure.com/content-inventory#rewrite)
-   [`retire`](https://vocab.methodandstructure.com/content-inventory#retire)

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Merge" class="section" about="[ci:Merge]" typeof="owl:Class">

#### `Merge`

In order to merge a document, we must define the target to which it
ought to be merged. This class is identical to an Action, save for such
a property.

Subclass of:  
<a href="https://vocab.methodandstructure.com/content-inventory#Action"
rel="rdfs:subClassOf"><code>ci:Action</code></a>

Properties:  
<a href="https://vocab.methodandstructure.com/content-inventory#target"
rev="rdfs:domain"><code>ci:target</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Document Classes/Decorators

Ontologies like BIBO are far from exhaustive in their breadth of
document types, so any additional salient document types will go here.

<div id="Abstract" class="section" about="[ci:Abstract]"
typeof="owl:Class">

#### `Abstract`

This is an explicit document abstract/executive summary class, intended
to belong to BIBO, which appears to be abandonware.

Subclass of:  
<a href="http://purl.org/ontology/bibo/DocumentPart"
rel="rdfs:subClassOf"><code>bibo:DocumentPart</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Advertisement" class="section" about="[ci:Advertisement]"
typeof="owl:Class">

#### `Advertisement`

In general there is no programmatic way to tell whether a resource is an
advertisement, since advertisements on the Web look (to a machine) like
any other resource. This is intended to be a decorator class to indicate
that the subject is an advertisement. It can therefore be combined with
other classes such as `foaf:Image`, or `bibo:AudioVisualDocument`.

```
@prefix bibo: <http://purl.org/ontology/bibo/> .
@prefix dct:  <http://purl.org/dc/terms/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix ci:   <https://vocab.methodandstructure.com/content-inventory#> .

<https://example.club/17-mindblowing-ways-to-write-listicles> a bibo:Article ;
dct:title "17 Mindblowing Ways to Write Listicles!"@en ;
dct:hasPart <https://adtech.biz/assets/punch-the-monkey> .

<https://adtech.biz/assets/punch-the-monkey> a foaf:Image, ci:Advertisement ;
dct:title "Punch The Monkey And WIN!#@$!%%^!"@en .
```

Subclass of:  
<a href="http://xmlns.com/foaf/spec/#term_Document"
rel="rdfs:subClassOf"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Appendix" class="section" about="[ci:Appendix]"
typeof="owl:Class">

#### `Appendix`

This is an explicit document appendix class, intended to belong to BIBO,
which appears to be abandonware.

Subclass of:  
<a href="http://purl.org/ontology/bibo/DocumentPart"
rel="rdfs:subClassOf"><code>bibo:DocumentPart</code></a>

See also:  
<a
href="https://github.com/structureddynamics/Bibliographic-Ontology-BIBO/pull/17"
rel="rdfs:seeAlso">the 2018 pull request proposing the addition</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Block" class="section" about="[ci:Block]" typeof="owl:Class">

#### `Block`

This is intended to represent a generic block-level segment, such as a
paragraph, list, figure, or table.

Subclass of:  
<a href="http://purl.org/ontology/bibo/DocumentPart"
rel="rdfs:subClassOf"><code>bibo:DocumentPart</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Section" class="section" about="[ci:Section]"
typeof="owl:Class">

#### `Section`

This is an explicit document section (i.e., sub-chapter) class.

Subclass of:  
<a href="http://purl.org/ontology/bibo/DocumentPart"
rel="rdfs:subClassOf"><code>bibo:DocumentPart</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Variation

This section is for classes that have to do with creating content that
can vary. Currently the only class defined is `ci:Variable`, which is a
way to refer to values which are defined elsewhere and thus can maintain
their consistency across the document.

<div id="Variable" class="section" about="[ci:Variable]"
typeof="owl:Class">

#### `Variable`

Identifies a variable which can be embedded into a document and assigned
an `rdf:value`.

<div property="skos:example">

Consider the markup:

    <p about="https://example.biz/ratecard#">Shingy's bill-out rate is <span rel="dct:references">
    <var about="#rate" typeof="ci:Variable" property="rdf:value" datatype="xsd:decimal">100.00</var>
    <var about="#unit" typeof="ci:Variable" property="rdf:value" datatype="xsd:token">USD</var>
    </span> per hour.</p>

…which when parsed will produce the statements:

    @base <https://example.biz/ratecard#> .
    @prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
    @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
    @prefix dct: <http://purl.org/dc/terms/> .
    @prefix ci:  <https://vocab.methodandstructure.com/content-inventory#> .

    <> dct:references <#rate>, <#unit> .

    <#rate> a ci:Variable ; rdf:value "100.00"^^xsd:decimal .
    <#unit> a ci:Variable ; rdf:value "USD"^^xsd:token .

</div>

See also:  
<a href="https://www.w3.org/TR/rdf-schema/#ch_value" rel="rdfs:seeAlso"
resource="rdf:value"><code>rdf:value</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Audience Modelling

Classes involved in describing audiences will go here.

<div id="Audience" class="section" about="[ci:Audience]"
typeof="owl:Class">

#### `Audience`

An audience represents the set of people who are the intended recipients
of the resource. This class is at once an agent class as well as a
conceptual entity, capable of being mixed into a SKOS concept scheme.

Subclass of:  
<a
href="http://www.dublincore.org/specifications/dublin-core/dcmi-terms/#terms-AgentClass"
rel="rdfs:subClassOf"
resource="http://purl.org/dc/terms/AgentClass"><code>dct:AgentClass</code></a>

<a href="https://www.w3.org/TR/skos-reference/#concepts"
rel="rdfs:subClassOf"
resource="http://www.w3.org/2004/02/skos/core#Concept"><code>skos:Concept</code></a>

Properties:  
<a
href="https://vocab.methodandstructure.com/content-inventory#aware-of"
rev="rdfs:domain"><code>ci:aware-of</code></a>

<a
href="https://vocab.methodandstructure.com/content-inventory#understands"
rev="rdfs:domain"><code>ci:understands</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#values"
rev="rdfs:domain"><code>ci:values</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#eschews"
rev="rdfs:domain"><code>ci:eschews</code></a>

<a
href="https://vocab.methodandstructure.com/content-inventory#exemplar"
rev="rdfs:domain"><code>ci:exemplar</code></a>

See also:  
<a href="http://dublincore.org/documents/dcmi-terms/#terms-audience"
rel="rdfs:seeAlso"
resource="http://purl.org/dc/terms/audience"><code>dct:audience</code></a>

<a href="https://www.w3.org/TR/vocab-org/#org:Role" rel="rdfs:seeAlso"
resource="http://www.w3.org/ns/org#Role"><code>org:Role</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

</div>

<div id="sec-properties" class="section" about="#">

## Properties

<div class="section">

### Authorial/Editorial Intent

After a content inventory comes an audit, wherein we figure out what we
want to do with the content. The following properties govern *who* the
document is (not) for and *what outcome* it is supposed to accomplish.

<div id="desired-outcome" class="section" about="[ci:desired-outcome]"
typeof="owl:ObjectProperty">

#### `desired-outcome`

This property is intended to indicate what the document is supposed to
do—what material effect it is supposed to produce. It is intentionally
open-ended, and as such can point to something like a `skos:Concept`,
another document, or a literal string of text describing the outcome.

```
@prefix bibo: <http://purl.org/ontology/bibo/> .
@prefix dct:  <http://purl.org/dc/terms/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix ci:   <https://vocab.methodandstructure.com/content-inventory#> .
@prefix eg:   <https://backoffice.example.club/concepts/> .

# we can extend our article metadata the following way:

<https://example.club/17-mindblowing-ways-to-write-listicles> a bibo:Article ;
dct:title "17 Mindblowing Ways to Write Listicles!"@en ;
ci:desired-outcome eg:maximize-clicks .

# and create a corresponding resource to unambiguously identify the goal:

eg:maximize-clicks a skos:Concept ;
skos:prefLabel "Maximize Clicks"@en ;
skos:description "Moar clicks means moar monies."@en .
            
```

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Sub-property of:  
<a href="http://purl.org/dc/terms/type"
rel="rdfs:subPropertyOf"><code>dct:type</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="non-audience" class="section" about="[ci:non-audience]"
typeof="owl:ObjectProperty">

#### `non-audience`

This property complements `dct:audience` insofar as enabling the author
or editor to designate a set of entities who are explicitly *not* the
intended audience of the document.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Range:  
<a href="http://purl.org/dc/terms/AgentClass"
rel="rdfs:range"><code>dct:AgentClass</code></a>

See also:  
<a href="http://dublincore.org/documents/dcmi-terms/#terms-audience"
rel="rdfs:seeAlso"
resource="http://purl.org/dc/terms/audience"><code>dct:audience</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Editing Tasks

A content audit will generate actionable tasks on some subset of the
inventoried documents. Use `ci:action` to relate a document to an
action, including one or more of the actions [specified in this
document](https://vocab.methodandstructure.com/content-inventory#sec-actions).
A `ci:Merge` is a special kind of `ci:Action` that takes a `ci:target`,
as in the following example:

    @prefix bibo: <http://purl.org/ontology/bibo/> .
    @prefix bs:   <http://purl.org/ontology/bibo/status/> .
    @prefix ci:   <https://vocab.methodandstructure.com/content-inventory#> .

    <https://example.club/our-team> a bibo:Webpage ;
    bibo:status bs:published, ci:obsolete ;
    ci:action <tag:example.club,2020-01:content-inventory/merge/our-team> .

    <tag:example.club,2020-01:content-inventory:merge:our-team> a ci:Merge ;
    ci:target <https://example.club/about> .

This example is in [Turtle syntax](https://www.w3.org/TR/turtle/). It is
stating that the published document at `https://example.club/our-team`
is obsolete and should be merged into `https://example.club/about`. A
[`tag:` URI](https://tools.ietf.org/html/rfc4151) was chosen to identify
the merge, to reinforce the idea that it is just a piece of data and not
a Web page (although one could imagine representing it as one).

<div id="action" class="section" about="[ci:action]"
typeof="owl:ObjectProperty">

#### `action`

Relates a document to an action to take.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/content-inventory#Action"
rel="rdfs:range"><code>ci:Action</code></a>

Sub-property of:  
<a href="http://purl.org/NET/c4dm/event.owl#factor_of"
rel="rdfs:subPropertyOf"><code>ev:factor_of</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="target" class="section" about="[ci:target]"
typeof="owl:ObjectProperty">

#### `target`

Specify the URI of the target resource into which this document should
be merged.

Domain:  
<a href="https://vocab.methodandstructure.com/content-inventory#Merge"
rel="rdfs:domain"><code>ci:Merge</code></a>

Range:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:range"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Conceptual Relations

Documents, if they don't explicitly *mention*, certainly *allude to
concepts*. Certain documents may *introduce* or *define* a concept,
making it suitable introductory material. Still other documents may
evoke images or concepts which members of the audience are actually
trying to *avoid*. The following properties relate documents to
concepts, specifically whether a document mentions, introduces, evokes
without mentioning, or otherwise assumes a level of understanding on the
part of the audience.

The concepts themselves belong to an ordinary SKOS concept scheme, and
can be reasoned over using their ordinary semantic relations
(`skos:broader`, `skos:narrower`, `skos:related`).

<div id="mentions" class="section" about="[ci:mentions]"
typeof="owl:ObjectProperty">

#### `mentions`

The document explicitly mentions this concept.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Range:  
<a href="https://www.w3.org/TR/skos-reference/#concepts"
rel="rdfs:range"
resource="http://www.w3.org/2004/02/skos/core#Concept"><code>skos:Concept</code></a>

Sub-property of:  
<a href="http://purl.org/dc/terms/references"
rel="rdfs:subPropertyOf"><code>dct:references</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="depicts" class="section" about="[ci:depicts]"
typeof="owl:ObjectProperty">

#### `depicts`

The document explicitly depicts this concept (or other entity).

This term is identical in meaning to `foaf:depicts` except that the
latter constrains its domain to images only, whereas this can relate any
kind of document. The range of this property is also left open, to
accommodate any kind of resource being depicted.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Sub-property of:  
<a href="http://purl.org/dc/terms/references"
rel="rdfs:subPropertyOf"><code>dct:references</code></a>

See also:  
<a href="http://xmlns.com/foaf/spec/#term_depicts" rel="rdfs:seeAlso"
resource="foaf:depicts"><code>foaf:depicts</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="introduces" class="section" about="[ci:introduces]"
typeof="owl:ObjectProperty">

#### `introduces`

The document defines, describes, or otherwise introduces the audience to
this concept.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Range:  
<a href="https://www.w3.org/TR/skos-reference/#concepts"
rel="rdfs:range"
resource="http://www.w3.org/2004/02/skos/core#Concept"><code>skos:Concept</code></a>

Sub-property of:  
<a
href="https://vocab.methodandstructure.com/content-inventory#mentions"
rel="rdfs:subPropertyOf"><code>ci:mentions</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="assumes" class="section" about="[ci:assumes]"
typeof="owl:ObjectProperty">

#### `assumes`

The document assumes the audience is familiar with this concept, and may
not mention it explicitly.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Range:  
<a href="https://www.w3.org/TR/skos-reference/#concepts"
rel="rdfs:range"
resource="http://www.w3.org/2004/02/skos/core#Concept"><code>skos:Concept</code></a>

Sub-property of:  
<a href="http://purl.org/dc/terms/references"
rel="rdfs:subPropertyOf"><code>dct:references</code></a>

See also:  
<a
href="http://dublincore.org/documents/dcmi-terms/#terms-educationLevel"
rel="rdfs:seeAlso"
resource="http://purl.org/dc/terms/educationLevel"><code>dct:educationLevel</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="evokes" class="section" about="[ci:evokes]"
typeof="owl:ObjectProperty">

#### `evokes`

The document evokes the given concept without mentioning it explicitly.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Range:  
<a href="https://www.w3.org/TR/skos-reference/#concepts"
rel="rdfs:range"
resource="http://www.w3.org/2004/02/skos/core#Concept"><code>skos:Concept</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/content-inventory#assumes"
rel="rdfs:subPropertyOf"><code>ci:assumes</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Audience Properties

On the other side of the relationships between documents and concepts,
are the relationships between *audiences* and concepts. In order to get
any use out of a document, it is safe to assume a person has to
*understand* it, which they won't if the document deals with concepts
the person doesn't understand, unless the document specifically contains
content explaining those concepts. Conversely, a person may understand a
concept all too well, and have an opinion about it, which will entice
them to either *seek out* or *avoid* documents that deal with those
concepts. These properties are intended to model both the audience's
grasp of, and emotional valence toward, a given concept.

Intersecting the concept relations declared on the documents in our
inventory with the following properties declared on our audiences will
enable us to construct appropriate pairings of content to audiences,
and/or root out gaps in our assumptions about both our content *and* our
audiences.

    @prefix bibo: <http://purl.org/ontology/bibo/> .
    @prefix dct:  <http://purl.org/dc/terms/> .
    @prefix ci:   <https://vocab.methodandstructure.com/content-inventory#> .
    @prefix dbc:  <https://dbpedia.org/page/Category:> .

    <https://example.news/2020/01/gruesome-car-accident> a bibo:Article ;
    dct:title "Gruesome Car Accident Gruesomely Kills 42" ;
    ci:depicts dbc:Traffic_collisions, dbc:Road_incident_deaths .

    # we could define the following audience:

    <https://example.news/audience/squeamish-person> a ci:Audience ;
    ci:eschews dbc:Accidents, dbc:Injuries, dbc:Death, dbc:Violence .

    # over at DBPedia, there is the following relation:

    dbc:Traffic_collisions skos:broader dbc:Accidents .

    # that statement is enough to match the audience, but this chain
    # would match it too:

    dbc:Road_incident_deaths skos:broader dbc:Deaths_by_cause .
    dbc:Deaths_by_cause skos:broader dbc:Causes_of_death .
    dbc:Causes_of_death skos:broader dbc:Death .

    # from this we can reason (programmatically) that the article is not
    # appropriate for the given audience and append the following statement
    # to the article's metadata:

    <https://example.news/2020/01/gruesome-car-accident>
    ci:non-audience <https://example.news/audience/squeamish-person> .

References to DBPedia concepts have been linked to demonstrate that
concepts can also be rendered as Web pages, as well as cross domains.

<div id="aware-of" class="section" about="[ci:aware-of]"
typeof="owl:ObjectProperty">

#### `aware-of`

This property relates an Audience to a SKOS concept that is likely to be
in the orbit of the audience's members: they are *aware* that the
concept *exists*, although they may not necessarily *understand* it.

Domain:  
<a
href="https://vocab.methodandstructure.com/content-inventory#Audience"
rel="rdfs:domain"><code>ci:Audience</code></a>

Range:  
<a href="https://www.w3.org/TR/skos-reference/#concepts"
rel="rdfs:range"
resource="http://www.w3.org/2004/02/skos/core#Concept"><code>skos:Concept</code></a>

Sub-property of:  
<a href="https://www.w3.org/TR/skos-reference/#semantic-relations"
rel="rdfs:subPropertyOf"
resource="http://www.w3.org/2004/02/skos/core#related"><code>skos:related</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="understands" class="section" about="[ci:understands]"
typeof="owl:ObjectProperty">

#### `understands`

This property relates an Audience to a SKOS concept that members of the
audience are known to comprehend, and thereby do not need any additional
explanation.

Domain:  
<a
href="https://vocab.methodandstructure.com/content-inventory#Audience"
rel="rdfs:domain"><code>ci:Audience</code></a>

Range:  
<a href="https://www.w3.org/TR/skos-reference/#concepts"
rel="rdfs:range"
resource="http://www.w3.org/2004/02/skos/core#Concept"><code>skos:Concept</code></a>

Sub-property of:  
<a
href="https://vocab.methodandstructure.com/content-inventory#aware-of"
rel="rdfs:subPropertyOf"><code>ci:aware-of</code></a>

See also:  
<a
href="http://dublincore.org/documents/dcmi-terms/#terms-educationLevel"
rel="rdfs:seeAlso"
resource="http://purl.org/dc/terms/educationLevel"><code>dct:educationLevel</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="values" class="section" about="[ci:values]"
typeof="owl:ObjectProperty">

#### `values`

This property relates an Audience to a SKOS concept that members of the
audience are known to *value*, that is, to find meaningful in an
axiological sense.

Domain:  
<a
href="https://vocab.methodandstructure.com/content-inventory#Audience"
rel="rdfs:domain"><code>ci:Audience</code></a>

Range:  
<a href="https://www.w3.org/TR/skos-reference/#concepts"
rel="rdfs:range"
resource="http://www.w3.org/2004/02/skos/core#Concept"><code>skos:Concept</code></a>

Sub-property of:  
<a href="https://www.w3.org/TR/skos-reference/#semantic-relations"
rel="rdfs:subPropertyOf"
resource="http://www.w3.org/2004/02/skos/core#related"><code>skos:related</code></a>

See also:  
<a href="https://vocab.methodandstructure.com/content-inventory#eschews"
rel="rdfs:seeAlso"><code>ci:eschews</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="eschews" class="section" about="[ci:eschews]"
typeof="owl:ObjectProperty">

#### `eschews`

This property relates an Audience to a SKOS concept that members of the
audience are known to actively avoid or regard with contempt. This
relation is intended to represent the complement of *values*.

Domain:  
<a
href="https://vocab.methodandstructure.com/content-inventory#Audience"
rel="rdfs:domain"><code>ci:Audience</code></a>

Range:  
<a href="https://www.w3.org/TR/skos-reference/#concepts"
rel="rdfs:range"
resource="http://www.w3.org/2004/02/skos/core#Concept"><code>skos:Concept</code></a>

Sub-property of:  
<a href="https://www.w3.org/TR/skos-reference/#semantic-relations"
rel="rdfs:subPropertyOf"
resource="http://www.w3.org/2004/02/skos/core#related"><code>skos:related</code></a>

See also:  
<a href="https://vocab.methodandstructure.com/content-inventory#values"
rel="rdfs:seeAlso"><code>ci:values</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="exemplar" class="section" about="[ci:exemplar]"
typeof="owl:ObjectProperty">

#### `exemplar`

This property relates an `Audience` to a specific `foaf:Person` who is
an exemplar of the audience.

Domain:  
<a
href="https://vocab.methodandstructure.com/content-inventory#Audience"
rel="rdfs:domain"><code>ci:Audience</code></a>

Range:  
<a href="http://xmlns.com/foaf/0.1/#term_Person" rel="rdfs:range"
resource="foaf:Person"><code>foaf:Person</code></a>

Sub-property of:  
<a href="https://www.w3.org/TR/skos-reference/#notes"
rel="rdfs:subPropertyOf"
resource="http://www.w3.org/2004/02/skos/core#example"><code>skos:example</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Content Management Metadata

One of the details we want in a content inventory is the set of
hyperlinks going out of a document, including whether or not the user
can see them, and what kind of links they are. These next few terms
extend Dublin Core with that additional information.

Note that words like “visible” and “see” are proxies for saying
something like “amenable to non-specific perception and/or interaction
by the user”. The essential information to capture with these properties
is whether the hyperlink is on the user-facing canvas, or hidden away in
the document's metadata.

Note as well that these properties are intended to capture relations
between documents read naïvely as hypermedia, *not* as embedded metadata
such as Microdata or RDFa. Indeed, in RDFa, a construct like
`<a rel="some:relation" resource="some:object" href="/some/page">…`
would yield the contents of `resource=` whereas these properties (in
this example, `ci:link`) are meant to capture the contents of `href=`
(or `src=`, `action=`, etc.).

    @prefix ci: <https://vocab.methodandstructure.com/content-inventory#> .

    # This statement relates a resource to its canonical address:

    <https://example.club/seventeen-mindblowing-ways-to-write-listicles>
    ci:canonical <https://example.club/17-mindblowing-ways-to-write-listicles> .

    # here we define a slug and aliases:

    <https://example.club/17-mindblowing-ways-to-write-listicles>
    ci:canonical-slug "17-mindblowing-ways-to-write-listicles"^^xsd:token ;
    ci:alias <https://example.club/seventeen-mindblowing-ways-to-write-listicles>,
    <https://short.nr/aXbQ1> .

    # one of these alias clauses is implied by the other statement, as
    # ci:canonical is a subproperty of ci:alias-for, which is the inverse
    # of ci:alias.

<div id="embed" class="section" about="[ci:embed]"
typeof="owl:ObjectProperty">

#### `embed`

This property specifies an embedded resource, such as an image, which is
visible on the document's canvas.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Sub-property of:  
<a href="http://purl.org/dc/terms/hasPart"
rel="rdfs:subPropertyOf"><code>dct:hasPart</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="form" class="section" about="[ci:form]"
typeof="owl:ObjectProperty">

#### `form`

This property specifies form target, which may or may not be visible to
the user.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/content-inventory#link"
rel="rdfs:subPropertyOf"><code>ci:link</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="include" class="section" about="[ci:include]"
typeof="owl:ObjectProperty">

#### `include`

This property specifies a related resource which is *not* directly
visible to the user.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Sub-property of:  
<a href="http://purl.org/dc/terms/requires"
rel="rdfs:subPropertyOf"><code>dct:requires</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="link" class="section" about="[ci:link]"
typeof="owl:ObjectProperty">

#### `link`

This property specifies an ordinary hyperlink, which is visible on the
document's canvas.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:domain"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

Sub-property of:  
<a href="http://purl.org/dc/terms/references"
rel="rdfs:subPropertyOf"><code>dct:references</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

Resources on the Web tend to be identified by more than one URI. The
following properties extend the `owl:sameAs` property to indicate a
definite direction of canonicality, and throw in another couple of
properties to capture the same idea for the terminal “slug” of the URI
path, i.e., `/this/thing/here`. An example use case for these properties
is the generation of <span class="dfn">rewrite maps</span>.

<div id="alias" class="section" about="[ci:alias]"
typeof="owl:ObjectProperty">

#### `alias`

Denotes an alternate URI for the subject resource. It extends
`owl:sameAs` insofar as asserting that the object is somehow “less
canonical” than the subject.

Sub-property of:  
<a href="http://www.w3.org/2002/07/owl#sameAs"
rel="rdfs:subPropertyOf"><code>owl:sameAs</code></a>

Inverse of:  
<a
href="https://vocab.methodandstructure.com/content-inventory#alias-for"
rel="owl:inverseOf"><code>ci:alias-for</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="alias-for" class="section" about="[ci:alias-for]"
typeof="owl:ObjectProperty">

#### `alias-for`

Denotes that the *subject* is the alias URI, and the object is “more
canonical” (though not necessarily the *most* canonical).

Sub-property of:  
<a href="http://www.w3.org/2002/07/owl#sameAs"
rel="rdfs:subPropertyOf"><code>owl:sameAs</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/content-inventory#alias"
rel="owl:inverseOf"><code>ci:alias</code></a>

See also:  
<a
href="https://vocab.methodandstructure.com/content-inventory#canonical"
rel="rdfs:seeAlso"><code>ci:canonical</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="representation" class="section" about="[ci:representation]"
typeof="owl:ObjectProperty">

#### `representation`

Denotes a resource that is a concrete representation of the subject,
which assumed to be more abstract.

This property is deprecated in favour of
[ci:variant](https://vocab.methodandstructure.com/content-inventory#variant).

Sub-property of:  
<a
href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/hasFormat"
rel="rdfs:subPropertyOf"
resource="dct:hasFormat"><code>dct:hasFormat</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="variant" class="section" about="[ci:variant]"
typeof="owl:ObjectProperty">

#### `variant`

Denotes a resource that is a variant of a concrete representation of the
subject, which assumed to be more abstract.

Sub-property of:  
<a
href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/hasFormat"
rel="rdfs:subPropertyOf"
resource="dct:hasFormat"><code>dct:hasFormat</code></a>

Equivalent to:  
<a
href="https://vocab.methodandstructure.com/content-inventory#representation"
rel="owl:equivalentProperty"><code>ci:representation</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="primary" class="section" about="[ci:primary]"
typeof="owl:ObjectProperty owl:FunctionalProperty">

#### `primary`

Denotes the *primary* variant that concretely represents the resource.

Sub-property of:  
<a href="https://vocab.methodandstructure.com/content-inventory#variant"
rel="rdfs:subPropertyOf"><code>ci:variant</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="canonical" class="section" about="[ci:canonical]"
typeof="owl:ObjectProperty owl:FunctionalProperty">

#### `canonical`

Asserts the canonical URI of the subject resource, i.e., the one you
always want to publish in content or redirect Web requests to.

Sub-property of:  
<a
href="https://vocab.methodandstructure.com/content-inventory#alias-for"
rel="rdfs:subPropertyOf"><code>ci:alias-for</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="slug" class="section" about="[ci:slug]"
typeof="owl:DatatypeProperty">

#### `slug`

The slug is a text token which represents either the full path or
terminal path segment of an HTTP(S) URL by which a resource can be
located. This property is mainly for the purpose of archiving old or
alternative URL paths in a content inventory, for such tasks as
generating URL rewriting maps.

Sub-property of:  
<a
href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/identifier"
rel="rdfs:subPropertyOf"
resource="dct:identifier"><code>dct:identifier</code></a>

Range:  
<a href="http://www.w3.org/2001/XMLSchema#string"
rel="rdfs:range"><code>xsd:string</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="canonical-slug" class="section" about="[ci:canonical-slug]"
typeof="owl:DatatypeProperty owl:FunctionalProperty">

#### `canonical-slug`

This is the canonical slug associated with the resource, and should be
populated with the slug which is actually in use.

Sub-property of:  
<a href="https://vocab.methodandstructure.com/content-inventory#slug"
rel="rdfs:subPropertyOf"><code>ci:slug</code></a>

Range:  
<a href="http://www.w3.org/2001/XMLSchema#string"
rel="rdfs:range"><code>xsd:string</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="fragment-of" class="section" about="[ci:fragment-of]"
typeof="owl:ObjectProperty owl:FunctionalProperty">

#### `fragment-of`

This property asserts that the subject should be treated as a fragment
of the document it relates to.

Range:  
<a href="http://xmlns.com/foaf/spec/#term_Document" rel="rdfs:range"
resource="http://xmlns.com/foaf/0.1/Document"><code>foaf:Document</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="indexed" class="section" about="[ci:indexed]"
typeof="owl:DatatypeProperty owl:FunctionalProperty">

#### `indexed`

This is a boolean value to indicate whether or not a resource ought to
be indexed. It does not necessarily ascribe a policy: an absence of an
explicit *true* value does not necessarily imply the resource ought not
be indexed, but the *presence* of a *false* value probably should.

Range:  
<a href="http://www.w3.org/2001/XMLSchema#boolean"
rel="rdfs:range"><code>xsd:boolean</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

</div>

<div id="sec-individuals" class="section" about="#">

## Individuals

This document defines a set of values useful for describing the status
of documents and actions to take with them.

<div class="section">

### Statuses

The following bibo:DocumentStatuses are supplied in addition to the
statuses specified by the Bibliography Ontology.

<div id="empty" class="section" about="[ci:empty]"
typeof="bibo:DocumentStatus">

#### `empty`

The document contains no content.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="incomplete" class="section" about="[ci:incomplete]"
typeof="bibo:DocumentStatus">

#### `incomplete`

The document has been started, but is clearly not finished.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="incorrect" class="section" about="[ci:incorrect]"
typeof="bibo:DocumentStatus">

#### `incorrect`

The content of this document is factually wrong.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="obsolete" class="section" about="[ci:obsolete]"
typeof="bibo:DocumentStatus">

#### `obsolete`

The content of this document was correct and relevant at one point, but
external circumstances have caused it to lapse in relevance or factual
accuracy.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="landing" class="section" about="[ci:landing]"
typeof="bibo:DocumentStatus">

#### `landing`

The resource is a landing page from some other medium (e.g. e-mail,
television, billboard). This status is a hint to automated systems which
would otherwise orphan or retire a landing page with no inbound links.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="orphan" class="section" about="[ci:orphan]"
typeof="bibo:DocumentStatus">

#### `orphan`

The resource is not explicitly pending or removed from publication,
however it has managed to be disconnected from the rest of the site:
There is no path to it from a landing page, and it is not a landing page
on its own. That is to say that the resource either has no inbound
links, or if it does, those links are from other resources that are in
the same situation. Documents which are only linked from retired
documents are also considered orphans.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="confidential" class="section" about="[ci:confidential]"
typeof="bibo:DocumentStatus">

#### `confidential`

The document is confidential and not for publication.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="circulated" class="section" about="[ci:circulated]"
typeof="bibo:DocumentStatus">

#### `circulated`

The document is available for select people to see, but not “published”
in the strict literal sense.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="retired" class="section" about="[ci:retired]"
typeof="bibo:DocumentStatus">

#### `retired`

The document has been explicitly retired by an editor or curator, but
still exists in the archive.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="unavailable" class="section" about="[ci:unavailable]"
typeof="bibo:DocumentStatus">

#### `unavailable`

The resource at the subject address is unavailable for reasons other
than explicit retirement, e.g. HTTP 404 or 403, or going out of print.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div id="sec-actions" class="section">

### Actions

The following is a list of
[`ci:Action`](https://vocab.methodandstructure.com/content-inventory#Action)
entities to be used with the
[`ci:action`](https://vocab.methodandstructure.com/content-inventory#action)
property.

<div id="keep" class="section" about="[ci:keep]" typeof="ci:Action">

#### `keep`

Keep this document to which this is associated; make no changes to it at
this time.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="split" class="section" about="[ci:split]" typeof="ci:Action">

#### `split`

Split this document into multiple pieces.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="tentative-merge" class="section" about="[ci:tentative-merge]"
typeof="ci:Merge">

#### `tentative-merge`

Merge this document into some other document, though unspecified at this
time as to which.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="update-metadata" class="section" about="[ci:update-metadata]"
typeof="ci:Action">

#### `update-metadata`

Update the metadata of this document, such as keywords, audience, etc.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="proofread" class="section" about="[ci:proofread]"
typeof="ci:Action">

#### `proofread`

Proofread this document.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="revise" class="section" about="[ci:revise]" typeof="ci:Action">

#### `revise`

Revise or restructure this document.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="rewrite" class="section" about="[ci:rewrite]"
typeof="ci:Action">

#### `rewrite`

Rewrite this document from scratch.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="retire" class="section" about="[ci:retire]" typeof="ci:Action">

#### `retire`

Remove all references to this document and consign it to the archive.

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

</div>

<div id="#sec-dsd" class="section" about="#">

## Quantitative Metrics

There are many ways to measure a set of Web pages that give valuable
insight into not only the individual character of each page, but also
the character of an entire site.

We use the
<a href="http://www.w3.org/TR/vocab-data-cube/" rel="dct:references">RDF
Data Cube vocabulary</a> to specify the quantitative metrics we gather
over our documents.

<div class="section">

### Data Structure Definitions

The following object is an instance of <a
href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_DataStructureDefinition"
rel="dct:references"><code>qb:DataStructureDefinition</code></a>. It
depicts the dimensions, measures and attributes for
<a href="http://www.w3.org/TR/vocab-data-cube/#ref_qb_DataSet"
rel="dct:references"><code>qb:DataSet</code>s</a> that carry the
relevant statistical data. (This particular data structure only contains
dimensions and measures.)

<div id="words-and-blocks" class="section" about="[ci:words-and-blocks]"
typeof="qb:DataStructureDefinition">

#### `words-and-blocks`

A set of descriptive statistics pertaining to the number of words per
block of text in a given document.

<div class="section" rel="qb:component">

##### Components

<div class="section">

###### Dimensions

-   <a
    href="https://vocab.methodandstructure.com/content-inventory#document"
    rel="qb:dimension"><code>document</code></a>

</div>

<div class="section">

###### Counts

-   <a
    href="https://vocab.methodandstructure.com/content-inventory#sections"
    rel="qb:measure"><code>sections</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#blocks"
    rel="qb:measure"><code>blocks</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#words"
    rel="qb:measure"><code>words</code></a>
-   <a
    href="https://vocab.methodandstructure.com/content-inventory#characters"
    rel="qb:measure"><code>characters</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#images"
    rel="qb:measure"><code>images</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#videos"
    rel="qb:measure"><code>videos</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#embeds"
    rel="qb:measure"><code>embeds</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#tables"
    rel="qb:measure"><code>tables</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#forms"
    rel="qb:measure"><code>forms</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#scripts"
    rel="qb:measure"><code>scripts</code></a>
-   <a
    href="https://vocab.methodandstructure.com/content-inventory#stylesheets"
    rel="qb:measure"><code>stylesheets</code></a>

</div>

<div class="section">

###### Five-number summary

-   <a href="https://vocab.methodandstructure.com/content-inventory#min"
    rel="qb:measure"><code>min</code></a>
-   <a
    href="https://vocab.methodandstructure.com/content-inventory#low-quartile"
    rel="qb:measure"><code>low-quartile</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#median"
    rel="qb:measure"><code>median</code></a>
-   <a
    href="https://vocab.methodandstructure.com/content-inventory#high-quartile"
    rel="qb:measure"><code>high-quartile</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#max"
    rel="qb:measure"><code>max</code></a>

</div>

<div class="section">

###### Mean and Standard Deviation

-   <a href="https://vocab.methodandstructure.com/content-inventory#mean"
    rel="qb:measure"><code>mean</code></a>
-   <a href="https://vocab.methodandstructure.com/content-inventory#sd"
    rel="qb:measure"><code>sd</code></a>

</div>

</div>

</div>

</div>

<div class="section">

### Dimensions

The set of all <a
href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_DimensionProperty"
rel="dct:references">qb:DimensionProperties</a> for a given data
structure can positively identify an observation. We currently only
specify one dimension, the URI of the document in question.

<div id="document" class="section" about="[ci:document]"
typeof="qb:DimensionProperty">

#### `document`

Document Reference

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://xmlns.com/foaf/0.1/Document"
rel="rdfs:range"><code>foaf:Document</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

The
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_MeasureProperty"
rel="dct:references">qb:MeasureProperties</a> are what define the data
observed in a
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="dct:references">qb:Observation</a>. Here we are interested in a
<a href="http://en.wikipedia.org/wiki/Five-number_summary"
rel="dct:references">five-number summary</a>, along with the
<a href="http://en.wikipedia.org/wiki/Mean"
rel="dct:references">mean</a> and
<a href="http://en.wikipedia.org/wiki/Standard_deviation"
rel="dct:references">standard deviation</a> of block sizes (in words)
found in a given document.

### Measures

<div id="sections" class="section" about="[ci:sections]"
typeof="qb:MeasureProperty">

#### `sections`

For document types that have a concrete representation of sections, this
property may be used to capture their sum.

Domain:  
<a href="http://xmlns.com/foaf/0.1/Document"
rel="rdfs:domain"><code>foaf:Document</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="blocks" class="section" about="[ci:blocks]"
typeof="qb:MeasureProperty">

#### `blocks`

A block count is conceptually similar to a word or section count, though
it counts the total of elements in the document considered to be text
blocks, such as paragraphs, tables, lists and figures. It is suited for
document types that have no concept of (semantic) sections, such as
HTML. The purpose of this measurement is to provide a sort of ratio to
the word count, to glean how well-proportioned the document is.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="words" class="section" about="[ci:words]"
typeof="qb:MeasureProperty">

#### `words`

This indicates the number of words in a document, similar to the
familiar function in a word processor. The exact method of counting
words may vary by document type, language etc., and is thus out of scope
from this document.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="characters" class="section" about="[ci:characters]"
typeof="qb:MeasureProperty">

#### `characters`

This indicates the number of characters in a document, with punctuation
and the XPath normalize-space function applied. Note this is characters,
not bytes.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

See also:  
<a href="http://www.w3.org/TR/xpath/#function-normalize-space"
rel="rdfs:seeAlso"><samp>normalize-space</samp> in the XPath 1.0
specification</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="images" class="section" about="[ci:images]"
typeof="qb:MeasureProperty">

#### `images`

This indicates the number of images in the document.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="videos" class="section" about="[ci:videos]"
typeof="qb:MeasureProperty">

#### `videos`

The number of videos in the document.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="embeds" class="section" about="[ci:embeds]"
typeof="qb:MeasureProperty">

#### `embeds`

The number of embeds in the document.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="tables" class="section" about="[ci:tables]"
typeof="qb:MeasureProperty">

#### `tables`

The number of tables in the document.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="lists" class="section" about="[ci:lists]"
typeof="qb:MeasureProperty">

#### `lists`

The number of lists in the document.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="forms" class="section" about="[ci:forms]"
typeof="qb:MeasureProperty">

#### `forms`

The number of forms in the document.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="scripts" class="section" about="[ci:scripts]"
typeof="qb:MeasureProperty">

#### `scripts`

The number of scripts in the document.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="stylesheets" class="section" about="[ci:stylesheets]"
typeof="qb:MeasureProperty">

#### `stylesheets`

The number of stylesheets in the document.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="outdegree" class="section" about="[ci:outdegree]"
typeof="qb:MeasureProperty">

#### `outdegree`

The number of links emanating from the specified resource.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#number" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#number"><code>xsd:number</code></a>

See also:  
<a
href="http://en.wikipedia.org/wiki/Directed_graph#Indegree_and_outdegree"
rel="rdfs:seeAlso">Directed graph (Wikipedia)</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="indegree" class="section" about="[ci:indegree]"
typeof="qb:MeasureProperty">

#### `indegree`

The number of links pointing at the specified resource.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#number" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#number"><code>xsd:number</code></a>

See also:  
<a
href="http://en.wikipedia.org/wiki/Directed_graph#Indegree_and_outdegree"
rel="rdfs:seeAlso">Directed graph (Wikipedia)</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="min" class="section" about="[ci:min]"
typeof="qb:MeasureProperty">

#### `min`

The smallest observation in the sample.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#number" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#number"><code>xsd:number</code></a>

See also:  
<a href="http://en.wikipedia.org/wiki/Sample_minimum"
rel="rdfs:seeAlso">Sample minimum (Wikipedia)</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="low-quartile" class="section" about="[ci:low-quartile]"
typeof="qb:MeasureProperty">

#### `low-quartile`

Equivalent to the bottom quarter, or 25th percentile, of the observed
data.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#number" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#number"><code>xsd:number</code></a>

See also:  
<a href="http://en.wikipedia.org/wiki/Quartile"
rel="rdfs:seeAlso">Quartile (Wikipedia)</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="median" class="section" about="[ci:median]"
typeof="qb:MeasureProperty">

#### `median`

The median of a population

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#number" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#number"><code>xsd:number</code></a>

See also:  
<a href="http://en.wikipedia.org/wiki/Median" rel="rdfs:seeAlso">Median
(Wikipedia)</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="high-quartile" class="section" about="[ci:high-quartile]"
typeof="qb:MeasureProperty">

#### `high-quartile`

Third Quartile

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#number" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#number"><code>xsd:number</code></a>

See also:  
<a href="http://en.wikipedia.org/wiki/Quartile"
rel="rdfs:seeAlso">Quartile (Wikipedia)</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="max" class="section" about="[ci:max]"
typeof="qb:MeasureProperty">

#### `max`

Maximum

Domain  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#number" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#number"><code>xsd:number</code></a>

See also:  
<a href="http://en.wikipedia.org/wiki/Sample_maximum"
rel="rdfs:seeAlso">Sample maximum (Wikipedia)</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="mean" class="section" about="[ci:mean]"
typeof="qb:MeasureProperty">

#### `mean`

Mean

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#number" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#number"><code>xsd:number</code></a>

See also:  
<a href="http://en.wikipedia.org/wiki/Mean" rel="rdfs:seeAlso">Mean
(Wikipedia)</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="sd" class="section" about="[ci:sd]"
typeof="qb:MeasureProperty">

#### `sd`

Standard Deviation

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="http://purl.org/linked-data/cube#Observation"><code>qb:Observation</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#number" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#number"><code>xsd:number</code></a>

See also:  
<a href="http://en.wikipedia.org/wiki/Standard_deviation"
rel="rdfs:seeAlso">Standard deviation (Wikipedia)</a>

<a href="https://vocab.methodandstructure.com/content-inventory#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

</div>

<div class="section" about="#">

Changes  
January 23, 2012

December 11, 2012

February 6, 2014

February 8, 2015

April 6, 2017

October 6, 2018

March 5, 2019

April 7, 2019

April 17, 2019

July 7, 2019

July 10, 2019

July 21, 2019

September 4, 2019

January 25, 2020

April 24, 2020

April 29, 2020

June 28, 2020

July 3, 2020

November 12, 2020

May 17, 2021

October 5, 2022

November 2, 2022

This document is copyright 2010-2022
<a href="https://doriantaylor.com/person/dorian-taylor#me"
rel="dct:creator">Dorian Taylor</a>, available under a
<a href="http://creativecommons.org/licenses/by/2.5/ca/"
rel="license">Creative Commons Attribution 2.5 Canada</a> license, where
<span class="dfn">attribution</span> is defined as a link
[here](https://vocab.methodandstructure.com/content-inventory#).

</div>
