# show

Generative visuals for a wall or a projector. Public, MIT. One page: `web/index.html`, no dependencies.

- Public site: https://show.javierr.com (Cloudflare Worker `show`, static assets from `web/`).
  Deploy: `env -u NODE_OPTIONS npx -y wrangler deploy`.
- Everything in this repo is public. No hostnames, tokens, private paths or personal details here.
- The page must keep making no network requests, and no scene may strobe or flash.
- Clock rules for shaders: `uT` wraps at 2000 pi (only inside sin/cos, frequencies in multiples of .001); `uD`
  wraps at 256 (integer multiples only). Break either and the picture jumps once every few hours.
- One pass per frame: every scene ends with `fin()`. No scene buffer, no feedback pass.
