# Designing Data Intensive Applications
## Chap1
### Reliability
Prevent faults from causing failures. 
* Fault - one component fails / failure - the whole system fails.
* Handle faults delibrately
#### Hardware Faults
Add redundancy, add software techniques to tolerate the loss of then entire machines. 
#### Software Errors
#### Human Errors
Design well, provide sandbox, test, provide quick recovery, monitoring
### Scalabilty
Can system cope with the increased load?
#### Twitter
1. Fetch tweet when a user tries to read the updated tweet - low write cost, high read cost
2. Insert new tweet when it’s created - high write cost, low read cost -> better than 1 since write < read. 
3. For celebrities use 1, others, use 2
#### Describing performance
Response time
- Use percentiles instead of average - shows how users typically have to wait.
- SLO(Service Level Objectives), SLA(Service Level Agreements)
#### Approaches for Coping with Load
Mixture of scale-up, scale-out
- stateless services to scale-out / stateful services like DBs to scale-up
### Maintainability
#### Operability: Making Life Easy for Operations
Make it easy for operations teams to keep the system running smoothly.
#### Simplicity: Managing Complexity
Make it easy to understand the system. Eg. abstractions
#### Evolvability: Making Change Easy
Agile techniques helpful. TDD refactoring

## Chap2: Data Models and Query Languages
### The Object-Relational Mismatch
Impedance mismatch
### One-to-many relationships
 representations
1. Fully normalized SQL[[
2. Support multi-valued data type
3. Store XML, JSON to text field
### Many-to-One and Many-to-Many Relationships
Eg. Storing region info / Industry info / company / school / recommender
Representation
- Join needed if the data is normalized
### The debate between the network model and the relational model
#### The Network Model
A record has =multi-parents, implemented like pointers.
Querying and updating the db was difficult, since the access path had to be tracked.
#### The Relational Model
Insert and update easily. The access path optimized automatically by the query optimizer
### Relational Versus Document Databases Today
#### Which data model leads to simpler application code?
a tree of one-to- many relationships -> document db
many-to-many relationships used; joins -> relational db
#### Schema flexibility in the document model
Document db: Schema-on-read -  similar to dynamic (runtime) type -> great if items do not have the same schema
Relational db: Schema-on-write - similar to static (compile-time) type
#### Data locality for queries
Document db - advantages when retrieving large parts of the document at the same time. 
Relational db also offer locality
### Query Languages for Data
Imperative language: commands how to get the result.
Declarative language: specifies only the data you want. (SQL or relational algebra)
- concise
- Implementation is hidden ->  how data is stored do not matter, automatic optimization, parallel execution 
#### MapReduce Querying
Mix of imperative lang and declarative lang
### Graph-Like Data Models
Good for complex many-to-many relationships.
Can also store different types of data structures in a single datastore.
#### Property Graphs
#### The Cypher Query Language
declarative query language.
Example: (person) -[:BORN_IN]-> () -[:WITHIN*0..]-> (location)
#### Graph Queries in SQL
If Relational db is used or the graph data, the joins need to be decided in advance. 
Still, the recursive common table expression of relational db can be utilized with much more queries.
##### Triple-Stores and SPARQL
Forms of three parts - subject, predicate, object.
Example
- predicate is an edge, object is a vertex -> _:idaho :within _:usa 
- predicate is a property, the object is a string literal ->  _:usa :name "United States"
##### The SPARQL query language
query language for triple-stores using the RDF data model.
Example: ?person :bornIn / :within* ?location.
### The Foundation: Datalog
similar to the triple-store model - predicate(subject, object)
 rules can be combined and reused in different queries
