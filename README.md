# CS 340: Client/Server Development Portfolio

This repository contains coursework for CS-340-13502-M01, Client/Server Development, 2026 C-5. The Grazioso Salvare project uses a MongoDB animal shelter database and a reusable Python data-access module to support finding dogs for rescue work.

## Current portfolio artifact

[Project One submission archive](Project_One_Chas_Steves_Submission%20%282%29.zip) contains:

- **CRUD_Python_Module.py**: the reusable AnimalShelter class with Create, Read, Update, and Delete operations.
- **ProjectOneTestScript.ipynb**: a notebook that verifies the four operations with a temporary test record.
- **Project_One_README_Chas_Steves.docx**: module documentation, usage instructions, and screenshots of the database import, authentication, and CRUD results.

## How do you write programs that are maintainable, readable, and adaptable?

I write maintainable programs by separating responsibilities, using descriptive names, documenting methods, and checking inputs. In Project One, the AnimalShelter class keeps the MongoDB connection and CRUD operations in one module. Each method performs a focused task and returns a documented result, such as a list of matching records or the number of documents modified. The test notebook checks the full Create, Read, Update, and Delete sequence and confirms that the temporary record is removed.

This separation gives the Project Two dashboard a consistent way to access the database: a widget callback can pass a query to read() instead of repeating connection and query code throughout the interface. It makes the database layer easier to test independently and lets database changes stay in one place. The constructor also accepts a host, port, database, and collection, making the module adaptable to other environments. I could reuse it in a reporting script, an administrative tool, or another dashboard that works with MongoDB documents.

## How do you approach a problem as a computer scientist?

I approach a problem by breaking the client's needs into smaller, testable requirements. For Grazioso Salvare, that means understanding which animal records are relevant to rescue work, checking the available data fields, and translating selection criteria into database queries. Project One establishes the database foundation by importing the shelter data, verifying authenticated access, and testing CRUD operations before connecting an interface to that layer. For the dashboard, I would trace each filter and display back to a client requirement and verify that the returned records match the intended criteria.

Compared with an assignment centered on a single function, this project requires thinking about how the database, Python module, and user interface work together. A successful query is only useful if the interface presents its results clearly. For future client requests, I would clarify the required fields and workflows, inspect sample data for missing or inconsistent values, choose a suitable schema, and define expected query results before implementation. I would then test representative cases, consider indexes for frequent queries, and review the results with the client to confirm that the database supports their actual decisions.

## What do computer scientists do, and why does it matter?

Computer scientists turn practical problems into systems that organize information, automate repeated work, and support decisions. Their work includes understanding user needs, designing data structures and software, testing behavior, and maintaining systems as requirements change. Readable code and dependable data access matter because people need to understand, trust, and improve the tools they use.

For Grazioso Salvare, a database-connected dashboard could help staff narrow a large set of shelter records to dogs that meet specified rescue-training criteria. Filters, tables, and visual displays would make relevant information easier to compare and reduce the effort of searching records manually. The software would support staff judgment about potential candidates while allowing them to spend more time evaluating and training dogs. The reusable CRUD module provides a foundation for extending that workflow as the organization's needs grow.
