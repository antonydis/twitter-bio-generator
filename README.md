# [Twitter Bio Generator](https://twbio.vercel.app/)

This project uses AI to generate Twitter bios for you.

[![Twitter Bio Generator](./public/screenshot.png)](https://www.twitterbio.com)

## How it works

This project uses the [OpenAI GPT-3 API](https://openai.com/api/) (specifically, text-davinci-003) and [Vercel Edge functions](https://vercel.com/features/edge-functions) with streaming. It constructs a prompt based on the form and user input, sends it to the GPT-3 API via a Vercel Edge function, then streams the response back to the application. It was originally made by [@nutlope](https://nutlope.substack.com/).

## Running Locally

After cloning the repo, go to [OpenAI](https://beta.openai.com/account/api-keys) to make an account and put your API key in a file called `.env`.

Then, run the application in the command line and it will be available at `http://localhost:3000`.

```bash
npm run dev
```

## One-Click Deploy

Deploy the example using [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=vercel-examples):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.dev/antonydis/twitter-bio-generator&env=OPENAI_API_KEY&project-name=twitter-bio-generator&repo-name=twitter-bio)
