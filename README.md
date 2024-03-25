# Github Action to test a helm chart

## About

This action is designed to run a series of tests against the helm chart specified in `test_path`.

Tests included:

* Linting
* Build success
* Validation against the Kubernetes API (via [kubeconform](https://github.com/yannh/kubeconform))

## Usage

```workflow
...
  steps:
  - name: Test a Helm chart
    uses: launchbynttdata/actions-helm-test@v0
    with:
      test_path: path/to/test
      value_file: path/to/values.yaml
      kube_api_version: "1.2.3" #(optional: default 1.26.5)
...
```

To use this action, you need to provide the following input:

* `test_path`: The path to the test directory containing the chart to be tested.
* `value_file`: The path to the values file to be used for the test.
* `kube_api_version`: The version of the Kubernetes API to be used when validating the output of the helm templates. Optional, default: 1.26.5.

## Compatability

This action has only been tested on GitHub.com.
