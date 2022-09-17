The front-end was built with React and Typescript for responsive UI.
The backend of the project was built as a monolith but organically evolved into a small web of python microservices. Each of those is built with the **FastAPI** framework, as it is lightweight, really fast, and refreshingly convenient to work with.

- microfunkhaus is the facade/gateway microservice. It orchestrates the chord-progression generation pipeline asynchronously with the **aiohttp** library using the **pydantic** library for robust data coercion, validation and serialization.

- microaccountant is a persistent, session-based, SQL dialect-agnostic, transaction-aware microservice that provides data storage and retrieval with **SQLAlchemy** and **pydantic**

- microbureaucrat is a small and robust microservice MIDI-file generation, that uses the **mido** library to create MIDI files and serves them as a hex-encoded string.

- microvoicemaster is a microservice for converting chord-specifications into note-implementations based on the propreitary **voicemaster** python library.

- micropathforger is a microservice to generate chord progression specifications given the mode definition based on the proprietary **pathforger** python library.

The project uses the **poetry** tool for dependency management and package building.
Apart from the **fastapi** library, all of the microservices depend on the **chrdiotypes** proprietary library. It defines common types, shemas and methods that glue different codebases together.
Also some of the microservices above feature another two proprietary python libraries - **pathforger** and **voicemaster**. They're the heart and soul of the project. Developed from scratch, both of them feature a good deal of controlled randomness to ensure that the content is original.