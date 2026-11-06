<div align="center">

# Bunch Webhost
**TLDR: Six old office PCs, running NixOS and Kubernetes, with all configuration is declared in Git. It’s my homelab, and it hosts sites for people too.**

It exists so I can practice and learn how real infrastructure works by actually running it. It runs on six machines running NixOS, which are running a Kubernetes cluster. Everything is declared in Git, because I hate configuring things and forgetting what is set up, and I love declarative configuration. It’s not trying to compete with the big providers, but is rather a homelab that serves people over the internet.

The cluster is made up of six HP machines pulled out of office environments: two EliteDesk towers and four ProDesk minis, with about 120GB of RAM and 36 cores between them. Each node is named after a character from My Little Pony (yes, seriously). Twilight is the router, which handles networking for each other node, it sits between the cluster and the internet, and acts as a firewall, DHCP, and DNS server. Fluttershy, Rainbow Dash, Rarity, Pinkie Pie and Applejack are the other nodes in the cluster.

Kubernetes is handled by k3s, a lightweight distribution that suits small hardware like this. Every machine's configuration lives in a single NixOS flake, and everything running on the cluster is defined in a separate repo that Flux watches and applies automatically. Renovate keeps dependencies up to date, and secrets are encrypted with sops so they can live safely alongside everything else in Git. Remote access goes through Tailscale only, so nothing management-related is exposed to the internet.

</div>
