# holochain-webservice
Holochain webservice for talking to holochain Holo-REA gateway.

# How to setup
1. Provision an AWS Ubuntu node.
`As of 28th Jan 2019 the Holo-REA and NixOS shell contain a lot of of build files (routhly 4GB so it's safer to provision a machine that has at least 16GBs.`

2. Log into your machine with ssh.

3. Install NixOS `curl https://nixos.org/nix/install | sh` then run `. ~/.nix-profile/etc/profile.d/nix.sh`
Further instructions here if needed: https://developer.holochain.org/docs/install/
You can check if NixOS shell is running by running `nix-shell --version`

4. Clone the Holo-REA project from: https://github.com/holo-rea/holo-rea
`git clone https://github.com/holo-rea/holo-rea.git`

5. Enter into the Holo-REA directory then run `nix-shell` this will take a while to run.

6. Now you need to copy the 2 conductor files with their associated Agent keys into the holo-REA repo. The fastest way to do this is to enter into the holo-REA repo and then run `git clone https://github.com/BeefLedger/holochain-webservice.git`

This allows us to create 2 instances of Holo-REA with 2 different agents on the same machine.  If you would like to create another idenity you can use the hc helper tool. `hc keygen` for further reference you can run `hc --help`. 

7. Now it's time to run the 2 instances in different windows.
First lets create 2 seperate node scripts. 
Add the following node scripts to the holo-rea package.json folder.

`"dht:conductor1": "holochain -c ./conductor-config-Agent1-httpinterface-4101.toml",
"dht:conductor2": "holochain -c ./conductor-config-Agent2-httpinterface-4201.toml",`

8. Now start the frist instance with the first Agent ID with "npm run dht:conductor1"

9. Now startt the second instance with the second Agent ID with "dht:conductor2"

Well done you now have 2 holo-rea instances running on AWS.