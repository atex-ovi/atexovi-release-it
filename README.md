<h1 align="center">atexovi-release-it 🚀</h1>

<p align="center">
  <a href="https://nodejs.org/">
    <img src="https://img.shields.io/badge/Node.js-20+-339933?style=flat-square&logo=node.js&logoColor=white" alt="Node.js">
</a>
  <a href="https://github.com/atex-ovi/atexovi-release-it/stargazers">
    <img src="https://img.shields.io/github/stars/atex-ovi/atexovi-release-it?style=flat-square&logo=github&color=000000&logoColor=ffffff" alt="GitHub stars">
  </a>
  <a href="https://github.com/atex-ovi/atexovi-release-it/network/members">
    <img src="https://img.shields.io/github/forks/atex-ovi/atexovi-release-it?style=flat-square&logo=github&color=000000&logoColor=ffffff" alt="GitHub forks">
  </a>
  <a href="https://termux.com/">
    <img src="https://img.shields.io/badge/Termux-0.119.0-3DDC84?style=flat&logo=android&logoColor=white" alt="Termux / Android">
  </a>
</p>

<p align="center">
  <a href="https://saweria.co/atexovi">
    <img src="https://img.shields.io/badge/Saweria-FFA726?style=flat&logo=ko-fi&logoColor=white" alt="Saweria">
  </a>
  <a href="https://facebook.com/atex.ovi">
    <img src="https://img.shields.io/badge/Facebook-1877F2?style=flat-square&logo=facebook&logoColor=white" alt="Facebook">
  </a>
  <a href="https://t.me/atexovi">
    <img src="https://img.shields.io/badge/Telegram-26A5E4?style=flat-square&logo=telegram&logoColor=white" alt="Telegram">
  </a>
</p>

<p align="center">
  Lightweight script for <strong>automating releases and versioning</strong> using release-it, modified for <strong>Node.js 20+</strong>.
</p>

<br>

## Features
- Automatically bump version (`package.json`)  
- Commit, tag, and push to Git  
- Create GitHub/GitLab releases  
- Generate simple changelog  
- Run hooks before/during/after release  

> [!NOTE]
> This version **only supports Node.js 20 and above**.  

<br>

## Installation
```bash
npm install --save-dev atexovi-release-it
```

Add a script to `package.json`:

```bash
{
  "scripts": {
    "release": "atexovi-release-it"
  }
}
```
<br>

## Usage
Run from the project root:

```bash
npm run release
# or
npx atexovi-release-it
```
<br>

## The process

When running `atexovi-release-it`, the process will:

1. Ensure a clean working tree
2. Determine release type (patch/minor/major)
3. Update version & commit automatically
4. Tag Git and push to remote
5. Generate changelog

<br>

## Configuration

Add a `.release-it.json` file if you want to customize the behavior:

```json
{
  "git": {
    "commitMessage": "chore: release v${version}"
  },
  "github": {
    "release": true
  },
  "hooks": {
    "after:bump": "npm run build"
  }
}
```
<br>

## CI Mode

Use `--ci` for non-interactive mode, suitable for CI/CD pipelines:

```bash
npx atexovi-release-it --ci
```
<br>

## License
[MIT](LICENSE)
