# FISMA Ready Introduction

In the United States, all Federal Government information systems are regulated by the [Federal Information Security Management Act](http://en.wikipedia.org/wiki/Federal_Information_Security_Management_Act_of_2002) (FISMA). This law empowers the [National Institute for Standards and Technology](http://www.nist.gov/) (NIST) to issue guidance on what security controls should exist on information systems, especially those in production. 

While nothing is completely without risk, Federal agencies require systems to receive an Authority to Operate (ATO) before putting a system into production. An ATO is the final step in NIST's [risk management framework](http://csrc.nist.gov/groups/SMA/fisma/framework.html). An ATO represents the agency's acceptance of the risk presented in operating the system, after all due dilligence has been completed and reasonable controls put in place.

[NIST Special Publication (SP) 800-53 Revision 4](http://csrc.nist.gov/groups/SMA/fisma/controls.html) lists various control baselines, depending on how the system has been [categorized](http://csrc.nist.gov/groups/SMA/fisma/categorization.html). Implenting, documenting, and assesing these controls on a system of even moderate complexity can be incrediably time consuming and prone to error.

[18F](https://18F.gsa.gov), a digital services delivery team within the [General Services Administration](http://www.gsa.gov) (GSA), is interested in making this process more efficient and effective, while radically reducing the time necessary to get an ATO. One way to increase both quality and speed is to heavily resuse pre-approved components in the system.

## Considerations and prerequisites

Before starting to use FISMA Ready components, implement the following best practices.

### Secure your cloud infrastructure

This work presumes the system is deployed on cloud infrasturcture that has a [FedRAMP](http://cloud.cio.gov/fedramp) authorization. FedRAMP pre-approves cloud infrastructure as meeting NIST controls. Many of the NIST controls presumes the agency still has physical control to the servers or hypervisor level access. Increasingly, these controls are instead implemented by [vendors proving Infrastucture as a Service (IaaS)](http://cloud.cio.gov/fedramp/cloud-systems). FedRAMP, along with an accredited third-party assesor, ensures the vendor's controls meet Federal guidelines. 

### Continuous monitoring and a team where everyone is responsible

Using FedRAMP, or pre-approved system components in general, does not remove the need to implement a program of continuinous monitoring or other intrustion detection systems. If using a true IaaS solution, Federal technology teams are responsible for a continuous monitoring program. The vast majority of a system's security comes not from technical controls, but the culture of the team responsible for the system. In order to bridge the gaps between application developers, system administrators and engineers, and cybersecurity proffesionals, Federal agencies should consider re-organizing their technology teams under a [DevOps model](http://en.wikipedia.org/wiki/DevOps).

### Trust but verify

If an agency resuses a system component that has received an ATO from another agency, they should be sure to test the security controls are indeed in place. FISMA Ready will strive to ensure those tests are automated, easy to use, and able to be run with free and open source software, without any restrictions. Once an initial re-assesment has been completed, agencies should consider the use of hashes on the virtual machine, container, or package to ensure they are always building from a known component state.

# 18F FISMA Ready Ubuntu - version 0.1.2

The team at 18F decided to startwork exactly where FedRAMP stops - at the operating system layer, in a true IaaS environment. Current baselines were available for Windows, Solaris, and Red Hat Enterprise Linux. But there were no generally available, and certainly not public baselines, for Ubuntu or the Debian version of Linux generally. 18F is committed to [free and open source software](https://github.com/18F/open-source-policy/blob/master/policy.md) - our intention is that the software we write can be run _anywhere_, without the need to pay for licensing fees.

