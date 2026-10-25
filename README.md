# <p align="center">👋 Hi, I'm Chandan Shahi</p>

<p align="center">
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=24&pause=1000&color=0089D6&center=true&vCenter=true&width=750&lines=Senior+DevOps+%26+Enterprise+Cloud+Architect;Azure+Landing+Zone+(CAF)+%26+GenAI+Infrastructure;Hub-and-Spoke+Zero-Trust+Networking+Specialist;Production-Grade+Terraform+%26+DevSecOps+Pipelines;100%2B+Enterprise+Workload+Cloud+Migration+Lead" alt="Typing SVG" />
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Microsoft_Azure-0089D6?style=for-the-badge&logo=microsoft-azure&logoColor=white" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" />
  <img src="https://img.shields.io/badge/Azure_OpenAI-00A67E?style=for-the-badge&logo=openai&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/DevSecOps-4A154B?style=for-the-badge&logo=slack&logoColor=white" />
  <img src="https://img.shields.io/badge/FinOps-Certified-success?style=for-the-badge&logo=google-analytics" />
</p>

---

## 👨‍💻 About Me & Architectural Vision

I am a **Senior DevOps & Enterprise Cloud Architect** specializing in large-scale cloud transformations, zero-trust enterprise landing zones, and GenAI infrastructure enablement.

- 🔭 **Current Focus:** Architecting Enterprise-Scale **Azure Landing Zones (CAF)** with private **Azure OpenAI (LLMOps)** integration.
- 💼 **Scale & Impact:** Successfully led the end-to-end migration of **100+ enterprise workloads** with zero unexpected downtime, achieving **~28% FinOps cost reduction**.
- 🛠️ **Core Strengths:** Reusable Terraform Modules, Centralized Hub-and-Spoke Virtual Networks, DevSecOps Automation (Checkov/Tfsec/Infracost), and Enterprise Delivery Governance.
- 🎯 **Leadership:** Technical evaluation of RFPs/SOWs, vendor governance, cross-functional mentoring, and KT acceleration.

---

## 🌟 Featured Enterprise Architecture Repositories

<table>
  <tr>
    <td width="50%">
      <h3 align="center">🏛️ <a href="https://github.com/chandandevops07-gif/azure-enterprise-landing-zone">azure-enterprise-landing-zone</a></h3>
      <p align="center"><b>Production-Grade Azure Landing Zone (CAF) with GenAI & Hub-Spoke</b></p>
      <ul>
        <li><b>GenAI Landing Zone:</b> Private Azure OpenAI & AI Search via Private Endpoints.</li>
        <li><b>Hub-and-Spoke:</b> Azure Firewall Premium inspection & forced tunneling UDRs.</li>
        <li><b>Terraform Modules:</b> Parameterized, versioned, DRY modules with remote state leasing.</li>
        <li><b>DevSecOps:</b> CI/CD pipelines with TFLint, Checkov (CIS Benchmark), and Infracost.</li>
      </ul>
      <p align="center">
        <a href="https://github.com/chandandevops07-gif/azure-enterprise-landing-zone">
          <img src="https://img.shields.io/badge/View_Repository-0089D6?style=flat-square&logo=github&logoColor=white" />
        </a>
      </p>
    </td>
    <td width="50%">
      <h3 align="center">📦 <a href="https://github.com/chandandevops07-gif/Terraform-modules">Terraform-modules</a></h3>
      <p align="center"><b>Reusable Enterprise Infrastructure as Code Modules</b></p>
      <ul>
        <li><b>VNet & Subnet Modules:</b> Standardized enterprise CIDR provisioning.</li>
        <li><b>Compute & Storage:</b> Hardened VMs, VMSS, and Storage Accounts with CMK.</li>
        <li><b>Governance:</b> Custom Azure Policy and RBAC assignment modules.</li>
        <li><b>Advanced State:</b> Nested maps, dynamic blocks, and variable validation patterns.</li>
      </ul>
      <p align="center">
        <a href="https://github.com/chandandevops07-gif/Terraform-modules">
          <img src="https://img.shields.io/badge/View_Repository-7B42BC?style=flat-square&logo=github&logoColor=white" />
        </a>
      </p>
    </td>
  </tr>
</table>

---

