# cst8919Assignment2

# Cloud Service Equivalents – Azure vs AWS vs GCP

## Objective
This report compares selected Microsoft Azure services studied during the course with equivalent services from Amazon Web Services (AWS) and Google Cloud Platform (GCP). The focus is on core features, security and compliance, pricing models, and integration with DevSecOps practices.  


## 1. Azure Active Directory (SSO, IAM)

| Feature | Azure Active Directory | AWS IAM / AWS SSO | Google Cloud Identity |
|---------|------------------------|-------------------|-----------------------|
| **Overview** | Cloud-based identity and access management with SSO, MFA, and conditional access. | AWS IAM manages AWS resource permissions; AWS SSO handles SSO across AWS accounts and apps. | Cloud Identity provides identity services, SSO, and MFA for GCP and SaaS apps. |
| **Core Features** | SSO, MFA, conditional access, user lifecycle management. | Fine-grained access policies, federated identities, SSO. | SSO, MFA, device management, directory sync. |
| **Security & Compliance** | ISO 27001, SOC, HIPAA, FedRAMP. | SOC, ISO, PCI DSS, FedRAMP. | ISO 27001, SOC, HIPAA, FedRAMP. |
| **Pricing** | Free tier + Premium P1/P2 licenses per user/month. | No cost for IAM; SSO costs per active user (for certain tiers). | Per-user/month for premium tiers; basic free tier. |
| **DevSecOps Integration** | Integrates with Azure DevOps, GitHub Actions, APIs for automation. | Supports IAM policies in CI/CD, integrates with AWS CodePipeline. | Integrates with Cloud Build, Terraform, APIs for automation. |

**Analysis:**  
Azure Active Directory is designed for hybrid identity management and integrates deeply with Microsoft 365 and Azure services. AWS splits similar functionality across IAM (permissions) and AWS SSO (federated logins). GCP’s Cloud Identity offers a blend of identity and device management. In DevSecOps pipelines, all three platforms can integrate into CI/CD tools, but Azure AD tends to be the most tightly coupled with developer tools in the Microsoft ecosystem.


## 2. Azure Monitor & Log Analytics

| Feature | Azure Monitor & Log Analytics | Amazon CloudWatch | Google Cloud Operations Suite (Stackdriver) |
|---------|------------------------------|-------------------|----------------------------------------------|
| **Overview** | Unified monitoring and analytics for Azure resources and apps. | Monitoring, logging, and alerting for AWS workloads. | Monitoring, logging, and diagnostics for GCP and hybrid workloads. |
| **Core Features** | Metrics, logs, alerts, custom queries (KQL). | Metrics, logs, dashboards, anomaly detection. | Metrics, logs, uptime checks, alerting. |
| **Security & Compliance** | Data encryption, RBAC, ISO, SOC, HIPAA. | Data encryption, IAM, SOC, PCI DSS. | Encryption, IAM, ISO, HIPAA, SOC. |
| **Pricing** | Pay-per-GB ingested & retention costs. | Pay-per-metric, log ingestion, retention. | Pay-per-metric, log ingestion, retention. |
| **DevSecOps Integration** | Supports CI/CD alerts, automation hooks, APIs. | Integrates with CodePipeline, Lambda alerts. | Works with Cloud Build, Terraform triggers. |

**Analysis:**  
Azure Monitor combines performance metrics with Log Analytics for deeper insights using Kusto Query Language (KQL). AWS CloudWatch has comparable capabilities but uses CloudWatch Logs Insights for queries. GCP’s Operations Suite provides a unified interface for monitoring and logging with good multi-cloud support. Pricing for all three is usage-based, making cost management a key consideration for large-scale workloads.


## 3. Azure Policy

| Feature | Azure Policy | AWS Config | Google Cloud Organization Policy Service |
|---------|--------------|-----------|-------------------------------------------|
| **Overview** | Defines and enforces governance rules on Azure resources. | Tracks AWS resource configuration & compliance. | Enforces constraints across GCP resources. |
| **Core Features** | Policy definitions, compliance dashboard, remediation. | Config rules, compliance evaluation, remediation. | Constraints, policy inheritance, compliance checks. |
| **Security & Compliance** | RBAC, ISO, SOC, FedRAMP. | IAM, ISO, SOC, FedRAMP. | IAM, ISO, SOC, FedRAMP. |
| **Pricing** | No extra cost for basic; remediation may incur charges. | Pay-per-rule evaluation. | No extra cost. |
| **DevSecOps Integration** | Policy as code with ARM/Terraform. | Works with CloudFormation, Terraform. | Works with Deployment Manager, Terraform. |

