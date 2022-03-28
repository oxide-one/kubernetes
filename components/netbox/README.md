# Netbox

I didn't like that there were no netbox kustomize files, so I made this one.
This (fairly) accurately maps the docker-compose stuff into an actual deployment.

It omits the volume mounts, and should work fine.

# Usage

If you want to use it, feel free to! I can't promise it won't drasticly change.

Grab the env file and chuck it in the same place as the kustomization.yaml

```yaml
# kustomization.yaml
resources:
- github.com/oxide-one/kubernetes/components/netbox

secretGenerator:
- name: netbox-secrets
  envs: 
  # This is whatever you named the env file
  - secret.env
  behavior: create

```
