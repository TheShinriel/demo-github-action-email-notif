# Email Notification CI/CD Pipeline

This repository demonstrates the use of a Continuous Integration and Continuous Deployment (CI/CD) pipeline using GitHub Actions to send email notifications via SendGrid whenever changes are pushed to the `main` branch.

## Overview

The GitHub Actions workflow in this repository is configured to trigger an email notification using SendGrid's email delivery service. This can be particularly useful for updates about the project's progress, alerts, or even automated reports directly from your repository.

## Workflow

The workflow is triggered on every push to the `main` branch. It runs on an Ubuntu latest environment and utilizes the `peter-evans/sendgrid-action` to handle email dispatch.

## Setup

### Prerequisites

- A GitHub account.
- A repository where this workflow can be implemented.
- A SendGrid account with an API key.

### Configuration

1. **SendGrid API Key**: Obtain an API key from SendGrid which allows you to send emails through their platform. This key should be stored securely in your repository's secrets as `SENDGRID_API_KEY`.

### Adding the Workflow to Your Repo

To implement this workflow in your repository, please follow these steps:

1. Create a `.github/workflows` directory in your repository if one does not already exist.
2. Add a new file named `email-notification.yml`.
3. Copy and paste the YAML content from above into this file.
4. Set up your repository's secrets with your `SENDGRID_API_KEY` securely stored.
5. Do the same for `EMAIL_TO` and `EMAIL_FROM`

## Usage

With the setup complete, the workflow will automatically send an email via SendGrid each time changes are pushed to the `main` branch. The specifics of the email, such as recipients, subject, and body, should be defined within your SendGrid templates or within the action's usage parameters.

## Customization

You can customize this workflow by:

- Changing the branches that trigger the workflow.
- Modifying or adding steps to perform before sending an email, such as running tests or compiling reports.
- Adjusting the email content or adding additional SendGrid API features.

## Support

For more details on configuring and using the `peter-evans/sendgrid-action`, refer to the [official action documentation on GitHub](https://github.com/peter-evans/sendgrid-action).
