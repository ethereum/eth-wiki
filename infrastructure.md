<!-- TITLE: Infrastructure -->
<!-- SUBTITLE: A list of Ethereum community infrastructure, how it works, and who maintains it -->

This is an attempt to list who to talk to or ask questions about various pieces of Ethereum community infrastructure. Some of it may not get answered because of opsec reasons. If you come across something, please [file an issue in the Ethereum Cat Herders PM repo](https://github.com/ethereum-cat-herders/PM/issues) so it can be tracked and someone can help answer it.
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

Hudson Jamieson facilitates the calls. A Zoom link is dropped in the All Core Devs Gitter shortly before the call. The video from Zoom is livestreamed to the [Ethereum Foundation Youtube brand channel](https://www.youtube.com/channel/UCNOfzGXD_C9YMYmnefmPH0g). Hudson (and others?) have access to manage the Ethereum Foundation brand channel. Hudson's paid Zoom account is used to host the call.

* who has commit access / can manage issues on the `ethereum/pm` repo
* what is the setup for YouTube livestreaming? anything that needs documenting?

Tim Beiko has been live tweeting highlights.

EthCatHerders have started posting summary notes. 

[ECH Issue #29](https://github.com/ethereum-cat-herders/PM/issues/29)

# Ethereum Github Organization
The Ethereum Foundation owns the `ethereum` organization on GitHub http://github.com/ethereum.

There are [52 people publicly listed](https://github.com/orgs/ethereum/people).

* who has admin rights on the organization?
* which are the "critical" repos, and who has admin rights over them for adding maintainers?

# Ethstats
https://ethstats.net

Run by the EF

- who is the point of contact?

# blog.ethereum.org
* where is it hosted?
* who has permission to post here / who to talk to if you want something highlighted here?

# forum.ethereum.org 
* who is in charge with that forum? It looks abandoned and also there is questionable ads of miners chasis right in the forum header. 

[ECH Issue #33](https://github.com/ethereum-cat-herders/PM/issues/33)
# ethereum.org DNS
The `ethereum.org` domain is owned by the Ethereum Foundation.

- where is DNS hosted?
- who has access to change DNS?