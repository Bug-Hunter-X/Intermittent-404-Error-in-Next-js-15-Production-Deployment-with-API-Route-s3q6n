# Next.js 15 Intermittent 404 Error with API Route

This repository demonstrates a bug encountered in a Next.js 15 application where an API route intermittently returns a 404 error in production. The issue occurs when navigating from one page to another page that fetches data from the API route. The problem is seemingly random.

## Steps to Reproduce

1. Clone the repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Navigate between the Home and About pages.  The About page will correctly fetch data from the API route. 
5. Build the application: `npm run build`
6. Run the production server: `npm run start`
7. Attempt to navigate between the pages multiple times.  You'll notice that the 404 error on About page occurs after several page transitions in production.

## Potential Causes

The root cause is likely related to the interaction between Next.js's build process, edge runtime, and the API route.  It could be an edge caching issue, or a problem with API route revalidation under load.

## Solution

The solution involved ensuring robust error handling, revalidation, and caching strategies in the API route and ensuring the API route was correctly deployed and configured in production.