# GitHub Enterprise Server Exercise
Approximate time: 8h

The GHES workshop exercise is meant for people to become confident in deploying and managing the core featureset of GitHub Enterprise Server. Installations can take place in Cloud or on-premise. The main focus points will be network setup, infrastructure settings, authentication, GitHub Connect, Actions and Packages and SSH access. If this is not your first installation attempt feel free to experiment with the wide variety of different deployment options.

### Duration
This exercise should take approximately 8 hours to complete. The time estimates are based on the average time it takes to complete each step. The time estimates are not meant to be a hard limit, but rather a guideline to help you plan your time. It is always possible to step away from the exercise and come back to it later.


### Prerequisites
- GitHub.com account with the Enterprise owner role for a GitHub Enterprise Cloud instance (optional for GitHub Connect).
- A valid GitHub Server license file.
- Deployment and network permissions to one of the supported environ-
ments (e.g. Azure, AWS, GCP, VMware ESXi).
- Access to one of the supported external authentication methods for testing,
either via SAML or using LDAP (e.g. Azure AD, Windows AD FS, Okta or Active Directory).
- Permissions to configure blob storage using one of the supported storage
providers (Azure Blob, AWS S3, GCP Storage, MinIO).
- Ability to connect over SSH.

### Installation (1h)
- [Downloading your license for GitHub Enterprise.](https://docs.github.com/en/enterprise-server@3.10/billing/managing-your-license-for-github-enterprise/downloading-your-license-for-github-enterprise)
- [Follow one of the guides Setting up a GitHub Enterprise Server instance matching your preferred environment.](https://docs.github.com/en/enterprise-server@3.10/admin/installation/setting-up-a-github-enterprise-server-instance)
- [Deploy or download the latest (or almost the latest in order to perform the upgrade) cloud template (optional) or on-premise appliance version.](https://enterprise.github.com/releases/)
- During setup leave Actions and Packages disabled for now.


### Configuration ( 2h)
- Configure or verify IP and DNS settings after installation:
  - [Configuring the IP address using the virtual machine console (on-premise).](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/configuring-network-settings/configuring-the-ip-address-using-the-virtual-machine-console)
  - [Configuring DNS nameservers.](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/configuring-network-settings/configuring-dns-nameservers)
  - [Open inbound application ports for end users publicly to the internet (ports 22, 25, 80, 443, 9418).](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/configuring-network-settings/network-ports#application-ports-for-end-users)
  - [Open inbound administrative ports only for trusted IPs (ports 122, 123, 161, 1194, 8080, 8443).](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/configuring-network-settings/network-ports#administrative-ports)

- Access the Management Console and configure the following settings:
  - [Configuring a hostname.](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/configuring-network-settings/configuring-the-hostname-for-your-instance)
  - [Validating your domain settings.](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/configuring-network-settings/validating-your-domain-settings)
  - [Configuring TLS (Let’s Encrypt or custom TLS certificate).](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/hardening-security-for-your-enterprise/configuring-tls)
  - [Enabling subdomain isolation (optional).](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/hardening-security-for-your-enterprise/enabling-subdomain-isolation)


### Authentication (2h)
- Configure external authentication using SAML or LDAP choosing one of our supported services or providers:
  - [Using SAML for enterprise IAM (e.g. Azure AD, OKTA, Windows AD FS).](https://docs.github.com/en/enterprise-server@3.10/admin/identity-and-access-management/using-saml-for-enterprise-iam)
    - [Azure AD: Tutorial: Azure AD SSO integration with GitHub Enterprise Server.](https://learn.microsoft.com/en-us/entra/identity/saas-apps/github-ae-tutorial)
    - [Okta: How to Configure SAML 2.0 for GitHub Enterprise Server. Windows AD FS: Configuring Active Directory Federation Services (ADFS) as a SAML identity provider.](https://saml-doc.okta.com/SAML_Docs/How-to-Configure-SAML-2.0-for-Github_Enterprise.html)
    - [Using LDAP (e.g. Active Directory, OpenLDAP).](https://gist.github.com/nicklegan/b3c5d6beb1752f6459d7d37f04540245)

### GitHub Actions and Packages with external blob storage ( 1h)
- [Enabling GitHub Actions for GitHub Enterprise Server.](https://docs.github.com/en/enterprise-server@3.10/admin/github-actions/enabling-github-actions-for-github-enterprise-server)
- [Managing GitHub Packages for your enterprise.](https://docs.github.com/en/enterprise-server@3.10/admin/packages)

### GitHub Connect ( 30m)
- Enable GitHub Connect and its features: 
  - [Enabling GitHub Connect.](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/configuring-github-connect/managing-github-connect#enabling-github-connect)
  - [Enable GitHub Connect features.](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/configuring-github-connect/about-github-connect#github-connect-features)

### Advanced Security ( 30m)
- [Enabling GitHub Advanced Security for your enterprise](https://docs.github.com/en/enterprise-server@3.10/admin/code-security/managing-github-advanced-security-for-your-enterprise/enabling-github-advanced-security-for-your-enterprise)
  - Dependency graph
  - Dependabot updates 
  - Code scanning
  - Secret scanning


### Administrative shell and command-line utilities ( 1h)
- Configure your SSH access to the appliance and test some of the various available command-line utlities:
  - [Accessing the administrative shell (SSH).](https://docs.github.com/en/enterprise-server@3.10/admin/administering-your-instance/administering-your-instance-from-the-command-line/accessing-the-administrative-shell-ssh)
  - [Command-line utilities.](https://docs.github.com/en/enterprise-server@3.10/admin/administering-your-instance/administering-your-instance-from-the-command-line/command-line-utilities)

### Finish line :checkered_flag: :rocket: :octocat: :sparkles:
• You’ve made it! When you arrive at this step it means you succeeded having all the core features of a single GitHub Enterprise Server instance active, this is an awesome skill to have! Take some time to relax and celebrate your newly acquired skills! There’s still plenty more to learn about our GHES product! For example I recommend you to learn about following:

- [Setting up a High Availability Replica](https://docs.github.com/en/enterprise-server@3.10/admin/monitoring-managing-and-updating-your-instance/configuring-high-availability/creating-a-high-availability-replica#creating-a-high-availability-replica)
- [Setting up a geo-replication](https://docs.github.com/en/enterprise-server@3.10/admin/monitoring-managing-and-updating-your-instance/configuring-high-availability/creating-a-high-availability-replica#creating-geo-replication-replicas)
- [Enabling GitHub Pages](https://docs.github.com/en/enterprise-server@3.10/admin/configuration/configuring-user-applications-for-your-enterprise/configuring-github-pages-for-your-enterprise)
- [Performing a backup!](https://docs.github.com/en/enterprise-server@3.10/admin/backing-up-and-restoring-your-instance/configuring-backups-on-your-instance)
- [Updating your instance](https://docs.github.com/en/enterprise-server@3.10/admin/monitoring-managing-and-updating-your-instance/updating-the-virtual-machine-and-physical-resources/upgrading-github-enterprise-server)
