# avi_clusterclouddetails

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_clusterclouddetails" {
  source = "./modules/avi/r/avi_clusterclouddetails"

  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  azure_info = [{
    cloud_credential_ref = null
    subscription_id      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_info" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cloud_credential_ref = string
      subscription_id      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_clusterclouddetails" "this" {
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "azure_info" {
    for_each = var.azure_info
    content {
      # cloud_credential_ref - (required) is a type of string
      cloud_credential_ref = azure_info.value["cloud_credential_ref"]
      # subscription_id - (required) is a type of string
      subscription_id = azure_info.value["subscription_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_clusterclouddetails.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_clusterclouddetails.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_clusterclouddetails.this.uuid
}

output "this" {
  value = avi_clusterclouddetails.this
}
```

[top](#index)