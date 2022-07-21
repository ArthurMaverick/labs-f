# Project Layout

```bash
├── build/                         # Compiled output
├── migrations/                    # Database schema migration files
├── node_modules/                  # 3rd-party libraries and utilities
├── public/                        # Static files such as favicon.ico etc.
├── scripts/                       # Automation scripts (yarn update-schema etc.)
├── seeds/                         # Reference and seed data for the database
├── src/                           # Application source code
│   ├── admin/                     # Admin section (Dashboard, User Management etc.)
│   ├── common/                    # Shared React components and HOCs
│   ├── icons/                     # Icon components
│   ├── news/                      # News section (example)
│   ├── pages/                     # Static pages (landing, about, privacy, etc.)
│   ├── server/                    # Server-side code (API, authentication, etc.)
│   │   ├── db/                    # Database client
│   │   ├── story/                 # Story related schema, queries, and mutations
│   │   ├── templates/             # HTML templates for server-side rendering
│   │   ├── user/                  # User related schema, queries, and mutations
│   │   ├── api.js                 # GraphQL API middleware
│   │   ├── Context.js             # GraphQL context wrapper
│   │   ├── createRelay.js         # Relay factory method for Node.js environment
│   │   ├── index.js               # Node.js app entry point
│   │   ├── login.js               # Authentication middleware (e.g. /login/facebook)
│   │   ├── schema.js              # GraphQL schemaƒ
│   │   └── ssr.js                 # Server-side rendering, e.g. ReactDOMServer.renderToString(<App />)
│   ├── user/                      # User pages (login, account settings, user profile, etc)
│   ├── createRelay.js             # Relay factory method for browser envrironment
│   ├── index.js                   # Client-side entry point, e.g. ReactDOM.render(<App />, container)
│   ├── router.js                  # Universal application router
│   ├── serviceWorker.js           # Service worker helper methods
│   └── theme.js                   # Overrides for Material UI default styles
├── ssl/                           # SSL certificates for connecting to Cloud SQL instance
├── .env                           # Environment variables
├── .env.local                     # Local (development) overrides
├── graphql.schema                 # GraphQL schema (auto-generated, used by Relay)
└── package.json                   # The list of project dependencies + NPM scripts
```
