# triton_package

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_package" {
  source = "./modules/triton/d/triton_package"


  filter = [{
    disk    = null
    group   = null
    lwps    = null
    memory  = null
    name    = null
    swap    = null
    vcpus   = null
    version = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      disk    = number
      group   = string
      lwps    = number
      memory  = number
      name    = string
      swap    = number
      vcpus   = number
      version = string
    }
  ))
}
```

[top](#index)

### Datasource

```terraform
data "triton_package" "this" {

  dynamic "filter" {
    for_each = var.filter
    content {
      disk    = filter.value["disk"]
      group   = filter.value["group"]
      lwps    = filter.value["lwps"]
      memory  = filter.value["memory"]
      name    = filter.value["name"]
      swap    = filter.value["swap"]
      vcpus   = filter.value["vcpus"]
      version = filter.value["version"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "disk" {
  description = "returns a number"
  value       = data.triton_package.this.disk
}

output "group" {
  description = "returns a string"
  value       = data.triton_package.this.group
}

output "id" {
  description = "returns a string"
  value       = data.triton_package.this.id
}

output "lwps" {
  description = "returns a number"
  value       = data.triton_package.this.lwps
}

output "memory" {
  description = "returns a number"
  value       = data.triton_package.this.memory
}

output "name" {
  description = "returns a string"
  value       = data.triton_package.this.name
}

output "swap" {
  description = "returns a number"
  value       = data.triton_package.this.swap
}

output "vcpus" {
  description = "returns a number"
  value       = data.triton_package.this.vcpus
}

output "version" {
  description = "returns a string"
  value       = data.triton_package.this.version
}

output "this" {
  value = triton_package.this
}
```

[top](#index)