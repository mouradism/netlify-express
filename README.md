# netlify-express

A boilerplate for running an [Express](https://expressjs.com/) server as a [Netlify Function](https://www.netlify.com/products/functions/) using [`serverless-http`](https://github.com/dougmoscrop/serverless-http) and [`netlify-lambda`](https://github.com/netlify/netlify-lambda).

## Prerequisites

- [Node.js](https://nodejs.org/) (v8 or higher)
- [npm](https://www.npmjs.com/)
- [Netlify CLI](https://docs.netlify.com/cli/get-started/) (optional, for local development via Netlify Dev)

## Installation

```bash
npm install
```

## Development

Start a local development server with hot-reloading:

```bash
npm start
```

This runs `netlify-lambda serve src`, which compiles the functions in `src/` and serves them locally. The API will be available at:

```
http://localhost:9000/.netlify/functions/api
```

## Build

Compile the functions for production deployment:

```bash
npm run build
```

The compiled output is placed in the `functions/` directory (as configured in `netlify.toml`).

## Project Structure

```
netlify-express/
├── src/
│   └── api.js          # Express app wrapped for serverless deployment
├── dist/               # Static assets publish directory
├── netlify.toml        # Netlify build & dev configuration
└── package.json
```

## API

| Method | Path | Description |
|--------|------|-------------|
| GET | `/.netlify/functions/api/` | Returns a JSON greeting `{ "hello": "hi!" }` |

## Deployment

1. Push this repository to GitHub (or GitLab / Bitbucket).
2. Connect the repository to [Netlify](https://app.netlify.com/).
3. Netlify will automatically detect `netlify.toml` and run `npm run build` to deploy your functions.

The function will be accessible at:

```
https://<your-site>.netlify.app/.netlify/functions/api
```

## License

ISC