# ovh_me_installation_template

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_installation_template" {
  source = "./modules/ovh/r/ovh_me_installation_template"

  # base_template_name - (required) is a type of string
  base_template_name = null
  # default_language - (required) is a type of string
  default_language = null
  # remove_default_partition_schemes - (optional) is a type of bool
  remove_default_partition_schemes = null
  # template_name - (required) is a type of string
  template_name = null

  customization = [{
    change_log                      = null
    custom_hostname                 = null
    post_installation_script_link   = null
    post_installation_script_return = null
    rating                          = null
    ssh_key_name                    = null
    use_distribution_kernel         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "base_template_name" {
  description = "(required) - OVH template name yours will be based on, choose one among the list given by compatibleTemplates function"
  type        = string
}

variable "default_language" {
  description = "(required) - The default language of this template"
  type        = string
}

variable "remove_default_partition_schemes" {
  description = "(optional) - Remove default partition schemes at creation"
  type        = bool
  default     = null
}

variable "template_name" {
  description = "(required) - This template name"
  type        = string
}

variable "customization" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      change_log                      = string
      custom_hostname                 = string
      post_installation_script_link   = string
      post_installation_script_return = string
      rating                          = number
      ssh_key_name                    = string
      use_distribution_kernel         = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ovh_me_installation_template" "this" {
  base_template_name               = var.base_template_name
  default_language                 = var.default_language
  remove_default_partition_schemes = var.remove_default_partition_schemes
  template_name                    = var.template_name

  dynamic "customization" {
    for_each = var.customization
    content {
      change_log                      = customization.value["change_log"]
      custom_hostname                 = customization.value["custom_hostname"]
      post_installation_script_link   = customization.value["post_installation_script_link"]
      post_installation_script_return = customization.value["post_installation_script_return"]
      rating                          = customization.value["rating"]
      ssh_key_name                    = customization.value["ssh_key_name"]
      use_distribution_kernel         = customization.value["use_distribution_kernel"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "available_languages" {
  description = "returns a list of string"
  value       = ovh_me_installation_template.this.available_languages
}

output "beta" {
  description = "returns a bool"
  value       = ovh_me_installation_template.this.beta
}

output "bit_format" {
  description = "returns a number"
  value       = ovh_me_installation_template.this.bit_format
}

output "category" {
  description = "returns a string"
  value       = ovh_me_installation_template.this.category
}

output "deprecated" {
  description = "returns a bool"
  value       = ovh_me_installation_template.this.deprecated
}

output "description" {
  description = "returns a string"
  value       = ovh_me_installation_template.this.description
}

output "distribution" {
  description = "returns a string"
  value       = ovh_me_installation_template.this.distribution
}

output "family" {
  description = "returns a string"
  value       = ovh_me_installation_template.this.family
}

output "filesystems" {
  description = "returns a list of string"
  value       = ovh_me_installation_template.this.filesystems
}

output "hard_raid_configuration" {
  description = "returns a bool"
  value       = ovh_me_installation_template.this.hard_raid_configuration
}

output "id" {
  description = "returns a string"
  value       = ovh_me_installation_template.this.id
}

output "last_modification" {
  description = "returns a string"
  value       = ovh_me_installation_template.this.last_modification
}

output "lvm_ready" {
  description = "returns a bool"
  value       = ovh_me_installation_template.this.lvm_ready
}

output "remove_default_partition_schemes" {
  description = "returns a bool"
  value       = ovh_me_installation_template.this.remove_default_partition_schemes
}

output "supports_distribution_kernel" {
  description = "returns a bool"
  value       = ovh_me_installation_template.this.supports_distribution_kernel
}

output "supports_gpt_label" {
  description = "returns a bool"
  value       = ovh_me_installation_template.this.supports_gpt_label
}

output "supports_rtm" {
  description = "returns a bool"
  value       = ovh_me_installation_template.this.supports_rtm
}

output "supports_sql_server" {
  description = "returns a bool"
  value       = ovh_me_installation_template.this.supports_sql_server
}

output "supports_uefi" {
  description = "returns a string"
  value       = ovh_me_installation_template.this.supports_uefi
}

output "this" {
  value = ovh_me_installation_template.this
}
```

[top](#index)