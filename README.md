## Helm debug
```
helm lint chartdir
helm template chartdir
helm install --dry-run --debug --disable-openapi-validation mrelease mychart
```

## Helm chart package
https://medium.com/containerum/how-to-make-and-share-your-own-helm-package-50ae40f6c221
```
git clone https://github.com/gree-gorey/helm-example.git  #empty repo
cd helm-example
git checkout -b gh-pages

touch index.yaml
git add index.yaml
git commit -a -m "add index.yaml"
git push --set-upstream origin gh-pages

helm package my-app
mv my-app-0.1.0.tgz helm-example
helm repo index helm-example/ --url https://gree-gorey.github.io/helm-example/   ## see next

git commit -a -m "change index"
git push origin
```
```
helm repo add helm-example https://gree-gorey.github.io/helm-example
$ helm repo list
NAME            URL                                        
helm-example    https://gree-gorey.github.io/helm-example


$ helm install helm-example/my-app --name=my-app-name
```

```
$ cat helm-example/index.yaml 
apiVersion: v1
entries:
  my-app:
  - apiVersion: v1
    appVersion: "1.0"
    created: 2018-03-30T14:00:56.531328411Z
    description: A Helm chart for Kubernetes
    digest: 29089aabaa8aa08a03215098b1982ad38f6cd9de1c9b25ff842003a53cad881d
    name: my-app
    urls:
    - https://gree-gorey.github.io/helm-example/my-app-0.1.0.tgz
    version: 0.1.0
generated: 2018-03-30T14:00:56.530846921Z
```


# Jenkins Community Kubernetes Helm Charts

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

The code is provided as-is with no warranties.



## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```console
helm repo add jenkins https://charts.jenkins.io
```

You can then run `helm search repo jenkins` to see the charts.

<!-- Keep full URL links to repo files because this README syncs from main to gh-pages.  -->
Chart documentation is available in [jenkins directory](https://github.com/jenkinsci/helm-charts/blob/main/charts/jenkins/README.md).

## Contributing

<!-- Keep full URL links to repo files because this README syncs from main to gh-pages.  -->
We'd love to have you contribute! Please refer to our [contribution guidelines](https://github.com/jenkinsci/helm-charts/blob/main/CONTRIBUTING.md) for details.

## License

<!-- Keep full URL links to repo files because this README syncs from main to gh-pages.  -->
[Apache 2.0 License](https://github.com/jenkinsci/helm-charts/blob/main/LICENSE).
