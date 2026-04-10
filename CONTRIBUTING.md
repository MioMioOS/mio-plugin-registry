# Contributing to MioIsland Plugin Registry

Thank you for building a plugin for MioIsland! Follow these steps to submit your plugin.

## Prerequisites

- A GitHub account
- Your plugin, built from [mio-plugin-template](https://github.com/MioMioOS/mio-plugin-template)
- Familiarity with Git and pull requests

## Step-by-step submission guide

### 1. Build your plugin

Fork [mio-plugin-template](https://github.com/MioMioOS/mio-plugin-template) and follow its README to create your plugin. Make sure your `plugin.json` is valid and contains all required fields.

### 2. Fork this registry repo

Go to [mio-plugin-registry](https://github.com/MioMioOS/mio-plugin-registry) and click **Fork**.

### 3. Clone your fork

```bash
git clone https://github.com/<your-username>/mio-plugin-registry.git
cd mio-plugin-registry
```

### 4. Create a branch

```bash
git checkout -b add-plugin/<your-plugin-id>
```

### 5. Add your plugin directory

Place your plugin files under the correct type directory:

```
plugins/
  themes/<your-plugin-id>/
    plugin.json
    preview.png       (optional, recommended)
    ...
  buddies/<your-plugin-id>/
    plugin.json
    ...
  sounds/<your-plugin-id>/
    plugin.json
    ...
```

Your `plugin.json` must include these required fields:

```json
{
  "type": "theme",
  "id": "your-plugin-id",
  "name": "Your Plugin Name",
  "version": "1.0.0",
  "author": {
    "name": "Your Name"
  }
}
```

### 6. Commit and push

```bash
git add plugins/<type>/<your-plugin-id>/
git commit -m "Add <your-plugin-id> plugin"
git push origin add-plugin/<your-plugin-id>
```

### 7. Open a pull request

Go to your fork on GitHub and open a pull request against `main` of this repo.

CI will automatically:
- Check that `plugin.json` exists in your plugin directory
- Validate JSON syntax
- Verify all required fields are present

### 8. Wait for review

A maintainer will review your submission. You may be asked to make changes. Once approved and merged, your plugin will be published to the registry automatically.

## Review criteria

- **plugin.json** must be valid JSON with all required fields
- **id** must be unique and use kebab-case
- **version** must follow semver
- **No malicious content** — plugins are reviewed for safety
- **Preview image** is recommended for themes and buddies

## Updating an existing plugin

To update a plugin you previously submitted, follow the same process: fork, branch, update the files in your plugin directory (bump the version), and open a PR.

## Questions?

Open an issue in this repo if you need help.
