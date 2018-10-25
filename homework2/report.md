##  Homework 2
####  Sam Chami, Merci Magallanes, and John Scott


###  Chapter 9
3\.  Try to map the relational schema in Figure 6.14 [page 189] into an ER schema. This is part of a process known as _reverse engineering_, in which a conceptual schema is created for an existing implemented database. State any assumptions you make.

>  TODO

7\.  Is it possible to successfully map a binary M:N relationship type without requiring a new relation? Why or why not?

>  TODO


###  Chapter 10
3\.  Why is it important to design the schemas and applications in parallel?

>  TODO

4\.  Why is it important to use an implementation-independent data model during conceptual schema design? What models are used in current design tools? Why?

>  TODO

6\.  Consider an actual application of a database system of interest. [NOTE: this means pick one you are familiar with to use for this exercise.] Define the requirements of the different levels of users in terms of data needed, types of queries, and transactions to be processed.

>  TODO


###  Chapter 15
5\.  What is a functional dependency? What are the possible sources of the information that defines the functional dependencies that hold among the attributes of a relation schema?

>  TODO

9\.  What undesirable dependencies are avoided when a relation is in 2NF?

>  TODO

10\.  What undesirable dependencies are avoided when a relation is in 3NF?

>  TODO

13\.  What is a multivalued dependency? When does it arise?

>  TODO


###  Chapter 21
1\.  What is meant by the concurrent execution of database transactions in a multiuser system? Discuss why concurrency control is needed, and give informal examples.

>  TODO

6\.  Discuss the atomicity, durability, isolation, and consistency preservations properties of a database transaction.

>  TODO


###  Chapter 4
1\.  The four fundamental data constructs of Neo4j are [select one and describe each of the items in your selection]:
  1.  Table, record, field, and constraint
  >  TODO

  2.  Node, relationship, property, and schema
  >  TODO

  3.  Node, relationship, property, and label
  >  TODO

  4.  Document, relationship, property, and collection
  >  TODO

3\.  If you have a few entities in your dataset that have lots of relationships to other entities, then you can't use a graph database because of the dense node problem.
  1.  True – you will have to use a relational system
  >  TODO

  2.  True – but there is no alternative, so you will have to live with it
  >  TODO

  3.  False – you can still use a graph database but it will be painfully slow for all queries
  >  TODO

  4.  False – you can very effectively use a graph database, but you should take precautions, for example, applying a fan-out pattern to your data
  >  TODO
