<!-- --- -->
## Long
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
4. "microvoicemaster" - the voicification microservice.
    - uses the propreitary **voicemaster** library to turn abstract chord definitions into concrete note-implementations
    - uses the pydantic library for data coercion
5. "micropathforger" - the chord-specification generator.
    - uses the propreitary **pathforger** library to generate chord-progression specs given the mode definition
    - uses the pydantic library for data coercion
