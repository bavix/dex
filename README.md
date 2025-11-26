Dex (custom theme)

This image embeds the `@bavix/babichev-design` CSS and the theme templates into the official Dex image.

How to apply or change the theme
- Edit the templates under `web/themes/babichev` (header/footer/login/password/etc).
- Rebuild the image:
  - docker build -t dex-babichev .
- Run Dex:
  - docker run -d --name dex-demo -p 5556:5556 dex-babichev
- Visit the auth UI to verify: http://localhost:5556/dex/auth

Notes
- The Dockerfile uses a multi-stage build to pull the compiled CSS from the design package and place it into Dex frontend.
- To change the design system itself, update `@bavix/babichev-design`, publish a new release, update the dependency in `package.json`, and rebuild the image.

Based on: https://github.com/dexidp/dex
