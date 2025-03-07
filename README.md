# github-workflow-release-tagger-for-github-workflows

In GitHub actions, the major version tags should be automatically updated when
there is a new release so that major version referenced in workflows can use
the latest version.

The recommendation is to update only the major tag:
https://github.com/actions/toolkit/blob/main/docs/action-versioning.md


## Configuring your repository

You can change settings in the repository by manipulating configuration file in
`.pallet/gitconfig.yaml`

The full definition of the api can be found [here][gitconfig-api-ref]

CI of the changes in the repositoryconfig is not configured yet. For now, you
can use the [argocd app status][argocd-app-ref] to find the status and
potential errors.


[gitconfig-api-ref]: https://github.com/coopnorge/cloud-platform-apis/blob/main/cloud-platform-apis/templates/repositoryconfig.github.coop.no/definition.yaml
[argocd-app-ref]:  https://argocd.internal.coop/applications?search=pallet-github-workflow-release-tagger-for-github-workflows&showFavorites=false&proj=&sync=&autoSync=&health=&namespace=&cluster=&labels=
