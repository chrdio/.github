The heart and soul of the project are the two proprietary python libraries developed from scratch – "pathforger" and "voicemaster". Both of them feature a good deal of controlled randomness to ensure that the content is original.

The front-end is built with React and Typescript for responsive UI.

The backend of the project was built as a monolith but organically evolved into a small web of microservices. Each of those is built with the FastAPI framework, as it is lightweight, really fast, and refreshingly convenient to work with.

---
##Long

1. "microfunkhaus" - the facade/gateway microservice.
    - uses the **pydantic** library for robust data coercion, validation and serialization
    - orchestrates the chord-progression generation pipeline asynchronously with the **aiohttp** library
    - authorizes client requests with **FastAPI** and **starlette** middleware
2. "microaccountant" - the database manager microservice.
    - uses the **SQLAlchemy** library for SQL dialect-agnostic database access and ORM
    - uses the **pydantic** library to coerce data into database-compatible types
3. "microbureaucrat" - the MIDI-file generation microservice.
    - uses the **mido** library for MIDI-related tasks
    - manages file caching and hex-string convertion

---
##Short
microfunkhaus is the facade/gateway microservice. It orchestrates the chord-progression generation pipeline asynchronously with the aiohttp library using the pydantic library for robust data coercion, validation and serialization.

microaccountant is a persistent, session-based, SQL dialect-agnostic, transaction-aware microservice that provides data storage and retrieval with **SQLAlchemy** and **pydantic**

microbureaucrat is a small and robust microservice MIDI-file generation, that uses the **mido** library to create MIDI files and serves them as a hex-encoded string.

---
##Shorter
microfunkhaus is a gateway microservice for the progression generation pipeline.

microaccountant is a database manager microservice.

microbureaucrat is a MIDI-file generation microservice.