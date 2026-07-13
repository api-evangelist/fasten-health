---
title: "Developers Need to Know: SQL Is Not Enough for FHIR Data"
url: "https://blog.fastenhealth.com/developers-need-to-know-sql-is-not-enough-for-fhir-data"
date: "2026-07-04"
author: ""
feed_url: "https://blog.fastenhealth.com/feed.xml"
---
This article explains why storing FHIR healthcare data in standard SQL databases creates performance and scalability problems, noting that FHIR is a graph rather than a document and requires complex reference resolution across resources. It argues that instead of using PostgreSQL JSONB as a shortcut, developers should implement purpose-built Clinical Data Repositories to handle nested data structures, automatic indexing, and schema-free versioning. It compares approaches from Google Healthcare API, Azure Health Data Services, and Smile Digital Health.
