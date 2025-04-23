# Frontity - Now builder

Use this builder to deploy a [Frontity](https://frontity.org) project in the Vercel hosting.

## About this fork

This is the fork of the official custom builder for Frontity (@frontity/now) to pulish the site on Vercel.

This is just a hack job without actually understanding what the code is actually about.

### The things that I already done
- Resolve the dependency problem. (eslint related)
- Update all dependencies to the latest version.
- Replace @now package with @vercel package equivalent.
- Add dist into the repo to make it installable via npm.

### Why I do this?

Because I kind of annoyed that despite Vercel support using when npm 7 when encountering package-lock.json with lockfile version 2, 
it not worked as it should with the builder.
Also, I cannot specify node version 14.x on my package.json. These make me suspect maybe the cause is on the older @now library that 
@frontity/now using do not support the features. So, I tried to do it myself. And it actually worked!

Now, npm install will automatically use npm 7 when encountered lockfile version 2 as it should!

## Before deploying

1. Create this `vercel.json` file in your project and change the site url:

```json
{
  "alias": "www.your-site.com",
  "version": 2,
  "builds": [
    {
      "src": "package.json",
      "use": "github:Miracutor/now-builder"
    }
  ]
}
```

2. Create an account on Vercel. You can [signup here](https://vercel.com/signup).

3. Log in the terminal:

```bash
> npx vercel login
```

## Deploy a test site

Deploy Frontity using this command:

```bash
> npx vercel
```

That will give you a unique URL for that deploy. Check that everything is ok.

## Deploy a production site

You need to [add a CNAME](https://zeit.co/docs/v2/custom-domains/#option-2:-using-external-nameservers) of `www.your-site.com` to `alias.zeit.co` in your domain DNS settings.

Then, deploy Frontity using this command:

```bash
> npx vercel --target production
```

That will createa a deploy and assign it to your real site url.
