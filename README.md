# holochain-webservice
Holochain webservice for talking to holochain Holo-REA gateway.

# How to setup
1. Provision an AWS Ubuntu node.  

`As of 28th Jan 2019 the Holo-REA and NixOS shell contain a lot of of build files (routhly 4GB so it's safer to provision a machine that has at least 8GBs.  for this demo had to increase our AWS machine from a t2.micro to t2.large.`

2. Log into your machine with ssh.

3. Install NixOS `curl https://nixos.org/nix/install | sh` then run `. ~/.nix-profile/etc/profile.d/nix.sh`
Further instructions here if needed: https://developer.holochain.org/docs/install/

You can check if NixOS shell is running by running `nix-shell --version`

4. Clone the Holo-REA project from: https://github.com/holo-rea/holo-rea
`git clone https://github.com/holo-rea/holo-rea.git`

5. Enter into the Holo-REA directory then run `nix-shell`
this will take a while to run.