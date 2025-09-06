# n8n-BFL-hackathon
06September2025, Creative AI hackathon submission repo



# This n8n template automates the creation of an AI-powered travel newsletter by analyzing trends and news, with a human-in-the-loop approval process.

## AI-Powered Travel Newsletter Automation (n8n Template)
This repository contains an n8n automation template designed to generate content for a travel newsletter. It automates the entire workflow from idea generation to content creation and visual storytelling.

How It Works
The workflow is broken down into the following automated steps:

Data Aggregation:

Scans Google Trends for trending travel topics in Germany and France.

Collects breaking airline news (e.g., fare discounts, new routes) and tourism updates (e.g., local events, demonstrations).

AI Content Generation:

An OpenAI model processes the aggregated data to generate a title, summary, and a compelling benefit (e.g., "Why you should consider this destination").

All generated content is saved to a primary table in Airtable, tagged with the week number and day for tracking.

Human-in-the-Loop (HITL) Approval:

The system sends an email notification via Outlook with the proposed destinations, allowing a human to review the content.

The user selects the most attractive destination, and this choice is updated in Airtable with a "selected" status.

Note: The Outlook node can easily be swapped for Gmail or another email service.

AI Image Storytelling:

Once a destination is marked as "selected," its data is sent to Flux Kontext.

Flux Kontext edits the source material and generates a series of images to create a visual story.

The newly created images are saved to a separate table in the same Airtable base, linked to the selected destination.

Technology Stack
Automation: n8n

Data Storage: Airtable

AI Content: OpenAI

Notifications (HITL): Outlook

Image Generation: Flux Kontext
