---
title: REST
draft: false
tags:
  - caching
---
REST is a way to design web services that makes it easy for clients and servers to communicate. It promotes a model where the client requests resources, and the server provides those resources or the means to manipulate them. Each resource is identified by a unique URL that acts like an address to the resource. Coupling between client and server is minimal compared to an [[Remote Procedure Call (RPC)]].


---

## Core Principles

1. **Statelessness** - The server does not store any information about the client's state between requests, allowing the server-side to be more scalable.

2. **Cacheability** - Each API response should be marked either as cacheable or not, to allow the client to save responses e.g., using "Cache-Control" and "Expires" headers.

---

## Core Qualities

1. Identify resources using a URL
2. Different verbs i.e., GET,POST, etc.. produce different actions.
	- **GET**: Retrieve a resource.
	- **POST**: Create a new resource.
	- **PUT**: Update an existing resource entirely.
	- **PATCH** : Update an existing resource partially.
	- **DELETE**: Remove a resource.
- Use existing [[HTTP]] status code standards. Error messages should be self-explanatory.
- The web service should be accessible via the browser.

---

## Disadvantages of REST

1. Not a simple way to define some API calls, and thus require additional query parameters and body.
2. REST is reliant on HTTP verbs which may not meet the use case by definition e.g., moving an expired document into an archived folder.
3. Fetching complicated resources may require multiple round trips e.g., paginating over posts on a Twitter to populate the timeline.
4. API calls can be updated, more fields are added which may bloat the API calls.
5. API calls may over-fetch data, leading to needlessly larger latencies.