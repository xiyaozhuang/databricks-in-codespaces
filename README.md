# How to setup Databricks on VS Code

**IMPORTANT**

- Sync as of 16/06/23 is only in one direction: LOCAL to REMOTE.
- Changes from LOCAL are pushed to REMOTE on FILE SAVE with sync running.
- Therefore, any changes made on REMOTE will always be OVERWRITTEN by LOCAL.

> This guide assumes that VS Code and Python is installed on your local machine and is a condensed version of: https://docs.databricks.com/dev-tools/vscode-ext.html

## Installation

Navigate to the the extensions tab in the left sidebar and install the Databricks extension for VS Code.

> Make sure this is the official extension by checking there is a blue tick next to the publisher name.

## Configuration

After installing the extension navigate to the Databricks tab in the left sidebar.

1. Click the configure button and paste in the `host URL`.

2. Click `Edit Databricks profiles` to open your Databricks configuration profiles file and fill in the following information:

   ```
   [<some-unique-name-for-this-configuration-profile>]
   host = <host-url>
   username = <email-address>
   password = <password>
   ```

   An example configuration profile would look like:

   ```
   [ACCOUNT]
   host = https://example.cloud.databricks.com
   username = user@example.com
   password = ********
   ```

3. Click the gear icon next to `Cluster` to attach a cluster

4. Click the gear icon next to `Sync Destination` to select or create a folder to sync your local files to.

5. Create a Python file and run your code by opening the drop-down next to the play button and selecting `Upload file and run on Databricks`.

That's it! Your code will run on the attached cluster and outputs will be displayed in the debug console.

## Optional QOL improvements

To enable IntelliSense, open the `Command Palette` (ctrl + shift + p) and find `Databricks: Configure autocomplete for Databricks globals` and press Enter.

Follow the on-screen prompt to install PySpark for your project, and to add or modify the `__builtins__.pyi` file for your project to enable Databricks Utilities.
