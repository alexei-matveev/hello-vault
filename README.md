#### Experiments with Metabase in k3s

Assuming you already installed the Token in your local config:

    $ export KUBECONFIG=~/.kube/config
    $ kubectl get nodes
    $ source <(kubectl completion bash)

Siehe [Releases](https://github.com/metabase/metabase/releases).

    $ kubectl create namespace hello-metabase
    $ kubectl config set-context --current --namespace=hello-metabase
    $ kubectl apply -k k3s/

Then visit the [URL](https://metabase.localhost).
