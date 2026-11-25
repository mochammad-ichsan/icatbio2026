# System architecture

The inspected TypeScript workspace separates a public React/Vite conference website, a React/Vite organizer interface, and an Express API. The server uses PostgreSQL through Drizzle ORM for structured records. Zod and an OpenAPI-to-client generation workflow are present. Public event materials are served from application storage through a restricted asset route. Email notification is conditional on mail configuration. Manuscript submission uses a separate institutional system rather than the application API.

The diagram in the [README](../../README.md#system-overview) intentionally presents components at a conceptual level. It is **not** a deployment topology or security diagram. In particular, a diagram arrow means a code path or documented connection, not that a transaction has been independently tested in production.

Public pages read conference configuration and listings from the API where available and may use local site data as fallback. Some public schedules are represented in site data; the main timetable may also be read from API records. The organizer interface includes authenticated content-management paths. Details of the login implementation, session format, secrets, privilege checks, network addresses, and administrative routes are intentionally excluded.

Architecture in this document describes the inspected workspace at portfolio preparation time. It does not imply that a documentation-only GitHub repository can build or serve the institutional application.
