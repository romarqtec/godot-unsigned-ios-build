# Build Your Godot Project for iOS Without a Mac 🚀

[![Download Releases](https://img.shields.io/badge/Download_Releases-brightgreen.svg)](https://github.com/romarqtec/godot-unsigned-ios-build/releases)

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository provides a ready-to-use GitHub Action script for building a Godot project for iOS. It enables you to create an iOS build without requiring access to a Mac. This means you can streamline your development process and save time while ensuring your Godot projects are ready for deployment on iOS devices.

## Features

- **No Mac Required**: Build your Godot project for iOS directly from GitHub Actions.
- **Seamless Integration**: Easy integration with your existing CI/CD pipeline.
- **Supports Godot 4**: Built specifically for Godot 4, ensuring compatibility with the latest features.
- **Unsigned IPA**: Generate unsigned IPA files suitable for sideloading.
- **Xcode Build Support**: Leverage Xcode build tools without needing a Mac.

## Getting Started

To get started with the Godot Unsigned iOS Build Action, follow these steps:

1. **Fork this Repository**: Click on the "Fork" button at the top right corner of this page to create your own copy of the repository.
2. **Clone Your Fork**: Use the following command to clone your forked repository:

   ```bash
   git clone https://github.com/YOUR_USERNAME/godot-unsigned-ios-build.git
   ```

3. **Navigate to Your Project Directory**:

   ```bash
   cd godot-unsigned-ios-build
   ```

4. **Download the Latest Release**: Visit the [Releases](https://github.com/romarqtec/godot-unsigned-ios-build/releases) section to download the latest version of the script. Follow the instructions provided there to execute the script.

## Usage

To use the GitHub Action in your own repository, you need to create a workflow file. Here’s a simple example of how to set it up:

1. **Create a Workflow File**: In your repository, create a directory called `.github/workflows`. Inside that directory, create a file named `ios-build.yml`.

2. **Add the Following Configuration**:

   ```yaml
   name: Build iOS

   on:
     push:
       branches:
         - main

   jobs:
     build:
       runs-on: ubuntu-latest

       steps:
       - name: Checkout Code
         uses: actions/checkout@v2

       - name: Build iOS
         uses: romarqtec/godot-unsigned-ios-build@main
         with:
           godot_version: '4.0'
           project_path: './your_project_path'
   ```

3. **Customize the Configuration**: Replace `your_project_path` with the path to your Godot project. You can also specify the Godot version if needed.

4. **Commit and Push**: Save your changes, commit them, and push to your GitHub repository.

5. **Trigger the Action**: The action will run automatically on pushes to the `main` branch. You can check the progress in the "Actions" tab of your repository.

## Configuration

You can customize the GitHub Action by modifying the input parameters. Here are some options you can set:

- **godot_version**: Specify the version of Godot to use (default is `4.0`).
- **project_path**: Path to your Godot project relative to the root of the repository.
- **output_directory**: Directory where the unsigned IPA will be saved (default is `./build`).

Example:

```yaml
- name: Build iOS
  uses: romarqtec/godot-unsigned-ios-build@main
  with:
    godot_version: '4.0'
    project_path: './your_project_path'
    output_directory: './output'
```

## Troubleshooting

If you encounter issues during the build process, consider the following tips:

- **Check Logs**: Review the logs in the Actions tab for any error messages.
- **Validate Paths**: Ensure that the paths specified in your workflow file are correct.
- **Dependencies**: Make sure all necessary dependencies are included in your Godot project.
- **GitHub Actions Status**: Sometimes, GitHub Actions may experience outages. Check the [GitHub Status Page](https://www.githubstatus.com/) for updates.

## Contributing

Contributions are welcome! If you have suggestions or improvements, please feel free to submit a pull request. Here’s how you can contribute:

1. **Fork the Repository**: Create your own copy of the repository.
2. **Create a Branch**: Use a descriptive name for your branch.
   
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Your Changes**: Implement your feature or fix.
4. **Commit Your Changes**:

   ```bash
   git commit -m "Add your message here"
   ```

5. **Push to Your Fork**:

   ```bash
   git push origin feature/your-feature-name
   ```

6. **Open a Pull Request**: Go to the original repository and click on "New Pull Request".

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

For more information and updates, visit the [Releases](https://github.com/romarqtec/godot-unsigned-ios-build/releases) section.