# Developer Guide

## Onboarding

### Pre-requisites

- [Node.js][nodejs] v12 or higher + [Yarn][yarn] v1.6 or higher &nbsp; (_HINT: On Mac install them via [Brew][brew]_)
- [VS Code][vc] editor (preferred) + [Project Snippets][vcsnippets], [EditorConfig][vceditconfig],
  [ESLint][vceslint], [Prettier][vcprettier], and [Babel JavaScript][vcjs] plug-ins
- [Watchman][watchman] file watcher used by Relay Modern
- [PostgreSQL][postgres] v9.6 or newer, only if you're planning to use a local db for development

### Getting Started

Clone the repo, create a local env file named `env.local`.

Add the entry `PGPASSWORD=##DB_PASSWORD_HERE##` with your password

### Running PostgresSQL though docker

If you want to run postgres though docker you'll need to set your password in `env.local` to the value `postgres`

Run the following docker command in the root of the project

run: docker-compose up

Free GUI for Postgres
https://tableplus.io/

1 - Obtain the .env and .env.local files from another developer  
2 - Create a db in Postgres named 'app'  
3 - Run `yarn db-migrate` to create the schema  
4 - Run `yarn db-seed` if you want to seed sample data

### How to Migrate Database Schema

```bash
$ yarn db-change                   # Create a new database migration file
$ yarn db-migrate                  # Migrate database to the latest version
$ yarn db-rollback                 # Rollback the latest migration
$ yarn db-save                     # Save data from database to JSON files
$ yarn db-seed                     # Seed database with previously saved data
$ yarn db                          # Open PostgreSQL shell (for testing/debugging)
```

**Note**: Appending `--env=production` flag to any of the commands above will force it to use
database connection settings from `.env.production` and/or `.env.production.local` file(s).

**DB Migration Problem**:
If you are running `yarn db-migrate` first time, an error related to `20201105162831_decision_and_contact_status.ts` and `20210727205238_update-buyermap.ts` files might occur. The error message will be related to the `decision_status` and `contact_status` data types. To solve this problem, please change `useNative: true` into `useNative: false` at four places out of 2 files temporarily; then run `yarn db-migration` then backup the files as original after the successful migration.

### How to Test

```bash
$ yarn lint                        # Check JavaScript and CSS code for potential issues
$ yarn lint-fix                    # Attempt to automatically fix ESLint warnings
$ yarn test                        # Run unit tests. Or, `yarn test -- --watch`
```

```bash
$ yarn start                       # Compile the app and opens it in a browser with "live reload"
```

Then open [http://localhost:3000/](http://localhost:3000/) to see the application<br>
