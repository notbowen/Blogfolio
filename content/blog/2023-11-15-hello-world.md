+++
title = "Hello World - An Introduction to my Blog"
+++

Following the tradition of creating a "Hello World" program after a project is set up,
here is the markdown equivalent of mine. I'll talk about the underlying technolgies
powering this blog, along with its deployment process that I've setup using Vercel.

## Underlying Technologies

- [Zola](https://getzola.org/), An SSG written in Rust
- [Anemone](https://www.getzola.org/themes/anemone/), A cool looking theme for Zola
- [Vercel](https://vercel.com/), A platform to deploy static sites

## Why Zola?

Previously, my portfolio site used a custom Rust webserver and stored the blog posts
in a multi modal database called [SurrealDB](https://surrealdb.com/). While it was
a great learning opportunity, I found it too troublesome to maintain, especially due
to the fact that SurrealDB is still in it's alpha stage, meaning that breaking changes
are released every now and then. The build times were also insane, averaging about
8-10 minutes per deployment.

{{ img(id="build_times.png", alt="Insane build times", class="textCenter") }}

I settled on using a static site generator as it is rather easy to maintain and write
new posts, since they force you to follow a certain folder structure while giving
you free reign over the site's looks, feel and content. Static site generators create
webpages in advance, improving performance and having a lighter backend since the need
to query webpages from a database is removed.

Cloudflare wrote a great article on what a static site generator is [here](https://www.cloudflare.com/learning/performance/static-site-generator/).

## Deployment using Vercel

Using Zola made things really easy to configure, it basically works out of the box. I just
needed to click "Import from Git Repository" and it got everything set up 😎. Deployments
happen automatically when I push to the `main` branch.

{{ img(id="vercel_prod.png", alt="Vercel production", class="textCenter") }}

An added bonus is that they help you set up your custom domains too!

{{ img(id="custom_domains.png", alt="Custom domains", class="textCenter") }}

## Closing Thoughts

All in all, this framework feels rather solid so far and I hope that it'll last me for the
time to come 😄. Gone are the days where I have to cry at the screen while refactoring half
my codebase due to a breaking change from a new database, and I hope the speedy compile times
last as my number of blog posts increases.
