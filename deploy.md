# Deployment Guide

This project is built as a zero-build Single Page Application (SPA). It uses CDNs for React, TailwindCSS, and Babel, meaning it does not require Node.js, Webpack, or Vite to run. It can be served from any static file host.

## Option 1: GitHub Pages (Easiest)
Since you are already hosting this repository on GitHub, GitHub Pages is the fastest way to get it live.

1. Ensure your main HTML file is named `index.html` and is located in the root of your repository.
2. Go to your repository on GitHub.
3. Click on **Settings** > **Pages** (under the "Code and automation" section on the left).
4. Under **Build and deployment**:
   - Source: Select **Deploy from a branch**
   - Branch: Select `main` (or `master`) and the `/ (root)` folder.
5. Click **Save**.
6. Wait 1-2 minutes. GitHub will provide you with a live URL (e.g., `https://yourusername.github.io/your-repo-name/`).

## Option 2: Vercel
Vercel provides excellent global edge caching.

1. Go to [Vercel.com](https://vercel.com/) and sign in with your GitHub account.
2. Click **Add New** > **Project**.
3. Import your GitHub repository.
4. Leave the Framework Preset as **Other** and the Build Command empty (since there is no build step).
5. Click **Deploy**. Your site will be live in seconds.

## Option 3: Netlify
Netlify is another excellent option for static sites.

1. Go to [Netlify.com](https://www.netlify.com/) and log in with GitHub.
2. Click **Add new site** > **Import an existing project**.
3. Select GitHub and authorize access to your repository.
4. Leave the Build Command and Publish Directory blank.
5. Click **Deploy site**.

## Environment Variables (Supabase)
Currently, the Supabase URL and Anon Key are hardcoded into the `index.html` file. Because this is a frontend-only application, these keys are publicly visible to the client anyway (which is safe as long as you have configured your **Row Level Security (RLS)** policies correctly in your Supabase dashboard). 

Ensure your Supabase `registry` table has RLS enabled so malicious users cannot arbitrarily delete or tamper with the distributed ledger.