**Analysis:**  
Azure Policy focuses on enforcing compliance proactively, with built-in remediation tasks. AWS Config takes a more audit-and-remediate approach, evaluating resources against defined rules. GCP’s Organization Policy Service applies constraints globally or per project. For DevSecOps, Azure Policy’s “policy as code” model offers strong automation potential, similar to AWS Config rules and GCP constraint templates.


## 4. Microsoft Defender for Cloud

| Feature | Microsoft Defender for Cloud | AWS Security Hub | Google Security Command Center |
|---------|-----------------------------|------------------|---------------------------------|
| **Overview** | Cloud security posture management & threat protection. | Central security findings from AWS services. | Security posture management & threat detection for GCP. |
| **Core Features** | Vulnerability scanning, compliance assessment. | Findings aggregation, compliance checks. | Threat detection, compliance checks. |
| **Security & Compliance** | ISO, SOC, PCI DSS, HIPAA. | ISO, SOC, PCI DSS, HIPAA. | ISO, SOC, PCI DSS, HIPAA. |
| **Pricing** | Pay per resource type monitored. | Pay per finding ingestion. | Tiered pricing. |
| **DevSecOps Integration** | API access for CI/CD scans. | Integrates with AWS DevOps tools. | Works with Cloud Build, APIs. |

**Analysis:**  
Defender for Cloud provides native vulnerability scanning and integrates tightly with Azure workloads. AWS Security Hub aggregates findings from multiple AWS security tools but relies on partner integrations for scanning. GCP’s Security Command Center includes asset discovery and vulnerability scanning in higher tiers. All three integrate with DevSecOps pipelines, but the depth of native integration varies.


## 5. Azure Sentinel (SIEM/SOAR)

| Feature | Microsoft Sentinel | Amazon Security Lake / OpenSearch SIEM | Chronicle Security Operations |
|---------|-------------------|------------------------------------------|--------------------------------|
| **Overview** | Cloud-native SIEM & SOAR. | Centralized security data lake + analytics. | Google’s cloud-native SIEM & SOAR. |
| **Core Features** | Threat detection, investigation, automation. | Data lake queries, threat hunting. | Threat detection, incident response, automation. |
| **Security & Compliance** | ISO, SOC, PCI DSS, HIPAA, FedRAMP. | ISO, SOC, PCI DSS, HIPAA. | ISO, SOC, PCI DSS, HIPAA. |
| **Pricing** | Pay-per-GB ingested & retention. | Pay-per-GB ingested. | Subscription-based. |
| **DevSecOps Integration** | Integrates with Azure DevOps, GitHub. | Integrates with AWS services & automation. | Works with Cloud Functions, APIs. |

**Analysis:**  
Sentinel offers a fully managed SIEM/SOAR with advanced analytics via KQL. AWS doesn’t have a single branded SIEM but provides equivalent functionality using Security Lake and OpenSearch. GCP’s Chronicle focuses on high-speed threat detection with Google-scale data processing. Pricing models differ significantly — Azure and AWS are consumption-based, while Chronicle often uses a subscription approach.


## Quick Reference Table

| Azure Service | AWS Equivalent | GCP Equivalent |
|---------------|---------------|----------------|
| Azure Active Directory | AWS IAM / AWS SSO | Cloud Identity |
| Azure Monitor & Log Analytics | Amazon CloudWatch | Cloud Operations Suite |
| Azure Policy | AWS Config | Organization Policy Service |
| Defender for Cloud | AWS Security Hub | Security Command Center |
| Azure Sentinel | Amazon Security Lake / OpenSearch SIEM | Chronicle Security Operations |

---

## Conclusion
While Azure, AWS, and GCP provide comparable services for identity management, monitoring, governance, security, and SIEM/SOAR, the differences lie in integration depth, pricing models, and native ecosystem alignment. For DevSecOps workflows, the choice often depends on the existing cloud footprint and how well each service integrates with automation pipelines and compliance processes.

