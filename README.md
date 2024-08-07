# Azure Administrator Study Notes

## Learning Modules

### Microsoft Learn Modules
- **Link**: [Learn Modules - Azure Administrator](https://learn.microsoft.com/en-us/credentials/certifications/azure-administrator/?ns-enrollment-type=Collection&ns-enrollment-id=2d5pizzq7e8454&practice-assessment-type=certification)
- **Estimated Time**: 31 Hours 10 Mins
- **Study Plan**: 12 Days at 2.5 Hours a Day

### Pluralsight Course
- **Link**: [AZ-104 Microsoft Azure Administrator Certification Prep](https://app.pluralsight.com/library/courses/az-104-microsoft-azure-adminstrator-certification-prep/table-of-contents)
- **Estimated Time**: 15 Hours and 5 Mins
- **Study Plan**: 6 Days at 2.5 Hours a Day

### AZ-104 Administrator Associate Study Cram v2
- **Estimated Time**: 4 Hours 1 Min

## Study Plan

1. **Complete all Learn Modules**: Include notes for each section.
2. **Complete Pluralsight Course**: Update notes accordingly.

---

## Azure Administration Section

### Azure Resource Manager (ARM)
- **Definition**: Container that holds all Azure resources. Logical container based on lifecycle, security, and environment.
- **Structure**:
  - **Subscription**: Billing unit encompassing all contained resources.
  - **Resource Group**: Logical grouping of resources within a subscription.
  - **Resources**: Individual components (e.g., VMs, storage accounts).

- **ARM Operations**:
  - **Dashboard**: Customizable page to view performance and resource stats.
  - **Cloud Shell**: Allows usage of both Bash and PowerShell; auto-filled region when creating storage mounts. Times out after 20 minutes.
  - **New Key**: Required when deploying new VMs.

### Using Azure CLI and PowerShell

- **PowerShell**:
  - Create Resource Group: `New-AzResourceGroup`
  - List Resource Groups: `Get-AzResourceGroup`
  - Save Resource Group to Variable: `$rg = Get-AzResourceGroup`
  - Create VM:
    ```powershell
    Az vm Create `
    --resource-group $rg.ResourceGroupName `
    --Location $rg.Location `
    --name <VMName> `
    --Image <Image> `
    --admin-username <Username> `
    --generate-ssh-keys `
    --no-wait
    ```

  - List Resources: `Get-AzResource | Format-Table`
  - Get Cloud Drive Info: `Get-CloudDrive`

- **Azure CLI**:
  - Create Resource Group: `az group create --name <ResourceGroupName> --location <Location>`
  - List Resource Groups: `az group list`
  - Create VM:
    ```bash
    az vm create \
    --resource-group $rg.ResourceGroupName \
    --location $rg.Location \
    --name <VMName> \
    --image <Image> \
    --admin-username <Username> \
    --generate-ssh-keys \
    --no-wait
    ```

### Using ARM Templates

- **Infrastructure as Code (IaC)**: Deploy environments quickly and consistently.
- **Components**:
  - **Parameters**: User-defined values (e.g., VM size).
  - **Variables**: Hard-coded values.
  - **Resources**: Definitions of the resources to deploy.
  - **Outputs**: Return values from the template (e.g., IP addresses).

- **Deployment**:
  - Via GUI: Templates > Deploy a Custom Template > Paste GitHub template > Visualizer shows deployment plan.

### Governance and Compliance

- **Managing Subscriptions**:
  - **Subscriptions**: Created for departments to allocate costs.
  - **Management Groups**: Hierarchical organization for subscriptions and other management groups. Supports up to 6 levels.

- **Azure Policy**:
  - **Purpose**: Enforce compliance and auditing.
  - **Types**:
    - **Policy Definitions**: Define criteria for resources.
    - **Policy Assignments**: Apply policies at various scopes (management groups, subscriptions, resource groups).
    - **Initiative Definitions**: Collections of policies to achieve a broader goal.
  - **Policy Enforcement**: Prevents deployment if criteria are not met (e.g., missing tags).

- **Tagging Resources**:
  - **Tags**: Name:Value pairs for resource identification and cost management.
  - **Limits**: Max of 50 tags; value length restrictions vary.
  - **Application**: Tags must be manually assigned or set via Azure Policy.

- **Locking and Moving Resources**:
  - **Locks**:
    - **ReadOnly**: Prevents updates and deletions.
    - **CanNotDelete**: Prevents deletion but allows read and modify.
  - **Resource Movement**: Resources can be moved between resource groups and subscriptions, respecting locks.

- **Managing Azure Costs**:
  - **Subscription Types**: Free, Pay-as-you-go, Enterprise Agreement, Cloud Solution Provider.
  - **Cost Factors**:
    - **Resource Types**: Different pricing for Blob vs Table Storage.
    - **Usage Meters**: CPU time, traffic, disk size.
    - **Location**: Costs may vary by geo-region.
  - **Cost Management Tools**:
    - **Pricing Calculator**: Estimate costs before purchase.
    - **Cost of Ownership**: Compare on-prem costs to Azure.
    - **Microsoft Cost Management**: Cost analysis and budgeting.

- **Building a Cloud Governance Strategy**:
  - **Steps**:
    1. Define organizational needs (e.g., GDPR compliance).
    2. Plan governance tools and their implementation.
    3. Implement governance using management groups, RBAC, policies, tagging, and Azure Blueprints (integrates policies, subscriptions, resources, and RBAC).

### Identity Management
*(Note: Add specific details from the Microsoft Learn and Pluralsight courses related to Identity management, including Azure Active Directory, roles, and permissions, as you progress.)*

---

## Work in Progress

- Continue to integrate notes from the Microsoft Learn and Pluralsight modules.
- Expand details on Azure Identity Management.
- Update study plan based on additional materials and progress.
