# avi_controllerportalregistration

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
module "avi_controllerportalregistration" {
  source = "./modules/avi/r/avi_controllerportalregistration"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  asset = [{
    asset_id = null
  }]

  portal_auth = [{
    access_token = null
    instance_url = null
    jwt_token    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "asset" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      asset_id = string
    }
  ))
  default = []
}

variable "portal_auth" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_token = string
      instance_url = string
      jwt_token    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_controllerportalregistration" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid

  dynamic "asset" {
    for_each = var.asset
    content {
      asset_id = asset.value["asset_id"]
    }
  }

  dynamic "portal_auth" {
    for_each = var.portal_auth
    content {
      access_token = portal_auth.value["access_token"]
      instance_url = portal_auth.value["instance_url"]
      jwt_token    = portal_auth.value["jwt_token"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_controllerportalregistration.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_controllerportalregistration.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_controllerportalregistration.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_controllerportalregistration.this.uuid
}

output "this" {
  value = avi_controllerportalregistration.this
}
```

[top](#index)