# Project Snapshot JSONifier (psj)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> Serialize codebases into AI-ready JSON with a single command

`psj` recursively scans project directories and outputs their complete structure + content as well-formatted JSON. Perfect for feeding codebases to AI systems, documentation tools, or analysis pipelines.

## Features
- 🚀 Recursive directory scanning
- 📁 File content embedding (base64-safe)
- ⚡️ Short mode for minimal output
- 🚫 Exclude patterns (multiple `-x` supported)
- 📦 Zero dependencies (only requires `jq`)

## Installation
```bash
# Download + make executable
curl -L https://raw.githubusercontent.com/scr0lll0ck1s4b0v3h0m3k3y/psj/main/psj.sh > psj
chmod +x psj
sudo mv psj /usr/local/bin/  # Optional: install globally
```


## Usage
```bash
# Basic usage (current directory)
psj

# Specify target directory
psj path/to/project

# Short mode (minimal fields)
psj -s

# Exclude files/directories
psj -x ".git" -x "node_modules" -x "*.log"
```

## Output Structure
```json
{
  "name": "project-root",
  "type": "directory",
  "path": "/full/path",
  "children": [
    {
      "name": "index.js",
      "type": "file",
      "path": "/full/path/index.js",
      "content": "console.log('Hello World!');\n"
    },
    {
      "name": "src",
      "type": "directory",
      "path": "/full/path/src",
      "children": [...]
    }
  ]
}
```

## Use Cases
1. **AI Context Injection**  
   Feed entire projects to LLMs like ChatGPT/Gemini for analysis
2. **Codebase Documentation**  
   Generate automatic project inventories
3. **Project Differ**  
   Compare codebase snapshots over time
4. **CLI Tool Integration**  
   Pipe into custom analysis scripts


---
> ⚠️ **Full Transparency Warning**  
> *Look, this entire util was vibe-coded using AI because I'm lazy lol.  
> But it works and I know what I'm doing (sometimes) xD  
> If it breaks... ¯\\\_(ツ)_/¯ just submit a PR or something*

