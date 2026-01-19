# Julia - Open source ChatGPT for cooking
I love using ChatGPT for cooking. It makes the process way simpler and approachable. Instead of long complicated recipes, it give simple instructions and acommodates the ingredients you have on hand. The recipes taste great too!

Julia is an open source chat app which streamlines common cooking needs:
- 📖 Ask for specific recipes
   - "Make me a chicken lo mein recipe."
- 💾 Saves recipes you like in a recipe book
- 💡 Get ideas to spice up your diet
   - "What are some steak sauces I can make in under 15 minutes?"
   - "What are some good budget friendly meal prep ideas?"

In the future, I want this to be one my one stop shop for my cooking needs. Some ideas:
- Meal planning
- Shared grocery list w/ family members
- Grocery receipt analyzer
- Sharing recipes (URL based, not just text)

## Self Hosting
1. Complete below prerequisites
2. Run these commands:
```sh
git clone https://github.com/bensenescu/julia.git
cd julia
npx everyapp app deploy
```
3. Add you OPENAI_API_KEY: 
```sh 
npx wrangler secret put OPENAI_API_KEY
```

### Prerequisites
Julia was built as part of my larger project: [Every App](https://github.com/every-app/every-app). Every App hoists common logic out of individual apps like auth and user management so that each app doesn't need to revinvent the wheel. 

The goal is to foster an open source ecosystem of apps and make it more accessible to people who aren't already self hosting software themselves.

Every App apps are self hosted on Cloudflare so there is a little bit of initial setup, but then self hosting more apps is as simple as the `npx everyapp app deploy` above.

1. Install [Node.js](https://nodejs.org/)

   This also installs `npx`, a tool that runs Node packages without installing them globally. You'll see `npx` commands throughout these docs.

2. Make a Cloudflare Account (No credit card needed) - https://dash.cloudflare.com/sign-up

   Skip any Cloudflare onboarding like configuring a domain, this is unnecessary for Every App. 

3. Authenticate with Cloudflare (choose one):
   - Login via the [Cloudflare CLI](https://developers.cloudflare.com/workers/wrangler/commands/#login) (recommended):
     ```bash
     npx wrangler login
     ```
   - Or set the `CLOUDFLARE_API_TOKEN` environment variable
4. Self host the Every App Gateway
    - `npx everyapp gateway deploy`
    - Follow the link this returns to create your account in the Gateway.


## Local Development
### Setup
1. `cp .env.example .env.local`
    - The `GATEWAY_URL` should match your gateway from  `npx everyapp gateway deploy`
2. `pnpm run db:migrate:local`
3. `pnpm install`

### Run locally
`pnpm dev`

## Helpful Resources

https://developers.cloudflare.com/workers/framework-guides/web-apps/tanstack/
https://orm.drizzle.team/docs/connect-cloudflare-d1


