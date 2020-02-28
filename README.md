This repository provides an example on how to make your interaction
data available through Global Biotic Interactions (GloBI,
http://globalbioticinteractions.org) using JSON-LD.

[![Build Status](https://travis-ci.org/globalbioticinteractions/jsonld-template-dataset.svg)](https://travis-ci.org/globalbioticinteractions/jsonld-template-dataset) [![DOI](https://zenodo.org/badge/32360002.svg)](https://zenodo.org/badge/latestdoi/32360002) [![GloBI](http://api.globalbioticinteractions.org/interaction.svg?accordingTo=globi:globalbioticinteractions/jsonld-template-dataset)](http://globalbioticinteractions.org/?accordingTo=globi:globalbioticinteractions/jsonld-template-dataset)


If you would like to instead make your data available through simple tab separated values (TSV) files, see [globalbioticinteractions/template-dataset](https://github.com/globalbioticinteractions/template-dataset) instead

If you have comments or questions please [open an issue](https://github.com/globalbioticinteractions/jsonld-template-dataset/issues/new).

## Share Your Interaction Data
If you want to share your own data through GloBI:

1. Fork this repository.
2. Edit your ```globi-dataset.jsonld``` to describe your data in a human readable.
3. Ensure that your README.rd contains a reference to ```http://globalbioticinteractions.org```. 
4. Edit the name of your repository and description to make it easy for others to understand what your data is about.

After you do this, the data will be available through GloBI within a day or so. Note that GloBI is uses [this sparql query](https://github.com/jhpoelen/eol-globi-data/blob/master/eol-globi-data-sources/src/main/resources/org/eol/globi/data/find-jsonld-interactions.rq) to extact information from the repository.

## Data Format

The file [globi-dataset.jsonld](./globi-dataset.jsonld) is a suggestion on how to encode your interaction data using [JSON-LD](http://jsonld.org). Both metadata about the dataset and interactions should be captured here. 

The document is in two parts: `nodes` describes the various instances of specimens, and `links` the connections between them.

## GloBI datasets JSON-LD context

The directory contains a JSON-LD context file called [context.jsonld](context.jsonld). It provides convenient short forms for namespaces, classes, individuals and properties in your jsonld dataset file. Note that if you want to modify this, you should also modify the URL at the top of your globi-dataset.jsonld file to point to your own github repo location.

The context file provides standard prefixes for many semweb vocabs, for example:

      "rdf" : "http://www.w3.org/1999/02/22-rdf-syntax-ns#",
      "void" : "http://rdfs.org/ns/void#",
      "rdfs" : "http://www.w3.org/2000/01/rdf-schema#",

In addition to many [bio-ontologies](http://obofoundry.org):

      "RO" : "http://purl.obolibrary.org/obo/RO_",
      "BCO" : "http://purl.obolibrary.org/obo/BCO_",
      "OBI" : "http://purl.obolibrary.org/obo/OBI_",
      "IAO" : "http://purl.obolibrary.org/obo/IAO_",
      "OBI" : "http://purl.obolibrary.org/obo/OBI_",
      "ENVO" : "http://purl.obolibrary.org/obo/ENVO_",

The complete URI for a property or class can also be specified, for example:

      "preys_on" : "RO:0002439",
      "specimen" : "OBI:0100051",

This means the globi-dataset.jsonld file can contain just the human-readable strings

i.e. either:

             "relation": {
                "id": "RO:0002439",
                "label": "preys on"
              },

or simple:

             "relation": "preys_on",


For more terms, please see [OBO Relations Ontology](https://code.google.com/p/obo-relations/).
 
interactionTypeId | interactionTypeName 
--- | ---
[RO:0002470](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002470) | eats
[RO:0002444](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002444) | parasite of
[RO:0002455](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002455) | pollinates
[RO:0002556](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002556) | pathogen of
