# Hugo TailwindCSS starter

This starter is based on [the official Hugo documentation guide](https://gohugo.io/functions/css/tailwindcss/)


## Getting started

Install npm dependencies and start hugo server

```
npm install
npm run dev
```

### Running Hugo in GitHub Codespaces

When running Hugo in GitHub Codespaces, there are some networking quirks that require specific server flags. The `npm run dev` script uses the following command:

```
hugo server --appendPort=false --baseURL / --bind 0.0.0.0
```

**Explanation of flags:**

- `--appendPort=false`: Prevents Hugo from appending the port number to URLs. Codespaces uses port forwarding, and the forwarded URL doesn't include the port, so appending it would create broken links.

- `--baseURL /`: Sets the base URL to root. This ensures all asset paths work correctly with Codespaces' port forwarding proxy, regardless of the forwarded URL structure.

- `--bind 0.0.0.0`: Binds the server to all network interfaces instead of just localhost. This is necessary because Codespaces needs to forward the port from the container to the external URL, and binding to 0.0.0.0 allows external connections to reach the server.
