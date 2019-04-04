<!-- TITLE: Infrastructure -->
<!-- SUBTITLE: A list of Ethereum community infrastructure, how it works, and who maintains it -->

# EIPs Repo + Website
The Ethereum Improvement Proposal -- aka EIPs -- repo is at https://github.com/ethereum/EIPs. It contains the source code for a Jekyll website which is generated whenever files are committed. The generated website is at https://eips.ethereum.org

* Get help in the Gitter channel https://gitter.im/ethereum/EIPs

---

- Who owns / runs the Travis CI account?
- Is the website hosted on Github Pages?

## EIP Automerger

The EIP automerger is an App Engine app to automatically merge EIP PRs which are edited by their authors. Source code: https://github.com/eip-automerger/automerger. The App Engine app is owned by Nick Johnson.

Sometimes the automerger gets pinged by Travis before Travis pings Github, so it fails to merge because Github didn't know it succeeded. Anyone can try and re-run the automerger on their own PR by running this command: `http://ethlab-183014.appspot.com/merge/?repo=ethereum/eips&pr=XXXX`, where `XXXX` is the number of your PR.

# All Core Dev Calls
All Core Dev Calls happen every 2 weeks. Issues in the [ethereum/pm](https://github.com/ethereum/pm) track the meeting agenda. 

Hudson Jamieson facilitates the calls. A Zoom link is dropped in the All Core Devs Gitter shortly before the call.

* who has commit access / can manage issues on the `ethereum/pm` repo
* whose Zoom account(s) are used? who pays for the Zoom accounts?
* who has control over the YouTube channel?
* what is the setup for YouTube livestreaming?

Tim Beiko has been live tweeting highlights.

EthCatHerders have started posting summary notes. 
# ethereum.org DNS
The `ethereum.org` domain is owned by the Ethereum Foundation.

- where is DNS hosted?
- who has access to change DNS?