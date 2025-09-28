# Cable Track Pro

Cable Track Pro is a app designed to make documenting the pulling of cables by electricians and others easier. It imports cable data from comma-separated-value (CSV) or JavaScript Object Notation (JSON) files and exports to the same formats to be imported into Building Information Management (BIM) applications.

## Getting Started

These instructions will set up a copy of the project on your local machine for development and testing purposes. See [deployment](#deployment) for notes on how to deploy the project on a live system.

### Prerequisites

* [Node.js](https://nodejs.org/en/download) - JavaScript runtime environment
* [PostgreSQL](https://www.postgresql.org/download/) - Database management system
* [Git](https://git-scm.com/downloads) - Distributed version control system

If you are running Windows, we strongly suggest using [Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/install) and installing [Ubuntu Linux](https://apps.microsoft.com/detail/9pdxgncfsczv). 

### Installing

1. Fork the [Repository on GitHub](https://github.com/awjans/cabletrack.pro/fork).
2. Clone the Repository

```bash
git clone git@github.com:{owner}/cabletrack.pro.git
```
Replace `{owner}` with your GitHub user or organization id.

3. Install the Dependencies

```bash
npm install
```

4. Create a Database

```bash
sudo -u postgres createdb cabletrackpro
```

4. Setup the Environment
Use the `sample.env` file to create a `.env` file with an edited `DATABASE_URL` and `NEXTAUTH_SECRET`

```bash
DATABASE_URL="postgresql://postgres:{password}@localhost:5432/cabletrackpro?schema=public"
NEXTAUTH_SECRET="{secret}"
NEXTAUTH_URL=http://localhost:3000
```
Replace `{password}` with the Root Password you set during the installation of PostgreSQL.
Replace `{secret}` with a random string. This can be generated using `openssl rand -base64 64`.

5. Migrate and Seed the Database

```bash
npx prisma migrate && npx prisma db seed
```

6. Start the Node.js Server in Development mode

```bash
npm run dev
```

7. Open your web browser to the [Home Page](https://localhost:3000)

Read the [User Guide](https://docs.cabletrack.pro) for more information about how to use the app.

## Running the tests

Cable Track Pro uses Jest and the React Testing Library for unit and acceptance testing. These frameworks are lightweight and provide good coverage.

```bash
npm run test
```

### And coding style tests

Cable Track Pro uses ESLint to enforce coding standards, so that we all write similar code and don't leave uncessary artifacts in the codebase.

```bash
npm run lint
```

## Contributing

Please read [CONTRIBUTING](CONTRIBUTING.md) for details on the process for submitting pull requests to us.

## Versioning

We use [Semantic Versioning](http://semver.org/). For the versions available, see the [tags on this repository](https://github.com/awjans/cabletrack.pro/tags). 

## Authors

* **Andrea Jans** - *Initial work* - [awjans](https://github.com/awjans)

See also the list of [contributors](https://github.com/awjans/cabletrack.pro/contributors) who participated in this project.

## License

This project is licensed under the TBD License - see the [LICENSE](LICENSE.md) file for details
