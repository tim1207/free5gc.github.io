# History

## Sep 5, 2024: v3.4.3

The release of free5GC v3.4.3 includes several new features, such as new network function TNGF, support for an empty SD value in SNSSAI, and the ability to disable CGF in CHF. It also features a refactored Subscriber Modal Page in the Webconsole. Additionally, several bugs have been fixed, including issues with double registration with N3IWF and unauthorized UE context releases, along with other bug fixes reported via GitHub issues and the free5GC forum.

**[Features]**

- Release TNGF & TNGFUE
- Support empty SD value (SNSSAI)
- Support disable CGF in CHF

**[Refactor]**

- Refactor Subscriber Modal Page in Webconsole

**[Bugs]**

- Fix can't registration with N3IWF twice problems
- Fix UEs can be context released by a second UE without authentication (src: [Issue](https://github.com/free5gc/free5gc/issues/580))
- Fix some bug reports from [Issues](https://github.com/free5gc/free5gc/issues) or [Forum](https://forum.free5gc.org/)

### July 3, 2024: v3.4.2

The free5GC v3.4.2 includes a Go version update to 1.21 and refactoring all Network Functions. New features include setting static IPs for UEs and OAuth2 authentication for the webconsole, plus a ULCL example in free5gc-compose. Bug fixes and a new commit message check are also included.

**[Refactor]**

- Go version bump to Go1.21
- Refactor NFs for preparation upgrading openapi to Release17


**[Features]**

- Set Static-IP for UE in webconsole 
- Webconsole acts as AF and uses OAuth2 authentication to get OAM service from NFs
- Add ULCL docker-compose example in [free5gc-compose](https://github.com/free5gc/free5gc-compose)
- Session AMBR in Data Plane
- CHF on k8s

**[Bugs]**

- Fix N3IWUE fails to ping when having flow rules([v1.0.1](https://github.com/free5gc/n3iwue/tree/v1.0.1))
- Fix some bug reports from [Issues](https://github.com/free5gc/free5gc/issues) or [Forum](https://forum.free5gc.org/)


**[Chore]**

- Apply [Conventional Commit Message](https://www.conventionalcommits.org/en/v1.0.0/) check in Pull Request


### March 28, 2024: v3.4.1

In free5GC v3.4.1, Convergent Charging on PDU Session will be fully supported!
Users will see the data usage on the webconsole after the PDU Session is created (please note that: The charging method (Online/Offline) needs to be determined during the subscription creation).

![](./assets/charging-demo.gif)

If you're interested in the implementation details, please visit the [CHF design document](https://free5gc.org/guide/Chf/design/).

### Feb 16, 2024: v3.4.0

We are delighted to unveil the release of free5GC v3.4.0! In this latest version, free5GC now boasts support for [OAuth](https://oauth.net/2/) within the Service-Based Architecture (SBA), marking a significant advancement in its capabilities. Furthermore, we have diligently addressed several issues and bugs that were reported by the Open-Source community, ensuring a smoother and more reliable user experience.

- OAuth Support
    - NRF acts as authorization server
    - All Services in AMF, SMF, NRF, PCF, UDR, UDM, AUSF, NSSF are supported to validate/request access token
- Implicit De-registration
    - Use case: UE has registered on Old AMF and send registration request to new AMF
        - New AMF is able to get the UE context by asking the old AMF, and old AMF will do the implicit de-registration.
- Support NAS Reroute ([Issue #413](https://github.com/free5gc/free5gc/issues/413))
- Support NITZ (Network Identiy and Time Zone) in UE Configuration Update Command ([Issue #113](https://github.com/free5gc/free5gc/issues/113))
- Bugfix
    - [Issue #421](https://github.com/free5gc/free5gc/issues/421)
    - [Issue #387](https://github.com/free5gc/free5gc/issues/387)
- Release N3IWUE
    - Source code: [https://github.com/free5gc/n3iwue](https://github.com/free5gc/n3iwue)