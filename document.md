# README.md

This project automates the setup and configuration of Active Directory on Google Cloud Platform (GCP), integrates it with other instances, deploys the Wazuh SIEM for monitoring, and implements secure remote connections through Twingate. The end goal is to create a robust and secure environment for managing and monitoring instances in a cloud-based infrastructure.

## Prerequisites

* Google Cloud Platform (GCP) account with appropriate permissions.
* Virtual machines (VMs) for Active Directory, Wazuh SIEM, and other instances.
* Access to the internet for downloading necessary packages.

## Project Features

### Active Directory Setup

- Automated deployment of Active Directory on GCP.
- Integration of instances into the domain.

### Wazuh SIEM Deployment

- Automated installation and configuration of Wazuh SIEM for comprehensive security monitoring.
- Integration with Active Directory for centralized user and system event management.

### Security Policies in Active Directory

- Implementation of security policies in Active Directory, including password policies for enhanced security.

### Twingate for Secure Remote Connections

- Deployment of Twingate to establish secure and seamless remote connections to instances.

## Instructions

1. **Create a GCP project and enable the necessary APIs.**

   - Create a new GCP project or use an existing one.
   - Enable the following APIs:
      - Compute Engine API
      - Cloud Storage API
      - Cloud IAM API

2. **Create virtual machines for Active Directory, Wazuh SIEM, and other instances.**

   - Create a VM for Active Directory.
   - Create a VM for Wazuh SIEM.
   - Create VMs for other instances as needed.

3. **Install and configure the necessary software.**

   - Install the following software on the Active Directory VM:
      - Active Directory Domain Services (AD DS)
      - DNS Server

   - Install the following software on the Wazuh SIEM VM:
      - Wazuh Agent
      - Wazuh Manager

   - Install the Twingate connector on the VMs that need remote access.

4. **Deploy Active Directory on GCP.**

   - Use the provided scripts to automate the deployment of Active Directory on GCP.

5. **Integrate instances into the Active Directory domain.**

   - Use the provided scripts to automate the integration of instances into the Active Directory domain.

6. **Deploy Wazuh SIEM.**

   - Use the provided scripts to automate the installation and configuration of Wazuh SIEM.

7. **Implement security policies in Active Directory.**

   - Use the provided scripts to automate the implementation of security policies in Active Directory.

8. **Deploy Twingate for secure remote connections.**

   - Use the provided scripts to automate the deployment of Twingate for secure remote connections.

## Testing

To test the setup, follow these steps:

1. **Verify that Active Directory is running and accessible.**

   - Use the provided scripts to verify that Active Directory is running and accessible.

2. **Verify that Wazuh SIEM is collecting logs and events.**

   - Use the Wazuh SIEM web interface to verify that logs and events are being collected.

3. **Verify that security policies are being enforced.**

   - Use the Active Directory Users and Computers tool to verify that security policies are being enforced.

4. **Verify that remote connections to instances are secure.**

   - Use the Twingate web interface to verify that remote connections to instances are secure.

## Troubleshooting

If you encounter any problems, please refer to the documentation or contact the project maintainers for assistance.
