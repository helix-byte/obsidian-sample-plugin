# Obsidian Sample Plugin

This is a project based on the official Obsidian sample plugin template, but it is currently in an initial state with significant differences from the original sample repository.

## Project Status Description

**Current Status:** This is an empty plugin template project with no actual functionality implemented yet.

**Main Differences from the Original Sample Repository:**

### 1. Missing Core Functionality Code
- **Original Sample Repository:** Contains a complete `main.ts` file that implements the following features:
  - Adds a ribbon icon that shows a notice when clicked
  - Adds an "Open Sample Modal" command
  - Adds a plugin settings tab
  - Registers a global click event and outputs 'click' to the console
  - Registers a global interval that logs 'setInterval' to the console
- **Current Repository:** The `main.ts` file is empty, with no plugin functionality implemented

### 2. Configuration File Differences

#### manifest.json Configuration
- **Original Sample Repository:** Contains complete plugin information such as name, description, author, etc.
- **Current Repository:** Most fields are empty:
  ```json
  {
    "description": "",
    "author": "",
    "authorUrl": "",
    "fundingUrl": ""
  }
  ```

#### package.json Configuration
- **Version Information:** Current version is "0.1.0", consistent with the original sample repository
- **Dependency Management:** Development dependencies are fully configured, including TypeScript, ESLint, esbuild, and other tools
- **Script Configuration:** Build scripts are fully configured, supporting development, building, and version management

### 3. Build Configuration

#### TypeScript Configuration (tsconfig.json)
- **Target Version:** ES6 (consistent with the original sample repository)
- **Module System:** ESNext (consistent with the original sample repository)
- **Strict Mode:** Strict mode options such as strict null checks are enabled

#### esbuild Configuration (esbuild.config.mjs)
- **Build Target:** ES2018 (consistent with the original sample repository)
- **External Dependencies:** Complete Obsidian API and CodeMirror module configuration
- **Source Mapping:** Inline source mapping enabled in development mode

### 4. Project Structure Completeness

**Completely Preserved Components:**
- ✅ Build configuration file (esbuild.config.mjs)
- ✅ TypeScript configuration (tsconfig.json)
- ✅ Package management configuration (package.json)
- ✅ Plugin manifest (manifest.json)
- ✅ Version management script (version-bump.mjs)
- ✅ Style file (styles.css)
- ✅ ESLint configuration (.eslintrc, .eslintignore)
- ✅ Git ignore file (.gitignore)
- ✅ Editor configuration (.editorconfig)

**Missing or Needing Improvement:**
- ❌ Main functionality code (main.ts is empty)
- ❌ Plugin description information
- ❌ Author information
- ❌ Funding support links

## Development Guide

### Environment Requirements
- Node.js v16 or higher
- Obsidian desktop application

### Quick Start

1. **Install Dependencies**
   ```bash
   npm install
   ```

2. **Development Mode Compilation**
   ```bash
   npm run dev
   ```

3. **Plugin Installation**
   - Copy the generated `main.js`, `styles.css`, `manifest.json` to the `.obsidian/plugins/sample-plugin/` directory in your Obsidian vault
   - Or enable community plugins in Obsidian settings and use this directory as the plugin development directory

### Development Workflow

1. **Write Code:** Implement plugin functionality in `main.ts`
2. **Auto Compilation:** After running `npm run dev`, code changes are automatically compiled to `main.js`
3. **Test Plugin:** Reload Obsidian or re-enable the plugin to test changes
4. **Code Quality:** Use ESLint to check code quality
   ```bash
   eslint main.ts
   ```

## Feature Comparison with Original Sample Repository

| Feature | Original Sample Repository | Current Repository | Status |
|---------|----------------------------|-------------------|---------|
| Ribbon Icon | ✅ | ❌ | Needs Implementation |
| Command System | ✅ | ❌ | Needs Implementation |
| Settings Page | ✅ | ❌ | Needs Implementation |
| Global Event Listening | ✅ | ❌ | Needs Implementation |
| Timer Functionality | ✅ | ❌ | Needs Implementation |
| Modal | ✅ | ❌ | Needs Implementation |
| TypeScript Configuration | ✅ | ✅ | Configured |
| Build System | ✅ | ✅ | Configured |
| ESLint Integration | ✅ | ✅ | Configured |

## Next Steps Development Suggestions

1. **Implement Basic Functionality:** Reference the original sample repository to implement basic plugin classes and functionality in `main.ts`
2. **Complete Metadata:** Add plugin description, author information, etc. in `manifest.json`
3. **Add Feature Features:** Add custom functionality according to requirements
4. **Test Verification:** Ensure all functionality works properly
5. **Version Release:** Prepare plugin release according to the release process

