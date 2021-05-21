#### Experiments with Vault in k3s

Assuming you already installed the Token in your local config:

    $ export KUBECONFIG=~/.kube/config
    $ kubectl get nodes
    $ source <(kubectl completion bash)

Siehe Docker [Hub](https://hub.docker.com/_/vault).

    $ kubectl create namespace hello-vault
    $ kubectl config set-context --current --namespace=hello-vault
    $ kubectl apply -k k3s/

For the server in Dev-mode check the Logs for the token:

    $ kubectl logs pod/vault-server-xxx

then visit the [URL](https://vault.localhost) or from the CLI:

    $ VAULT_ADDR=http://vault.localhost
    $ VAULT_TOKEN=...
    $ vault status

Default is to use KV Secret Engine v2, cf ``version:2`` in the list of
mounts:

    $ vault read sys/mounts

So  you probably  want to  get  used to  kv put/get  workflow that  is
supposed to work the same for v1 and v2 KB Stores:

    $ vault kv put secret/foo user=admin password=hunter4
    $ vault kv get secret/foo
