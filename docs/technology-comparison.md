# Technology Comparison

## 1. Introduction

The purpose of this document is to compare possible technologies for the development of the digital avatar advertising platform.

The technologies are preliminary options.

Final choices will be made after user requirements and integration needs are clearer.

## 2. Application Server Technologies

Three possible technologies were considered:
- FastAPI
- Django
- Express

### FastAPI

FastAPI is a Python framework for building application programming interfaces.

Possible uses in our project:
- Validate campaign requests
- Process application data
- Connect external generation services
- Return structured responses

FastAPI is currently a candidate for the server implementation.

### Django

Django is a Python web development framework.

It offers built-in functions that may be useful if the platform requires more administration features.

Django remains an alternative.

### Express

Express is a web framework for Node.js.

It is another possible solution for handling web requests and server functions.

No final server framework has been selected.

## 3. Database Technologies

The following databases were considered:
- PostgreSQL
- SQLite
- MongoDB

### PostgreSQL

PostgreSQL is a relational database system.

It is a candidate for storing connected project records such as:
- Campaigns
- Campaign versions
- Video generation tasks
- Output references

### SQLite

SQLite may be useful for small local experiments.

It offers a simple storage option during early development.

### MongoDB

MongoDB is a document-oriented database.

It was considered as an alternative storage technology.

The final choice depends on the project data requirements.

## 4. Background Video Generation

Video generation can take longer than an ordinary web request.

The system needs a way to track generation progress.

Three approaches were considered:

### Periodic Status Checking

The application sends status requests at intervals.

This is a possible starting approach.

### Completion Notifications

An external video generation provider sends a notification when processing finishes.

This approach depends on provider support.

### Message Queue

A separate queue may help manage background work.

It should only be introduced if the actual workload requires it.

## 5. Preliminary Technology Direction

| Component | Candidate |
|---|---|
| Application server | FastAPI |
| Database | PostgreSQL |
| Local testing database | SQLite |
| Generation status | Periodic status checking |
| External video generation | Provider not selected |
| Separate job queue | To be evaluated |

These are planning options, not confirmed implementation results.

## 6. Selection Criteria

The final technologies will be selected using:

1. Compatibility with project requirements
2. Team skills
3. Development complexity
4. Provider availability
5. Integration effort
6. Cost
7. Security and maintainability

## 7. Current Limitations

No measured performance comparison has been completed.

The team has not yet selected a final video generation provider.

Speed, reliability and cost differences must be checked before making final decisions.

## 8. Next Steps

The team plans to:
1. Confirm important user requirements.
2. Review provider access and documentation.
3. Test a small generation service connection.
4. Define shared data structures.
5. Confirm server and database technologies.
6. Begin implementation after the development scope is agreed.

## 9. Conclusion

The preliminary comparison provides a technical starting point for the platform.

FastAPI and PostgreSQL are candidate technologies, while periodic status checking is a possible initial method for monitoring generation tasks.

The final architecture will depend on requirements, provider support and practical testing.
