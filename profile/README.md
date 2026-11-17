<div align="center">

# Bunch Webhost
**TLDR: Six old office PCs, running Kubernetes (via Talos Linux), with all configuration declared in Git. It’s my homelab, and it hosts sites for people too.**

It exists so I can practice and learn how real infrastructure works by actually running it. It is six machines running a Kubernetes cluster. Everything is declared in Git, because I hate configuring things and forgetting what is set up, and I love declarative configuration. It’s not trying to compete with the big providers, but is rather a homelab that also serves people over the internet. The cluster is made up of six HP machines pulled out of office environments: two EliteDesk towers and four ProDesk minis, with about 120GB of RAM and 36 cores between them. Each node is named after a character from My Little Pony (yes, seriously). 

The cluster originally ran k3s on NixOS, with every machine configured from a single Nix flake. However I ended up switching to Talos Linux, a minimal, immutable OS built only for running Kubernetes and managed entirely through an API. The current setup lives in the repo, cluster, and the old NixOS config and scripts are still up in the repos, nixos and scripts for reference.
</div>
