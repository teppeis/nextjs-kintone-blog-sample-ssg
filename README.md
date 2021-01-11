# A blog example using Next.js and Kintone with SSG (Static Site Generation)

This example showcases Next.js's [Static Site Generation](https://nextjs.org/docs/basic-features/pages) feature using [Kintone](https://www.kintone.com/) as CMS and the data source. This is based on [blog-starter-typescript](https://github.com/vercel/next.js/tree/canary/examples/blog-starter-typescript).

The blog posts are stored in Kintone. If you add a new blog post or edit an existing post in Kintone, they trigger re-build of the entire blog, and they are available after that is complete.

## Deploy your own

Deploy the example using [Vercel](https://vercel.com):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/git/external?repository-url=https://github.com/teppeis/nextjs-kintone-blog-sample-isr&project-name=nextjs-kintone-blog-sample-isr&repository-name=nextjs-kintone-blog-sample-isr)

Required Environment variables:
- `KINTONE_BASE_URL`: Like `https://<your-domain>.cybozu.com`
- `KINTONE_APP_ID`: Your Kintone app for the blog. Like `123`
- `KINTONE_API_TOKEN`: API token with read permission for your app

Required Kintone app schema:
- `slug`: `SINGLE_LINE_TEXT`
- `title`: `SINGLE_LINE_TEXT`
- `date`: `DATETIME`
- `coverImage`: `SINGLE_LINE_TEXT`
- `excerpt`: `SINGLE_LINE_TEXT`
- `authorName`: `SINGLE_LINE_TEXT`
- `authorPicture`: `SINGLE_LINE_TEXT`
- `ogImage`: `SINGLE_LINE_TEXT`
- `content`: `MULTI_LINE_TEXT`

### Trigger Vercel Deploy from Kintone Webhook

Kintone has [Webhook](https://get.kintone.help/k/en/user/app_settings/set_webhook/webhook.html) and Vercel has [Deploy Hooks](https://vercel.com/docs/more/deploy-hooks). By combining them, you can automate the build process.

1. Create a Deploy Hook in your Vercel project and get the URL
2. Create a Webhook in your Kintone app and set Vercel Deploy Hook URL in it
