# tencentcloud_api_gateway_service_release

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
module "tencentcloud_api_gateway_service_release" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_service_release"

  # environment_name - (required) is a type of string
  environment_name = null
  # release_desc - (required) is a type of string
  release_desc = null
  # release_version - (optional) is a type of string
  release_version = null
  # service_id - (required) is a type of string
  service_id = null
}
```

[top](#index)

### Variables

```terraform
variable "environment_name" {
  description = "(required) - API gateway service environment name to be released. Valid values: `test`, `prepub`, `release`."
  type        = string
}

variable "release_desc" {
  description = "(required) - This release description of the API gateway service."
  type        = string
}

variable "release_version" {
  description = "(optional) - The release version."
  type        = string
  default     = null
}

variable "service_id" {
  description = "(required) - ID of API gateway service."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_api_gateway_service_release" "this" {
  environment_name = var.environment_name
  release_desc     = var.release_desc
  release_version  = var.release_version
  service_id       = var.service_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_service_release.this.id
}

output "release_version" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_service_release.this.release_version
}

output "this" {
  value = tencentcloud_api_gateway_service_release.this
}
```

[top](#index)