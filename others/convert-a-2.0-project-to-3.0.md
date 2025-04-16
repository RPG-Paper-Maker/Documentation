---
description: >-
  This page will describe how to convert a 2.0 project to the new 3.0 major
  version of RPG Paper Maker.
icon: rocket-launch
---

# Convert a 2.0 project to 3.0

## Upgrading your project to version 2.11.0

To begin, ensure your project is upgraded to version 2.11.0 using RPG Paper Maker 2.11.0. Download the latest version, open your project, and follow the prompts to convert it to the new version. This update includes essential improvements and features.

**RPG Paper Maker 3.0.0 requires your project to be at least version 2.11.0 before performing the upgrade.**

## Importing your project

Before importing your project into RPG Paper Maker 3.0.0, ensure your project directory is correctly structured. Verify that your 2.11.0 project folder contains the path `YourProjectName/resources/app/Content`. Follow these steps to prepare and import your project:

1. Compress the `Content` folder into a `.zip` archive. If necessary, download and use a tool like 7-Zip.
2. Rename the created `.zip` file from `Content.zip` to `YourProjectName.zip`.
3. Launch RPG Paper Maker 3.0.0 and click the "Import a project..." button.
4. Select the `YourProjectName.zip` file for import.
5. Accept the conversion prompt, if it appears, to complete the process.

## Manual changes needed

Certain manual updates might be necessary:

* **Local Plugins**: If you have plugins that are installed locally rather than through the online plugin manager, these won't be compatible with RPG Paper Maker 3.0.0. Check for any manual integration or updates required by the plugin creators.
* **Custom 3D Objects**: For any custom 3D objects in your project, ensure that the shapes are centered at the origin point (0,0,0). Misalignment may cause rendering issues in the updated version.
* **Special Characters**: If using the online version of RPG Paper Maker, it's important to remove any special characters before importing, such as `ñ`, from your project's file names and paths to avoid compatibility issues.

