# Tanzu Mission Control CD Demo

## Enable GitOps

1. Create a `Cluster group` in TMC
1. Enable Continuous Delivery in the `Cluster group`
   * `Actions` > `Enable continuous delivery`
   * (Optional) `Actions` > `Enable Helm service`
1. Go to `Add-ons` > `Git repositories` to add the git repo:
   * Repository name: `tmc-git-repo` (must be exactly this due to what is in the gitops repo)
   * Repository URL: `https://github.com/mbentley/tmc-poc.git`
   * Repository credential: `No credentials needed`
   * Advanced Settings > Branch: `main`
1. Go to `Installed kustomizations` to add the kustomization to use:
   * Kustomization name: `demo-clustergroup-prod`
   * Repository: `tmc-git-repo`
   * Path: `/environments/demo-clustergroup-prod`
   * Advanced settings > Prune: `enable`
1. Add a cluster to the Cluster Group and wait for reconciliation.
