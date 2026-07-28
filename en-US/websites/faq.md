---
title: "Kimi Websites FAQ"
slug: "websites-faq"
order: 3
extract_headings: true
preview: false
preview_content: "Frequently asked questions about using Kimi Websites."
---

<SeoMeta
  title="Kimi Websites FAQ - Kimi Help Center"
  description="Common troubleshooting for Kimi Websites, including preview issues, blank pages, data loss, and publish failures."
/>

# Kimi Websites FAQ

> For complete instructions on preview panel buttons, editing modes, publishing and unpublishing, see [Kimi Websites](/websites/websites-overview). This page only covers common troubleshooting.

## The preview won't load or I can't see the latest version?

> For example: "The website isn't showing up," "The preview is still the old version," or "I can't see the latest saved version."

In most cases, the website has been successfully generated and saved. The "can't see" issue usually happens with the preview panel or version card display. The most common cause is an incorrect project directory. Other cases can be handled in the following order:

<Callout type="warning">
**Verify the project directory**: The website project must be located at `/mnt/agents/output/app`. The preview only reads versions saved from this directory. If Kimi placed the project elsewhere (such as a temporary `/tmp` directory), the version may save successfully but the preview won't be able to read it—ask Kimi to move the project to this directory and save again.
</Callout>

1. **Refresh the page or reopen the conversation**—version cards sometimes take a few seconds to appear.
2. **Ask Kimi to save a new version in the conversation.**
3. **If the conversation is very long, try starting a new one** (see "My conversation is very long—should I start a new one?" below).
4. If it still doesn't appear: the code and version have usually been saved successfully (you can ask Kimi for the version number). This is often a temporary preview service fluctuation—please retry later. If it persists, click the **User Feedback** (envelope icon) in the preview panel to submit feedback with the version number, and our team will investigate.

## The website is blank, white screen, crashed, or unresponsive?

> For example: "The page is completely blank," "The website is empty," "The website crashed," or "Nothing shows up / clicking does nothing."

- A blank or crashed screen is usually caused by a **front-end runtime error** (such as missing dependencies, accessing a sub-page directly, or an individual resource or image failing to load). Describe the symptom to Kimi in the conversation (a screenshot is helpful), and it will locate and fix the issue, then save a new version.
- If you suspect the blank screen is caused by **missing files**, each version of the website saves a snapshot. Ask Kimi to restore from a historical version (see "Project files or directories are missing" below).
- **Browser compatibility**: Some privacy-focused browsers (Brave, certain Firefox add-ons) may block front-end resource loading, causing display anomalies. Try adding the Kimi domain to your whitelist, temporarily disabling shields/privacy blockers, or switching to Chrome / Edge / Safari.

## What if clicking "Publish" fails?

The handling is the same as above: retry later. If it persists, submit via **User Feedback** with the version number. The version has already been saved successfully and does not need to be rebuilt from scratch.

## How long is the website link valid? Will it expire?

If you click **Publish** to publicly deploy the website, the generated link will remain valid indefinitely unless you manually click **Unpublish** to make the site private, or the content is flagged for inappropriate content.

## Content, data, or records are missing?

> For example: "The content on my homepage disappeared," "The knowledge I uploaded to the database is gone," "The information I uploaded is missing," or "AI says the data is permanently lost."

In most cases, the data has not actually been lost. Verify in the following order:

1. **First, confirm whether the website is truly "full-stack"**: Only full-stack websites built with **back-end (database) capabilities** will store data in the platform's cloud database, persisting across visits and devices. In practice, many websites that claim to be "full-stack" **end up front-end only**, with data never actually entering the database—in this case, refreshing or switching devices will naturally make the previous data disappear. Ask Kimi to confirm whether the project includes a real back-end and database.
2. **Pure front-end website**: Data is only saved in your current browser's local storage (localStorage). Switching browsers / devices or clearing browser data will cause it to be lost. If you need long-term, multi-device data retention, ask Kimi to switch to a full-stack solution with a database.
3. **Confirmed full-stack website**: Data is saved in the platform-managed cloud database. **Publishing a new version will not clear existing data**; if data is still not visible despite being full-stack, this is usually a temporary issue—refresh or retry later.
4. **If you confirm data is actually lost**: Click the **User Feedback** (envelope icon) in the preview panel to submit feedback, and our team will investigate. Do not continue repeated operations at this point to avoid overwriting.

