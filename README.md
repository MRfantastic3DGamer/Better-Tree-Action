## About
Create butiful folder structure diagrams and embed them into your README.md

## Usage

> Add this to your readme
> <!---BETTER_FILES_TREE-->
> ```something```
> and then running the better tree will insert the project structure into that code block.


#### The various arguments are:

GITHUB_TOKEN
*root*: the directory, folder of which is to be drawn

*doc*: [optional] path to README.md

*auto-doc*: [optional] if true then we will find README.md from root directory

*no-files*: [optional] if true then only folders will be drawn

*stack-folders*: [optional] if true then folders/files will be stacked in case of single child

*show-hiden*: [optional] if true then hidden folders/files will also be rendered

*ignored-locations*: [optional] list of paths that will be ignored while rendering


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