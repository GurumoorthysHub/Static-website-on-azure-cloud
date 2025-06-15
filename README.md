# Deploying a Static Website to Azure Blob Storage

This project demonstrates how to host a simple static website (HTML, CSS, JavaScript) using Microsoft Azure Blob Storage. This method provides a cost-effective, scalable, and serverless way to serve web content.

## Project Overview

The primary goal of this project is to showcase the ability to:
*   Utilize Azure Blob Storage for static website hosting.
*   Configure Azure resources through the Azure Portal.
*   Understand the basic principles of serving web content from cloud storage.
*   Deploy simple front-end web assets (HTML, CSS, JS).

This repository contains the sample static website files that were deployed as part of this demonstration.

## Prerequisites

To replicate this deployment:
1.  An active Microsoft Azure subscription.
2.  Basic familiarity with the Azure Portal.
3.  Static website files (HTML, CSS, JavaScript). You can use the files in the `/website` directory of this repository as an example.

## Files in this Repository

*   **/website (or /src, /public_html):** This directory contains the source code for the sample static website.
    *   `index.html`: The main HTML page.
    *   `style.css` (if any): CSS for styling.
    *   `script.js` (if any): JavaScript for interactivity.
    *   `/images` (if any): Folder for image assets.
*   `README.md`: This file, providing an overview and deployment instructions.

## Deployment Steps to Azure Blob Storage

These steps outline how the static website (from the `/website` directory) was deployed to Azure Blob Storage:

1.  **Create an Azure Storage Account:**
    *   Log in to the Azure Portal.
    *   Navigate to "Storage accounts" and click "+ Create".
    *   Choose your subscription, resource group (create new or select existing).
    *   Provide a unique **Storage account name**.
    *   Select a **Region**.
    *   Choose **Performance** (Standard is usually fine for static sites).
    *   Choose **Redundancy** (LRS - Locally-redundant storage is often most cost-effective for this use case).
    *   Go to the "Advanced" tab and ensure "Enable hierarchical namespace" is **disabled** (unless you specifically need Azure Data Lake Storage Gen2 features, which isn't typical for basic static site hosting).
    *   Review and create the storage account.

2.  **Enable Static Website Hosting:**
    *   Once the storage account is deployed, navigate to it.
    *   In the left-hand menu, under "Data management," select "Static website."
    *   **Enable** the static website feature.
    *   Specify the **Index document name** (e.g., `index.html`).
    *   Optionally, specify an **Error document path** (e.g., `404.html`).
    *   Click "Save."
    *   Note the **Primary endpoint** URL provided. This will be your website's URL.

3.  **Upload Website Files:**
    *   After enabling static website hosting, a special container named `$web` will be automatically created.
    *   Navigate to "Containers" under "Data storage" in your storage account.
    *   Select the `$web` container.
    *   Upload all the files and folders from the `/website` directory of this repository into the `$web` container. Ensure you maintain the folder structure if you have subdirectories (like `/images`).

4.  **Access Your Website:**
    *   Open a web browser and navigate to the **Primary endpoint** URL you noted in Step 2.
    *   You should see your static website live!

## Azure Services Used
*   Microsoft Azure Blob Storage (specifically the static website hosting feature).
*   Azure Portal (for resource management and configuration).

## Key Learnings & Takeaways
*   Cost-effective and serverless approach to hosting static web content.
*   Ease of deployment and management via Azure Portal.
*   Understanding of how Azure Blob Storage can serve web assets directly.
*   Scalability benefits provided by Azure Storage.
