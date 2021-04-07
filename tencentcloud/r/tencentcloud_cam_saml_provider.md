# tencentcloud_cam_saml_provider

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_cam_saml_provider" {
  source = "./modules/tencentcloud/r/tencentcloud_cam_saml_provider"

  # description - (required) is a type of string
  description = null
  # meta_data - (required) is a type of string
  meta_data = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required) - The description of the CAM SAML provider."
  type        = string
}

variable "meta_data" {
  description = "(required) - The meta data document of the CAM SAML provider."
  type        = string
}

variable "name" {
  description = "(required) - Name of CAM SAML provider."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cam_saml_provider" "this" {
  # description - (required) is a type of string
  description = var.description
  # meta_data - (required) is a type of string
  meta_data = var.meta_data
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cam_saml_provider.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cam_saml_provider.this.id
}

output "provider_arn" {
  description = "returns a string"
  value       = tencentcloud_cam_saml_provider.this.provider_arn
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_cam_saml_provider.this.update_time
}

output "this" {
  value = tencentcloud_cam_saml_provider.this
}
```

[top](#index)