## Release Guide

When plugin development is complete, you can release it following these steps:

1. **Update Version Information**
   ```bash
   npm version patch  # or minor/major
   ```

2. **Build Production Version**
   ```bash
   npm run build
   ```

3. **Create GitHub Release**
   - Use the version number as the tag
   - Upload `manifest.json`, `main.js`, `styles.css` files

4. **Submit to Community Plugin List**
   - Ensure compliance with [plugin guidelines](https://docs.obsidian.md/Plugins/Releasing/Plugin+guidelines)
   - Create a Pull Request at [obsidian-releases](https://github.com/obsidianmd/obsidian-releases)

## API Documentation

For detailed Obsidian API documentation, please refer to: https://github.com/obsidianmd/obsidian-api

## Summary

The current project provides a complete Obsidian plugin development environment configuration but lacks actual plugin functionality implementation. Developers can use this template to quickly start plugin development, referencing the original sample repository's functionality implementation to build their own plugin features.

## First time developing plugins?

Quick starting guide for new plugin devs:

- Check if [someone already developed a plugin for what you want](https://obsidian.md/plugins)! There might be an existing plugin similar enough that you can partner up with.
- Make a copy of this repo as a template with the "Use this template" button (login to GitHub if you don't see it).
- Clone your repo to a local development folder. For convenience, you can place this folder in your `.obsidian/plugins/your-plugin-name` folder.
- Install NodeJS, then run `npm i` in the command line under your repo folder.
- Run `npm run dev` to compile your plugin from `main.ts` to `main.js`.
- Make changes to `main.ts` (or create new `.ts` files). Those changes should be automatically compiled into `main.js`.
- Reload Obsidian to load the new version of your plugin.
- Enable plugin in settings window.
- For updates to the Obsidian API run `npm update` in the command line under your repo folder.

## Releasing new releases

- Update your `manifest.json` with your new version number, such as `1.0.1`, and the minimum Obsidian version required for your latest release.
- Update your `versions.json` file with `"new-plugin-version": "minimum-obsidian-version"` so older versions of Obsidian can download an older version of your plugin that's compatible.
- Create new GitHub release using your new version number as the "Tag version". Use the exact version number, don't include a prefix `v`. See here for an example: https://github.com/obsidianmd/obsidian-sample-plugin/releases
- Upload the files `manifest.json`, `main.js`, `styles.css` as binary attachments. Note: The manifest.json file must be in two places, first the root path of your repository and also in the release.
- Publish the release.

> You can simplify the version bump process by running `npm version patch`, `npm version minor` or `npm version major` after updating `minAppVersion` manually in `manifest.json`.
> The command will bump version in `manifest.json` and `package.json`, and add the entry for the new version to `versions.json`

## Adding your plugin to the community plugin list

- Check the [plugin guidelines](https://docs.obsidian.md/Plugins/Releasing/Plugin+guidelines).
- Publish an initial version.
- Make sure you have a `README.md` file in the root of your repo.
- Make a pull request at https://github.com/obsidianmd/obsidian-releases to add your plugin.

## How to use

- Clone this repo.
- Make sure your NodeJS is at least v16 (`node --version`).
- `npm i` or `yarn` to install dependencies.
- `npm run dev` to start compilation in watch mode.

## Manually installing the plugin

- Copy over `main.js`, `styles.css`, `manifest.json` to your vault `VaultFolder/.obsidian/plugins/your-plugin-id/`.

## Improve code quality with eslint (optional)
- [ESLint](https://eslint.org/) is a tool that analyzes your code to quickly find problems. You can run ESLint against your plugin to find common bugs and ways to improve your code. 
- To use eslint with this project, make sure to install eslint from terminal:
  - `npm install -g eslint`
- To use eslint to analyze this project use this command:
  - `eslint main.ts`
  - eslint will then create a report with suggestions for code improvement by file and line number.
- If your source code is in a folder, such as `src`, you can use eslint with this command to analyze all files in that folder:
  - `eslint .\src\`

## Funding URL

You can include funding URLs where people who use your plugin can financially support it.

The simple way is to set the `fundingUrl` field to your link in your `manifest.json` file:

```json
{
    "fundingUrl": "https://buymeacoffee.com"
}
```

If you have multiple URLs, you can also do:

```json
{
    "fundingUrl": {
        "Buy Me a Coffee": "https://buymeacoffee.com",
        "GitHub Sponsor": "https://github.com/sponsors",
        "Patreon": "https://www.patreon.com/"
    }
}
```

## API Documentation

See https://github.com/obsidianmd/obsidian-api
