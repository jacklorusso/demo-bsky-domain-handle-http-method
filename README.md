# Demo: verify a domain handle on Bluesky via the HTTP/non-DNS method with Astro

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
├── src/
│   └── pages/
│       ├── .well-known
│       │   └── atproto-did.ts
│       └── index.html
└── package.json
```

If you run the build and navigate to `/.well-known/atproto-did` you'll be served plain text that reads `did:plc:yourDIDhere`. This is achieved with an
[Astro static file endpoint](https://docs.astro.build/en/core-concepts/endpoints/#server-endpoints-api-routes)

```typescript
import type { APIRoute } from "astro";

export const GET: APIRoute = () => {
  return new Response("did:plc:yourDIDhere");
};
```

Update the `src/pages/.well-known/atproto-did.ts` file with your own DID,
build the site and deploy it somewhere (I like [Netlify](https://www.netlify.com)). Then you'll be able to verify your custom domain handle on Bluesky with the HTTP method!

This demo might be useful if you don't have access easy access to the DNS
records of your site or subdomain. You may not even want to maintain a
website there, you can just use this to bootstrap the domain
authentication! For example, my bot project [@helveticabot.jacklorusso.com](https://bsky.app/profile/helveticabot.jacklorusso.com) is on a subdomain of my website, but doesn't really need a web presence; I
just used this approach as a little workaround because I couldn't figure
out how to use the DNS method with subdomains on Netlify.

For more information read ['How to set your domain as your handle'](https://blueskyweb.xyz/blog/4-28-2023-domain-handle-tutorial) on the Bluesky blog.

Thanks! —
[@jacklorusso.com](https://bsky.app/profile/jacklorusso.com)

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## 👀 Want to learn more?

Feel free to check [the Astro documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).