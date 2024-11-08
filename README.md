# Terraform-Module-Automation

*work in progress*

**Overview**

The Terraform-Module-Automation project is designed to streamline the management of Terraform modules by automating the generation of documentation. This project employs terraform-docs, a utility that generates documentation from Terraform modules in various output formats, including Markdown. This README serves as a comprehensive guide for users to understand the project's purpose, installation, usage, and contribution guidelines.

**Features**

Automated Documentation: Automatically generates a README.md file with module documentation.
GitHub Actions Integration: Seamlessly integrates with GitHub Actions for continuous documentation updates.
Customizable Output: Supports various output formats and customization options.

Requirements

Terraform version 1.0 or higher.
GitHub account for accessing GitHub Actions.
Basic knowledge of Terraform and GitHub workflows.

Installation

Clone the repository:

git clone https://github.com/PournimaTivatane12/Terraform-Module-Automation
cd Terraform-Module-Automation

Install terraform-docs using Homebrew (for macOS users):

brew install terraform-docs

Alternatively, you can download the binary from the terraform-docs GitHub repository and install it manually.

**Usage**

Generating Documentation

To generate documentation for your Terraform module, run the following command:

terraform-docs markdown table --output-file README.md --output-mode inject /path/to/module
This command will create or update a README.md file in the specified module directory.

GitHub Actions Workflow

To automate the documentation generation using GitHub Actions, create a workflow file .github/workflows/generate-docs.yml with the following content:

name: Generate Terraform Docs

on:
  push:
    branches:
      - master

jobs:
  docs:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      
      - name: Generate Terraform documentation
        uses: terraform-docs/gh-actions@v1.0.0
        with:
          find-dir: .
          output-file: README.md
          output-method: inject
          git-push: 'true'

This workflow triggers on every push to the master branch, automatically generating and updating the README.md file.

**Contributing**

Contributions are welcome! If you would like to contribute to this project, please follow these steps:


Fork the repository.

Create a new branch for your feature or bug fix.

Make your changes and commit them.

Push your changes to your forked repository.

Create a pull request detailing your changes.

**License**

This project is licensed under the MIT License - see the LICENSE file for details.

**Acknowledgments**

Thanks to the contributors of terraform-docs for providing an invaluable tool for automating Terraform documentation.
Special thanks to the community members who have shared their insights and improvements on automating documentation processes.
This README provides a structured overview of the Terraform-Module-Automation project, highlighting its purpose, features, and how to get started with it effectively.

