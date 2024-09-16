## About
Create butiful folder structure diagrams and embed them into your README.md

## Usage

Add this to your readme
> ```md
> <!---BETTER_FILES_TREE-->
> CODE_BLOCK
> ```
and then running the better tree will insert the project structure into that CODE_BLOCK.

### The various arguments are:

| **Parameter**         | **Description**                                                                       | **Optional/Mandatory** |
|-----------------------|---------------------------------------------------------------------------------------|------------------------|
| `GITHUB_TOKEN`        | Your GitHub tokens.                                                                   | Mandatory              |
| `root`                | The directory, folder of which is to be drawn.                                        | Optional               |
| `doc`                 | Path to `README.md`.                                                                  | Optional               |
| `auto-doc`            | If `true`, the program will find `README.md` from the root directory.                 | Optional               |
| `no-files`            | If `true`, only folders will be drawn.                                                | Optional               |
| `stack-folders`       | If `true`, folders/files will be stacked in case of a single child.                   | Optional               |
| `show-hidden`         | If `true`, hidden folders/files will also be rendered.                                | Optional               |
| `ignored-locations`   | List of paths that will be ignored while rendering.                                   | Optional               |

## Example Usage
```yml
name: Generate Folder 

on:
  push:
    branches: [ "master", "main" ]
  pull_request:
    branches: [ "master", "main" ]
  workflow_dispatch:

jobs:
  setup:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Magic
        uses: MRfantastic3DGamer/Better-Tree-Action@v1.0
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          root: "./"
          auto-doc: true
          ignored-locations: "./gradle"
```