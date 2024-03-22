# Web-Dev-Notes
This repo will contain all the resources and notes that I will use to prepare for my web development journey. 

Question 1: what happens when the website is first reloaded?

answer: the first request goes to the server and gets the HTML and then the second request goes out to get the javascript file. 

NEXTJS (FULL STACK FRAMEWORK)

The problem nextJS has solved over reactjs is that -> 1) it solved the water falling problem and 2) made the website SEO optimized. 

FEATURES OF NEXTJS:
1) Server-side rendering - Get rid of SEO problems -> Server-side rendering (SSR) in Next.js is a feature that allows you to render React components on the server instead of the client, improving performance and search engine optimization (SEO). Next.js provides built-in support for SSR through its file-based routing system and API routes.
2) API routes - Single codebase with frontend and backend -> (IT IS A FULL STACK FRAMEWORK WHERE AS REACT IS A FRONTEND FRAMEWORK).
3) File-based routing (no need for react-router-dom)
4) Bundle size optimisations, Static site generation
5) Maintained by the Vercel team.

Downside as well:
1) Can’t be distributed via a CDN (not easy to deploy on AWS), always needs a server running that does server-side rendering and hence is expensive (It is expensive at scale).
2) Very opinionated, very hard to move out of it. 

1) BOOTSTAPPING UP THE NEXTJS PROJECT:

Run: npx create-next-app@latest

After running the command, you will notice that these three files have been initialized. 

next.config.mjs - Nextjs configuration file

tailwind.config.js - Tailwind configuration file

app - Contains all your code/components/layouts/routes/apis

NOTE:
package.json: which contains all the dependencies. YOU WILL NOTICE THAT IT HAS REACT AND REACT-ROUTER-DOM this is because Next is written on top of reactjs. 

Q2: how many dev dependencies do we have? 

A: TWO types -> dependencies and dev dependencies. 

2) UNDERSTANDING ROUTING IN NEXTJS

Next.js has a file-based router, which means that the way you create your files describes what renders on a route.
Each folder represents a route segment that maps to a URL segment. To create a nested route, you can nest folders inside each other.
A special page.js file is used to make route segments publicly accessible.
See official docs here -> https://nextjs.org/docs/app/building-your-application/routing/defining-routes

The next thing to understand in routing in nextjs is PAGES:

A page is a UI that is unique to a route. You can define a page by default exporting a component from a page.js file.

For example, to create your index page, add the page.js file inside the app directory:

CODE:
<img width="633" alt="Screenshot 2024-03-22 at 7 44 29 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/3ad4d09a-b069-4e56-9811-0b05d1dcfacd">


Then, to create further pages, create a new folder and add the page.js file inside it. For example, to create a page for the /dashboard route, create a new folder called a dashboard, and add the page.js file inside it:

<img width="633" alt="Screenshot 2024-03-22 at 7 44 08 AM" src="https://github.com/meetjn/Web-Dev-Notes/assets/141674944/84f5b044-cf32-45d9-8524-361b15f12fec">