## 🏗️ Architectural Blueprint: Enterprise CAF + GenAI Landing Zone

```mermaid
flowchart TB
    subgraph OnPrem [On-Premises Datacenter]
        DC[Core Datacenter / Headquarters]
    end

    subgraph Hybrid [Hybrid Connectivity]
        ER[ExpressRoute / S2S VPN Gateway]
    end

    subgraph HubVNet [HUB Virtual Network - 10.0.0.0/16]
        AzFW[Azure Firewall Premium / IDPS]
        GWSubnet[GatewaySubnet]
        Bastion[Azure Bastion Subnet]
        DNS[Central Private DNS Resolver]
    end

    subgraph Spoke_GenAI [Spoke 1: Enterprise GenAI LZ - 10.10.0.0/20]
        APIM[Azure API Management / AI Gateway]
        AOAI[Azure OpenAI Private Endpoint]
        AISearch[Azure AI Search Vector Store]
        AppUI[Internal AI Assistant]
    end

    subgraph Spoke_Apps [Spoke 2: Workload Applications - 10.20.0.0/20]
        AKS[Azure Kubernetes Service Cluster]
        AppGW[App Gateway WAF v2]
        DB[(Azure SQL / CosmosDB Private Link)]
    end

    subgraph Spoke_Shared [Spoke 3: Operations & Tooling - 10.30.0.0/20]
        Runners[Self-Hosted CI/CD Runners]
        KeyVault[Azure Key Vault HSM]
        LogAnalytics[Central Log Analytics Workspace]
    end

    DC <--> ER
    ER <--> GWSubnet
    GWSubnet --> AzFW
    AzFW <-->|Peered + UDR 0.0.0.0/0| Spoke_GenAI
    AzFW <-->|Peered + UDR 0.0.0.0/0| Spoke_Apps
    AzFW <-->|Peered + UDR 0.0.0.0/0| Spoke_Shared

    APIM -->|Private Link| AOAI
    APIM -->|Private Link| AISearch
    AppUI --> APIM
```

---

## 🧠 Core Architectural Pillars & Enterprise Specializations

<details open>
<summary><b>1. Enterprise GenAI & LLMOps Infrastructure</b></summary>
<br>

- **Zero Public Access:** Azure OpenAI, AI Search, and Cosmos DB provisioned with `public_network_access_enabled = false` and connected via **Private Endpoints (`privatelink.openai.azure.com`)**.
- **GenAI Gateway via APIM:**
  - Token-bucket rate limiting to eliminate quota exhaustion.
  - Smart multi-region load balancing across Azure OpenAI instances.
  - **Semantic Caching** using Redis to reduce latency and save **~40% token costs**.
  - Integrated Azure AI Content Safety filters against prompt injection and data leaks.
</details>

<details>
<summary><b>2. Enterprise Hub-and-Spoke Networking</b></summary>
<br>

- **Centralized Traffic Inspection:** User Defined Routes (UDRs) forcing `0.0.0.0/0` and inter-spoke traffic through Azure Firewall Premium.
- **Private DNS Architecture:** Centralized Azure Private DNS Resolver in the Hub VNet linked to all spokes and On-Premises DNS servers.
- **Micro-Segmentation:** Fine-grained Network Security Groups (NSGs) and Application Security Groups (ASGs) preventing lateral movement.
</details>

<details>
<summary><b>3. Enterprise Governance & Management Hierarchy (CAF)</b></summary>
<br>

- **Hierarchy:** Microsoft Entra ID Tenant -> Root Management Group -> Platform (Identity, Connectivity, Management) + Workloads (Corp, Online, GenAI) + Sandboxes.
- **Policy Guardrails:** Automated assignment of CIS Azure Benchmark & MCSB initiatives with enforce/deny effects.
- **Identity & Access:** Group-based RBAC with Entra ID and Privileged Identity Management (PIM) for Just-in-Time access.
</details>

<details>
<summary><b>4. DevSecOps & Automated IaC Pipeline</b></summary>
<br>

- **Shift-Left Security:** Automated PR linting (`tflint`, `terraform fmt`), security vulnerability scanning (`tfsec`, `Checkov`), and FinOps cost estimation (`Infracost`).
- **Drift Detection:** Scheduled nightly pipelines running `terraform plan -detailed-exitcode` to automatically detect out-of-band console modifications.
- **Remote State Security:** Encrypted private Azure Blob Storage with lease locking and Managed Identity authentication.
</details>

