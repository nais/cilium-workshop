# cilium-workshop

Cilium Workshop for NDCOslo 2022

## Getting Started

### Prereq

* kubectl
* [cilium-cli](https://github.com/cilium/cilium-cli/releases)

<details>
  <summary>Install cilium-cli with asdf</summary>

  ```
  brew install asdf

  asdf plugin add cilium-cli
  asdf install cilium-cli latest
  asdf global cilium-cli latest
  ```
</details>

### With Colima

If you have not already install colima we reccomend installing it using brew:

```
brew install colima
```

Start colima with Kuberntes enabled:

```
colima start --kubernetes
```

Run the following two commands in order to get the things up and running (sourced from cilium/cilium-cli#669 and cilium/cilium#18675):

```
colima ssh -- sh -c "sudo mount bpffs /sys/fs/bpf -t bpf && sudo mount --make-shared /sys/fs/bpf"
colima ssh -- sh -c "sudo mount --make-shared /run/cilium/cgroupv2/"
```

## Install Cilium

Verify that you have a working Kubernetes connection:

```
kubectl version
```

Run the following command in order to set up Cilium:


```
cilium install
```
