# ovh_me_installation_template

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_installation_template" {
  source = "./modules/ovh/d/ovh_me_installation_template"

  # template_name - (required) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "template_name" {
  description = "(required) - This template name"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ovh_me_installation_template" "this" {
  template_name = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "available_languages" {
  description = "returns a list of string"
  value       = data.ovh_me_installation_template.this.available_languages
}

output "beta" {
  description = "returns a bool"
  value       = data.ovh_me_installation_template.this.beta
}

output "bit_format" {
  description = "returns a number"
  value       = data.ovh_me_installation_template.this.bit_format
}

output "category" {
  description = "returns a string"
  value       = data.ovh_me_installation_template.this.category
}

output "customization" {
  description = "returns a list of object"
  value       = data.ovh_me_installation_template.this.customization
}

output "default_language" {
  description = "returns a string"
  value       = data.ovh_me_installation_template.this.default_language
}

output "deprecated" {
  description = "returns a bool"
  value       = data.ovh_me_installation_template.this.deprecated
}

output "description" {
  description = "returns a string"
  value       = data.ovh_me_installation_template.this.description
}

output "distribution" {
  description = "returns a string"
  value       = data.ovh_me_installation_template.this.distribution
}

output "family" {
  description = "returns a string"
  value       = data.ovh_me_installation_template.this.family
}

output "filesystems" {
  description = "returns a list of string"
  value       = data.ovh_me_installation_template.this.filesystems
}

output "hard_raid_configuration" {
  description = "returns a bool"
  value       = data.ovh_me_installation_template.this.hard_raid_configuration
}

output "id" {
  description = "returns a string"
  value       = data.ovh_me_installation_template.this.id
}

output "last_modification" {
  description = "returns a string"
  value       = data.ovh_me_installation_template.this.last_modification
}

output "lvm_ready" {
  description = "returns a bool"
  value       = data.ovh_me_installation_template.this.lvm_ready
}

output "partition_scheme" {
  description = "returns a list of object"
  value       = data.ovh_me_installation_template.this.partition_scheme
}

output "supports_distribution_kernel" {
  description = "returns a bool"
  value       = data.ovh_me_installation_template.this.supports_distribution_kernel
}

output "supports_gpt_label" {
  description = "returns a bool"
  value       = data.ovh_me_installation_template.this.supports_gpt_label
}

output "supports_rtm" {
  description = "returns a bool"
  value       = data.ovh_me_installation_template.this.supports_rtm
}

output "supports_sql_server" {
  description = "returns a bool"
  value       = data.ovh_me_installation_template.this.supports_sql_server
}

output "supports_uefi" {
  description = "returns a string"
  value       = data.ovh_me_installation_template.this.supports_uefi
}

output "this" {
  value = ovh_me_installation_template.this
}
```

[top](#index)