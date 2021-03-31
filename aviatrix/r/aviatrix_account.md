# aviatrix_account

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_account" {
  source = "./modules/aviatrix/r/aviatrix_account"

  # account_name - (required) is a type of string
  account_name = null
  # arm_application_id - (optional) is a type of string
  arm_application_id = null
  # arm_application_key - (optional) is a type of string
  arm_application_key = null
  # arm_directory_id - (optional) is a type of string
  arm_directory_id = null
  # arm_subscription_id - (optional) is a type of string
  arm_subscription_id = null
  # aws_access_key - (optional) is a type of string
  aws_access_key = null
  # aws_account_number - (optional) is a type of string
  aws_account_number = null
  # aws_iam - (optional) is a type of bool
  aws_iam = null
  # aws_role_app - (optional) is a type of string
  aws_role_app = null
  # aws_role_ec2 - (optional) is a type of string
  aws_role_ec2 = null
  # aws_secret_key - (optional) is a type of string
  aws_secret_key = null
  # awsgov_access_key - (optional) is a type of string
  awsgov_access_key = null
  # awsgov_account_number - (optional) is a type of string
  awsgov_account_number = null
  # awsgov_secret_key - (optional) is a type of string
  awsgov_secret_key = null
  # cloud_type - (required) is a type of number
  cloud_type = null
  # gcloud_project_credentials_filepath - (optional) is a type of string
  gcloud_project_credentials_filepath = null
  # gcloud_project_id - (optional) is a type of string
  gcloud_project_id = null
  # oci_api_private_key_filepath - (optional) is a type of string
  oci_api_private_key_filepath = null
  # oci_compartment_id - (optional) is a type of string
  oci_compartment_id = null
  # oci_tenancy_id - (optional) is a type of string
  oci_tenancy_id = null
  # oci_user_id - (optional) is a type of string
  oci_user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - Account name. This can be used for logging in to CloudN console or UserConnect controller."
  type        = string
}

variable "arm_application_id" {
  description = "(optional) - Azure Application ID."
  type        = string
  default     = null
}

variable "arm_application_key" {
  description = "(optional) - Azure Application Key."
  type        = string
  default     = null
}

variable "arm_directory_id" {
  description = "(optional) - Azure Directory ID."
  type        = string
  default     = null
}

variable "arm_subscription_id" {
  description = "(optional) - Azure Subscription ID."
  type        = string
  default     = null
}

variable "aws_access_key" {
  description = "(optional) - AWS Access Key."
  type        = string
  default     = null
}

variable "aws_account_number" {
  description = "(optional) - AWS Account number to associate with Aviatrix account. Should be 12 digits."
  type        = string
  default     = null
}

variable "aws_iam" {
  description = "(optional) - AWS IAM-role based flag."
  type        = bool
  default     = null
}

variable "aws_role_app" {
  description = "(optional) - AWS App role ARN."
  type        = string
  default     = null
}

variable "aws_role_ec2" {
  description = "(optional) - AWS EC2 role ARN."
  type        = string
  default     = null
}

variable "aws_secret_key" {
  description = "(optional) - AWS Secret Key."
  type        = string
  default     = null
}

variable "awsgov_access_key" {
  description = "(optional) - AWS Gov Access Key."
  type        = string
  default     = null
}

variable "awsgov_account_number" {
  description = "(optional) - AWS Gov Account number to associate with Aviatrix account."
  type        = string
  default     = null
}

variable "awsgov_secret_key" {
  description = "(optional) - AWS Gov Secret Key."
  type        = string
  default     = null
}

variable "cloud_type" {
  description = "(required) - Type of cloud service provider."
  type        = number
}

variable "gcloud_project_credentials_filepath" {
  description = "(optional) - GCloud Project credentials local file path."
  type        = string
  default     = null
}

variable "gcloud_project_id" {
  description = "(optional) - GCloud Project ID."
  type        = string
  default     = null
}

variable "oci_api_private_key_filepath" {
  description = "(optional) - OCI API Private Key local file path."
  type        = string
  default     = null
}

variable "oci_compartment_id" {
  description = "(optional) - OCI Compartment OCID."
  type        = string
  default     = null
}

variable "oci_tenancy_id" {
  description = "(optional) - OCI Tenancy OCID."
  type        = string
  default     = null
}

variable "oci_user_id" {
  description = "(optional) - OCI User OCID."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_account" "this" {
  account_name                        = var.account_name
  arm_application_id                  = var.arm_application_id
  arm_application_key                 = var.arm_application_key
  arm_directory_id                    = var.arm_directory_id
  arm_subscription_id                 = var.arm_subscription_id
  aws_access_key                      = var.aws_access_key
  aws_account_number                  = var.aws_account_number
  aws_iam                             = var.aws_iam
  aws_role_app                        = var.aws_role_app
  aws_role_ec2                        = var.aws_role_ec2
  aws_secret_key                      = var.aws_secret_key
  awsgov_access_key                   = var.awsgov_access_key
  awsgov_account_number               = var.awsgov_account_number
  awsgov_secret_key                   = var.awsgov_secret_key
  cloud_type                          = var.cloud_type
  gcloud_project_credentials_filepath = var.gcloud_project_credentials_filepath
  gcloud_project_id                   = var.gcloud_project_id
  oci_api_private_key_filepath        = var.oci_api_private_key_filepath
  oci_compartment_id                  = var.oci_compartment_id
  oci_tenancy_id                      = var.oci_tenancy_id
  oci_user_id                         = var.oci_user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_account.this.id
}

output "this" {
  value = aviatrix_account.this
}
```

[top](#index)