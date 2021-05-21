#### Experiments with Vault in k3s

Assuming you already installed the Token in your local config:

    $ export KUBECONFIG=~/.kube/config
    $ kubectl get nodes
    $ source <(kubectl completion bash)

Siehe Docker [Hub](https://hub.docker.com/_/vault).

    $ kubectl create namespace hello-vault
    $ kubectl config set-context --current --namespace=hello-vault
    $ kubectl apply -k k3s/

Then visit the [URL](https://vault.localhost).
