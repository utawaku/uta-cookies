<img src="https://github.com/utawaku/uta-cookies/blob/main/public/assets/images/icon128.png?raw=true" align="right" width="128" height="128" title="Uta Cookies">

# Uta Cookies

Built with [catonaut](https://github.com/AminoffZ/catonaut), a browser extension builder with Astro and Bun

## 🚧 Before starting

Make sure you have some understanding of extension development. Here are some resources:

- [Chrome](https://developer.chrome.com/docs/extensions/mv3/getstarted/development-basics/)
- [Firefox](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension)
- Windows Users
  - Until [this](https://github.com/oven-sh/bun/issues/43) is resolved, Bun is not supported on Windows. [WSL](https://learn.microsoft.com/en-us/windows/wsl/install) is a workaround.
  - Or use the [Node.js + npm version](https://github.com/AminoffZ/catonaut-node) of this template

## Setup

### Get project

Get project

```bash
git clone https://github.com/utawaku/uta-cookies.git
```

or using github CLI

```bash
gh repo clone utawaku/uta-cookies
```

### Install dependencies

Install dependencies using bun

```bash
bun i
```

### Changing the icon

You can generate the icons from an image.

1. Replace the public/assets/images/example.png
2. Run the following command in the terminal:

```bash
bun run icons
```

This will create the icons referenced by default in the manifest of sizes 16, 32, 48 and 128.

### Testing the popup

You can test the popup by running the following command in the terminal:

```bash
bun run dev
```

This will start a development server and open the popup in your browser as if it were a website. You can then modify the popup and see the changes in real time.

## Testing your extension

Thankfully you don't have to get your extension published before being able to test it. Refer to [**Before starting**](https://github.com/AminoffZ/catonaut/tree/main#-before-starting) for information about testing an extension, also referred to as loading unpacked extensions. You do however need to build the extension to be able to test it.

## Build

To build the extension, run:

```bash
bun run build
```

## 🏗️ Project structure

<pre>
root
├── 📁 build-tools
├── 📁 dist
├── 📁 public
└── 📁 src
    ├── 📁 pages
    └── 📁 scripts
        └── 📁 internal
</pre>

### build-tools

Contains tools used for building the extension. You should not need to modify anything in this folder.

### dist

Contains the built extension. This folder can be loaded as an unpacked extension.

### public

Contains the public files. This folder is copied to the dist folder when building the extension. The files are not modified in any way.

### src

Contains the source files. This is where you will be doing most of your work.

### src/pages

Contains the index.astro. This is compiled to HTML when building the extension and functions as the popup. I find adding a folder src/components/ and importing them in the index.astro to be a good way to structure the popup.

### src/scripts

Contains the content.ts and background.ts. These are compiled to JavaScript when building the extension. The content.ts is injected into the DOM of the page.

### src/scripts/internal

Not necessary although I find that a useful way to structure the scripts is to add files in this folder and import their functionality in the content.ts and background.ts.

## Formatting

```bash
bun run format
```