## Project files or directories are missing, or "environment reset" / "unable to recover"?

> For example: "My website project directory is gone and can't be recovered," "Files are missing," or "Environment reset message."

- Each version of the website **saves a snapshot**, so source code can usually be recovered from historical versions. Ask Kimi to list historical versions and roll back / restore to a specific version.
- If this happens in a **very long conversation** (especially if you switched models mid-conversation), we recommend starting a new conversation (see next item).
- If recovery is still not possible, click **User Feedback** to submit feedback, and our team will investigate.

## My conversation is very long—should I start a new one?

If a conversation has been ongoing for a long time, spanning many versions, or if you switched models mid-conversation (such as K2.6 → K3), the current capabilities may not be the latest version, leading to context loss or file anomalies. **We recommend starting a new conversation** to get the latest building and delivery capabilities. Published websites and historical versions are not affected and can still be accessed normally.

## Can I self-deploy after exporting the code?

You can download the complete project code and deploy it to your own server, but the following two items are provided by the Kimi platform and **will not migrate with the code**:

- **Kimi account login**: This is a platform-provided login capability that cannot be used directly after leaving the Kimi platform. If you need login for self-deployment, ask Kimi to implement a username/password login system based on your own database.
- **Platform-managed database**: Full-stack website data is saved in the cloud database assigned by the platform for that site. The exported code does not include this data, nor will it automatically connect to your own database. Self-deployment requires setting up your own database and migrating data.

If you only want the webpage to be publicly accessible, simply use the platform's **Share → Publish** feature. No need to set up your own server—Kimi account login and cloud data will continue to work normally.

## The generated website doesn't match my requirements?

- In the conversation, specifically point out what doesn't match: for example, color, layout, text, feature modules, data tables, etc.
- You can upload reference images, example webpages, or more detailed text descriptions for the Agent to modify according to the reference.
- If you are still not satisfied after multiple modifications, try starting a new conversation with a more structured requirement description.

## Can I still modify the website content, links, or styles after generation?

Yes. In the original conversation, continue telling the Agent what you want to modify, for example:

- "Change the homepage title to XXX"
- "Change the 'Contact Us' button link to https://xxx"
- "Switch to a dark theme overall"

After modification, the Agent will regenerate and deploy a new link.

## How do I add a back-end, database, or login functionality to the website?

- Emphasize in the website-building instruction that you want a full-stack webpage with a database and login functionality.
- Alternatively, you can have the Agent generate the front-end page first, then export the source code and hand it over to a developer for secondary development.

## Can I download the website source code or export it to GitHub?

The current version supports downloading all files locally. In the conversation, open "All Files" and click the download button.

## How much credit does generating/modifying a website consume?

Website generation is a complex task that usually consumes a significant amount of tokens/credits, depending on:

- Number of pages and complexity
- Whether images, tables, and interaction logic are included
- Number of iterative modifications

We recommend making your requirement description as clear as possible to reduce trial and error. If you are not satisfied with the result, you can explain the situation in feedback.

## The website generation is very slow, keeps queuing, or the terminal fails?

- Peak hours (weekday daytime and evening) may experience queuing. We recommend using during off-peak hours.
- If the task is stuck for more than 10 minutes, try refreshing the webpage first.
- For complex websites, we recommend breaking them into smaller tasks: start with the homepage, then gradually add sub-pages and features.

## What is Kimi Websites suitable for? What is it not suitable for?

**Suitable for:**

- Personal homepages/portfolios, event landing pages, product showcase pages, simple tool pages, small game prototypes
- Rapidly validating design ideas and generating interactive demos
- Websites that require a simple back-end database and user system

**Not suitable for:**

- Complex websites with payment systems
- High-concurrency, high-availability formal production environments
- Business sites that require long-term stable hosting with a custom domain

---

If the above methods do not resolve your issue, please submit via the **User Feedback** button in the lower-right corner of the Kimi web/app, or [contact customer support](/others/contact-support). We recommend attaching:

- The website link where the issue occurred
- The browser and operating system you are using
- Screenshots or error message text
- The approximate time of the original conversation

We will continue to optimize website generation capabilities based on your feedback.
