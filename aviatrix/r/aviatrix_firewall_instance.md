# aviatrix_firewall_instance

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
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_firewall_instance" {
  source = "./modules/aviatrix/r/aviatrix_firewall_instance"

  # bootstrap_bucket_name - (optional) is a type of string
  bootstrap_bucket_name = null
  # bootstrap_storage_name - (optional) is a type of string
  bootstrap_storage_name = null
  # container_folder - (optional) is a type of string
  container_folder = null
  # egress_subnet - (required) is a type of string
  egress_subnet = null
  # file_share_folder - (optional) is a type of string
  file_share_folder = null
  # firenet_gw_name - (required) is a type of string
  firenet_gw_name = null
  # firewall_image - (required) is a type of string
  firewall_image = null
  # firewall_image_version - (optional) is a type of string
  firewall_image_version = null
  # firewall_name - (required) is a type of string
  firewall_name = null
  # firewall_size - (required) is a type of string
  firewall_size = null
  # iam_role - (optional) is a type of string
  iam_role = null
  # key_name - (optional) is a type of string
  key_name = null
  # management_subnet - (optional) is a type of string
  management_subnet = null
  # password - (optional) is a type of string
  password = null
  # sas_url_config - (optional) is a type of string
  sas_url_config = null
  # sas_url_license - (optional) is a type of string
  sas_url_license = null
  # share_directory - (optional) is a type of string
  share_directory = null
  # sic_key - (optional) is a type of string
  sic_key = null
  # ssh_public_key - (optional) is a type of string
  ssh_public_key = null
  # storage_access_key - (optional) is a type of string
  storage_access_key = null
  # user_data - (optional) is a type of string
  user_data = null
  # username - (optional) is a type of string
  username = null
  # vpc_id - (required) is a type of string
  vpc_id = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "bootstrap_bucket_name" {
  description = "(optional) - Advanced option. Bootstrap bucket name. Only available for AWS."
  type        = string
  default     = null
}

variable "bootstrap_storage_name" {
  description = "(optional) - Advanced option. Bootstrap storage name. Applicable to Azure and Palo Alto Networks VM-Series/Fortinet Series deployment only."
  type        = string
  default     = null
}

variable "container_folder" {
  description = "(optional) - Advanced option. Bootstrap storage name. Applicable to Azure and Fortinet Series deployment only."
  type        = string
  default     = null
}

variable "egress_subnet" {
  description = "(required) - Egress Interface Subnet."
  type        = string
}

variable "file_share_folder" {
  description = "(optional) - Advanced option. File share folder. Applicable to Azure and Palo Alto Networks VM-Series deployment only."
  type        = string
  default     = null
}

variable "firenet_gw_name" {
  description = "(required) - Name of the primary FireNet gateway."
  type        = string
}

variable "firewall_image" {
  description = "(required) - One of the AWS AMIs from Palo Alto Networks."
  type        = string
}

variable "firewall_image_version" {
  description = "(optional) - Version of firewall image."
  type        = string
  default     = null
}

variable "firewall_name" {
  description = "(required) - Name of the firewall instance to be created."
  type        = string
}

variable "firewall_size" {
  description = "(required) - Instance size of the firewall."
  type        = string
}

variable "iam_role" {
  description = "(optional) - Advanced option. IAM role. Only available for AWS."
  type        = string
  default     = null
}

variable "key_name" {
  description = "(optional) - The .pem file name for SSH access to the firewall instance."
  type        = string
  default     = null
}

variable "management_subnet" {
  description = "(optional) - Management Interface Subnet. Required for Palo Alto Networks VM-Series, and required to be empty for Check Point or Fortinet series."
  type        = string
  default     = null
}

variable "password" {
  description = "(optional) - Authentication method. Applicable to Azure deployment only."
  type        = string
  default     = null
}

variable "sas_url_config" {
  description = "(optional) - Advanced option. Bootstrap storage name. Applicable to Azure and Fortinet Series deployment only."
  type        = string
  default     = null
}

variable "sas_url_license" {
  description = "(optional) - Advanced option. Bootstrap storage name. Applicable to Azure and Fortinet Series deployment only."
  type        = string
  default     = null
}

variable "share_directory" {
  description = "(optional) - Advanced option. Share directory. Applicable to Azure and Palo Alto Networks VM-Series deployment only."
  type        = string
  default     = null
}

variable "sic_key" {
  description = "(optional) - Advanced option. Bic key. Applicable to Azure and Check Point Series deployment only."
  type        = string
  default     = null
}

variable "ssh_public_key" {
  description = "(optional) - Authentication method. Applicable to Azure deployment only."
  type        = string
  default     = null
}

variable "storage_access_key" {
  description = "(optional) - Advanced option. Storage access key. Applicable to Azure and Palo Alto Networks VM-Series deployment only."
  type        = string
  default     = null
}

variable "user_data" {
  description = "(optional) - Advanced option. Bootstrap storage name. Applicable to Check Point Series and Fortinet Series deployment only."
  type        = string
  default     = null
}

variable "username" {
  description = "(optional) - Applicable to Azure deployment only. 'admin' as a username is not accepted."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of the Security VPC."
  type        = string
}

variable "zone" {
  description = "(optional) - Availability Zone. Only available for AZURE. Must be in the form 'az-n', for example, 'az-2'."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_firewall_instance" "this" {
  bootstrap_bucket_name  = var.bootstrap_bucket_name
  bootstrap_storage_name = var.bootstrap_storage_name
  container_folder       = var.container_folder
  egress_subnet          = var.egress_subnet
  file_share_folder      = var.file_share_folder
  firenet_gw_name        = var.firenet_gw_name
  firewall_image         = var.firewall_image
  firewall_image_version = var.firewall_image_version
  firewall_name          = var.firewall_name
  firewall_size          = var.firewall_size
  iam_role               = var.iam_role
  key_name               = var.key_name
  management_subnet      = var.management_subnet
  password               = var.password
  sas_url_config         = var.sas_url_config
  sas_url_license        = var.sas_url_license
  share_directory        = var.share_directory
  sic_key                = var.sic_key
  ssh_public_key         = var.ssh_public_key
  storage_access_key     = var.storage_access_key
  user_data              = var.user_data
  username               = var.username
  vpc_id                 = var.vpc_id
  zone                   = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "egress_interface" {
  description = "returns a string"
  value       = aviatrix_firewall_instance.this.egress_interface
}

output "firewall_image_version" {
  description = "returns a string"
  value       = aviatrix_firewall_instance.this.firewall_image_version
}

output "id" {
  description = "returns a string"
  value       = aviatrix_firewall_instance.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = aviatrix_firewall_instance.this.instance_id
}

output "lan_interface" {
  description = "returns a string"
  value       = aviatrix_firewall_instance.this.lan_interface
}

output "management_interface" {
  description = "returns a string"
  value       = aviatrix_firewall_instance.this.management_interface
}

output "public_ip" {
  description = "returns a string"
  value       = aviatrix_firewall_instance.this.public_ip
}

output "this" {
  value = aviatrix_firewall_instance.this
}
```

[top](#index)