# [Twitter Bio Generator](https://twbio.vercel.app/)

This project uses AI to generate Twitter bios for you.

![image](https://user-images.githubusercontent.com/80656256/213340226-6adeca2a-f6bf-4a28-876f-40a236c25778.png)


## How it works

This project uses the [OpenAI GPT-3 API](https://openai.com/api/) (specifically, text-davinci-003) and [Vercel Edge functions](https://vercel.com/features/edge-functions) with streaming. It constructs a prompt based on the form and user input, sends it to the GPT-3 API via a Vercel Edge function, then streams the response back to the application. 

The code is a Next.js application that allows users to generate Twitter bios. It makes use of several libraries and components, including "framer-motion", "next", "react", and custom components such as "DropDown", "Footer", "GitHub", "Header", "LoadingDots", and "ResizablePanel".

It imports the necessary libraries and components at the top, and then defines a NextPage component called "Home". Within the component, it uses the useState hook to manage the state of the application, including a loading state, the user-entered bio text, the selected vibe ("Professional", "Casual", or "Funny"), and the generated bios.

The component has a form with a textarea for the user to enter their bio and a dropdown to select the vibe. When the form is submitted, the generateBio function is called, which sends a request to an API route /api/generate passing the prompt as a body. The prompt is a string that varies based on the selected vibe, and it's used to guide the generation of the bios.

The server-side function that handles the /api/generate route will use the prompt to generate the bios and sends the response back to the client. The client-side function generateBio receives the response and reads the data using a ReadableStream and TextDecoder to parse the bios and updating the state with the generated bios.

The component also includes a Toaster and a toast for displaying error messages, and a LoadingDots component for displaying a loading spinner while the bios are being generated. The component is rendered as a flex container with a maximum width of 5xl, centered horizontally and vertically on the screen. The Head component is used to set the title of the page.

## Running Locally

After cloning the repo, go to [OpenAI](https://beta.openai.com/account/api-keys) to make an account and put your API key in a file called `.env`.

Then, run the application in the command line and it will be available at `http://localhost:3000`.

```bash
npm run dev
```

## One-Click Deploy

Deploy the example using [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=vercel-examples):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.dev/antonydis/twitter-bio-generator&env=OPENAI_API_KEY&project-name=twitter-bio-generator&repo-name=twitter-bio)

## Acknowledgments

Thanks to OpenAI, Vercel Edge Functions and [@nutlope](https://nutlope.substack.com/) for the inspiration.
