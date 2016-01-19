
## Differences among FM formats

### Feature-IDE

[Feature IDE](http://wwwiti.cs.uni-magdeburg.de/iti_db/research/featureide/) uses an XML-based file format to store feature models.
Although some version of the plugin included an XML schema, currently the file format is not defined by any schema.

  * Feature Models structure and constraints are defined as XML entities
  * Feature models do not have a name.
  * Feature Groups are represented with a Feature. A Feature cannot have two feature groups. Instead, it must have two children features, each one representing a Feature Groups.
  * Features must have a name.
  * Features may be *And*, *Alt* or *Or* Features, i.e., supported Feature Groups are *Alternative* and *Or* groups.  
  * Constraints can include AND, OR, NOT, IMPLIES and EQ operators.
  * Constraints do not have a name or an id.

### Splot (SXFM)

[SXFM](http://www.splot-research.org/sxfm.html) (Simple XML Feature Model Format) is the file format used by [SPLOT](http://www.splot-research.org/). Although SXFM is an XML-based file format for Feature Models, the tree structure and the constraints are written as a text inside some XML entities. It is necessary to use a parser to get the tree structure and the constraints.

  * Feature model must have a name and may include a set of meta-data.
  * Features, Feature Groups may have an optional name and a mandatory ID. 
  * Models created using SPLOT do not include a name for the Feature Groups.
  * Although the format allow feature groups with cardinality, the only types of groups supported are *Alternative* and *Or* groups.
  * Each constraint has an ID. The SPLOT editor regenerates this ID each time the file is stored.
  * In SXFM, all the constraints are CNF-constraints, i.e., they only includes OR and NOT operators.
  * In the constraints, features are referenced using their ID (instead of their names) 
  * To store a SXFM model in SPLOT, the model must include some meta-data()

### FAMA (FML)

[FaMa](http://www.isa.us.es/fama/) is a framework for analysis of feature models. It supports a propietary XML-based file format for feature models. 

  * In contrast to Feature-IDE and SXFM, FML uses Features and Feature Relationships.
  * Each feature and each relationship has a different name.
  * It support feature groups with cardinaliy. However, many FAMA reasoners only supports *Alternative* and *Or* groups.
  * It supports constraints defined as excludes and requires relationships.
  