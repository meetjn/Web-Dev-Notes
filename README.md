# Web-Dev-Notes
This repo will contain all the resources and notes that I will use to prepare for my web development journey. 

Question 1: what happens when the website is first reloaded?

answer: the first request goes to the server and gets the HTML and then the second request goes out to get the javascript file. 

NEXTJS (FULL STACK FRAMEWORK)

The problem nextJS has solved over reactjs is that -> 1) it solved the water falling problem and 2) made the website SEO optimized. 

FEATURES OF NEXTJS:
1) Server-side rendering - Get rid of SEO problems
2) API routes - Single codebase with frontend and backend -> (IT IS A FULL STACK FRAMEWORK WHERE AS REACT IS A FRONTEND FRAMEWORK).
3) File-based routing (no need for react-router-dom)
4) Bundle size optimisations, Static site generation
5) Maintained by the Vercel team.

Downside as well:
1) Can’t be distributed via a CDN (not easy to deploy on AWS), always needs a server running that does server-side rendering and hence is expensive (It is expensive at scale).
2) Very opinionated, very hard to move out of it. 

BOOTSTAPPING UP THE NEXTJS PROJECT:

Run: npx create-next-app@latest

After running the command, you will notice that these three files have been initialized. 

next.config.mjs - Nextjs configuration file

tailwind.config.js - Tailwind configuration file

app - Contains all your code/components/layouts/routes/apis

NOTE:
package.json: which contains all the dependencies. YOU WILL NOTICE THAT IT HAS REACT AND REACT-ROUTER-DOM this is because Next is written on top of reactjs. 

Q2: how many dev dependencies do we have? 

A: TWO types -> dependencies and dev dependencies. 

UNDERSTANDING ROUTING IN NEXTJS

Next.js has a file-based router, which means that the way you create your files describes what renders on a route
