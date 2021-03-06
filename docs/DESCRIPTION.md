### Gene Ontology (GO)

http://geneontology.org/docs/download-ontology/#go_obo_and_owl

### RDF, N-triples format 
 - Gene Ontology (GO) data files are downloaded in RDF format . The download RDF file is then serialized and converted into n-triples format using rdflib in R. The n-triples data is parsed so that it can be stored in parquet data format. 
 - The n-triples format is tabular and follows the format```<subject> <predicate> <object>```. In addition, literals (text strings) are found in front of the object. These are incorporated into the parquet output data with three following column headers.  
	* Subject
	* Predicate
	* Object  (literals are included in the object column)

### GO ( Gene Ontology ) data 
```data/go.owl_ntriples.parquet```
Data represents Gene Ontology data. Consists of different classes and considers the Molecular Function, Cellular Component and the biological process. GO classes are composed of a definition, a label, a unique identifier, and several other elements.  [Elements of GO terms are described here](http://geneontology.org/docs/ontology/).

##### GO Documentation
Additional documentation on GO (Gene Ontology) data is provided herehttp://geneontology.org/docs/ontology-documentation/

### GO (Gene Ontology) plus data 
```data/go-plus.owl_ntriples.parquet```
The GO-Plus data set includes cross-ontology relationships (axioms) and imports additional required ontologies including [ChEBI](https://www.ebi.ac.uk/chebi/), [Cell Ontology](http://www.obofoundry.org/ontology/cl.html) and [Uberon](http://uberon.github.io/). It also includes a complete set of relationship types including some not in the ```data/go.owl_ntriples.parquet``` file . 

### GO Annotation data, GAF (GO Annotation Format) )
```data/goa_human_combined.parquet```
http://geneontology.org/docs/go-annotation-file-gaf-format-2.2/
GAF data has the following format and includes Human Genetic GO annotation info. 
|GO Annotation Column Headers  | 
|---|
|  DB|
|  DB Object ID|
|  DB Object Symbol|
|  Qualifier|
|  GO ID|
|  DB:Reference|
|  Evidence Code|
|  With or From|
|  Aspect|
|  DB Object Name|
|  DB Object Synonym|
|  DB Object Type|
|  DB Object Synonym|
|  Taxon|
|  Date|
|  Assigned By|
|  Annotation Extension|
|  Gene Product Form ID|

### GO CAMS data
```data/GO-CAMs.ttl.nt_ntriples.parquet```
https://s3.amazonaws.com/geneontology-public/gocam/GO-CAMs.ttl.zip
gocam documentation: http://geneontology.org/docs/gocam-overview/
GO CAMs annotation data is downloaded in RDF Turtle format. GO-CAM combines different GO annotations to produce a network of annotations ("model") to better understand biological function. The data is then serialized, processed and converted to parquet format. 
 
 ### GO External Data Links
 ```data/go_external_combined.parquet```
 http://current.geneontology.org/ontology/external2go/
 
 This dataset maps GO information to external databases based on IDs. Example databases that are mapped to GO terms include kegg, pfam and uniprot. This dataset includes the columns External database ID, GO description for the term, the corresponding GO ID, and a column containing the original file name. 
 
 **Columns**
 * ExternalID
 * GODescription 
 * GOID
 * filename