<details>
<summary><b>5. 100+ Enterprise Workload Migration Strategy</b></summary>
<br>

- **6-Phase Factory Model:** Discovery -> Assessment (Azure Migrate) -> Landing Zone Readiness -> Migration Waves -> Cutover -> Hypercare.
- **Resilience:** Pre-tested RTO (< 2 hrs) and RPO (< 15 mins) targets using Azure Site Recovery (ASR) and Geo-Replication.
- **War Room Governance:** Dedicated 24/7 hypercare support for 14-30 days post-cutover.
</details>

<details>
<summary><b>6. FinOps (Cloud Financial Management)</b></summary>
<br>

- **Waste Elimination:** Automated scripts for deleting unattached disks, orphan public IPs, and obsolete snapshots.
- **Commitment Optimization:** 1-year / 3-year Reserved Instances (RI) and Azure Savings Plans covering steady-state compute.
- **Non-Prod Scheduling:** Automated start/stop runbooks saving ~65% on non-production environments.
</details>

---

## 🛠️ Technology Stack & Tooling

<table>
  <tr>
    <td align="center" width="16.6%"><b>Cloud Platforms</b></td>
    <td>
      <img src="https://img.shields.io/badge/Microsoft_Azure-0089D6?style=flat-square&logo=microsoft-azure&logoColor=white" />
      <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white" />
      <img src="https://img.shields.io/badge/Cloud_Adoption_Framework-0078D4?style=flat-square&logo=microsoft" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>IaC & Automation</b></td>
    <td>
      <img src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white" />
      <img src="https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white" />
      <img src="https://img.shields.io/badge/Bicep-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" />
      <img src="https://img.shields.io/badge/Infracost-17C172?style=flat-square&logo=infracost&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Containers & Orchestration</b></td>
    <td>
      <img src="https://img.shields.io/badge/Kubernetes_(AKS)-326CE5?style=flat-square&logo=kubernetes&logoColor=white" />
      <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
      <img src="https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>CI/CD & DevSecOps</b></td>
    <td>
      <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white" />
      <img src="https://img.shields.io/badge/Azure_DevOps-0078D7?style=flat-square&logo=azure-devops&logoColor=white" />
      <img src="https://img.shields.io/badge/Checkov-2C3437?style=flat-square&logo=bridgecrew&logoColor=white" />
      <img src="https://img.shields.io/badge/TFLint-7B42BC?style=flat-square&logo=terraform&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>GenAI & Data</b></td>
    <td>
      <img src="https://img.shields.io/badge/Azure_OpenAI-00A67E?style=flat-square&logo=openai&logoColor=white" />
      <img src="https://img.shields.io/badge/Azure_AI_Search-0078D4?style=flat-square&logo=microsoft-azure&logoColor=white" />
      <img src="https://img.shields.io/badge/Redis_Cache-DC382D?style=flat-square&logo=redis&logoColor=white" />
      <img src="https://img.shields.io/badge/API_Management-005BA1?style=flat-square&logo=microsoft&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Monitoring & SRE</b></td>
    <td>
      <img src="https://img.shields.io/badge/Azure_Monitor-0078D4?style=flat-square&logo=microsoft-azure&logoColor=white" />
      <img src="https://img.shields.io/badge/Log_Analytics-0089D6?style=flat-square&logo=microsoft&logoColor=white" />
      <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" />
      <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white" />
    </td>
  </tr>
</table>

---

## 📊 GitHub Analytics & Activity

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=chandandevops07-gif&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" width="48%" />
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=chandandevops07-gif&theme=tokyonight&hide_border=true" width="48%" />
</p>

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=chandandevops07-gif&layout=compact&theme=tokyonight&hide_border=true" width="48%" />
</p>

---

## 📬 Connect With Me

<p align="center">
  <a href="https://linkedin.com">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://github.com/chandandevops07-gif">
    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="mailto:chandandevops07@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
</p>

<p align="center">
  <i>"Architecture is not just about tools; it's about business alignment, governance, and resilient engineering at scale."</i>
</p>
