---
title: Document Store
draft: false
tags:
  - databases
  - nosql
---
A document store is a type of [[NoSQL]] DB that stores data within documents. Documents come in formats such as XML, JSON or binary. Documents are self-contained i.e., each document holds all of the information about a particular object e.g., a customer document would hold all the relevant information in one place. This makes a document store typically [[Denormalization|denormalized]].

Document stores provide APIs or a query language to use to query the internal structure and content of the document.

## Document Store Structure

1. Documents are grouped into collections which are akin to tables. A collection of documents represent a set of entities e.g. customers.

 2. Documents can be tagged with keywords or labels. This allows for categorizing the documents based on their attributes/properties.

3. Documents contain metadata e.g., creation, access permissions, authorship.

4. In some implementations, documents could be organized into hierarchical structures (similar to file systems).

---

## Common Implementations

1. MongoDB
2. DynamoDB
3. CouchDB
