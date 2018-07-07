# kubectl-decode-secret

## About

### Description
A kubectl plugin to decode Kubernetes secrets

### Installation
Add `kubectl-decode-secret` to your `kubectl` plugins directory. For more information about how plugins are loaded, please see the [official documentation](https://kubernetes.io/docs/tasks/extend-kubectl/kubectl-plugins/).
```
git clone git@github.com:brosandilabs/kubectl-decode-secret.git ~/.kube/plugins/kubectl-decode-secret
```

### Dependencies
* docker - since this plugin relies on functionality only availale in `jq` 1.6-rc1, a custom docker image is used to execute `jq`

### Usage
```
> kubectl plugin decode-secret --help
decode-secret allows users to view decoded kubernetes secrets

Usage:
  kubectl plugin decode-secret [flags] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
```

### Examples
Decode content of 'my-secret' in 'default' namespace:
```
kubectl plugin decode-secret my-secret
```

Decode content of 'my-secret' in 'custom' namespace:
```
kubectl plugin decode-secret my-secret -n custom
```
