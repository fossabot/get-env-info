# get-env-info
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fkonveyor%2Fget-env-info.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fkonveyor%2Fget-env-info?ref=badge_shield)


Github action for getting environment information.  
Outputs useful information like go version and node version by reading files like go.mod and package.json

## Usage

```
steps:
- uses: actions/checkout@v2
- id: info
  uses: konveyor/get-env-info@v1
- uses: actions/setup-go@v2
  with:
    go-version: ${{ steps.info.outputs.go_version }} # The Go version to download (if necessary) and use.
- run: go version
```
```
steps:
- uses: actions/checkout@v2
- id: info
  uses: konveyor/get-env-info@v1
- uses: actions/setup-node@v1
  with:
    node-version: ${{ steps.info.outputs.node_version }}
- run: node --version
```

## Action Inputs

| Name | Description | Default |
| --- | --- | --- |
| `dir` | Path to the directory in which to look for go.mod, package.json, etc. | current directory |

## Action Outputs

| Name | Description |
| --- | --- |
| `go_version` | The version of Go mentioned in go.mod file. |
| `node_version` | The version of Node mentioned in package.json file under "engines": {"node":"vX.Y.Z"} |


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fkonveyor%2Fget-env-info.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fkonveyor%2Fget-env-info?ref=badge_large)