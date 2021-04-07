# hcp_consul_versions

[back](../hcp.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcp = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcp_consul_versions" {
  source = "./modules/hcp/d/hcp_consul_versions"


  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "hcp_consul_versions" "this" {

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "available" {
  description = "returns a list of string"
  value       = data.hcp_consul_versions.this.available
}

output "id" {
  description = "returns a string"
  value       = data.hcp_consul_versions.this.id
}

output "preview" {
  description = "returns a list of string"
  value       = data.hcp_consul_versions.this.preview
}

output "recommended" {
  description = "returns a string"
  value       = data.hcp_consul_versions.this.recommended
}

output "this" {
  value = hcp_consul_versions.this
}
```

[top](#index)