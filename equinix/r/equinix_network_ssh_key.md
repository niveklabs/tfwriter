# equinix_network_ssh_key

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_network_ssh_key" {
  source = "./modules/equinix/r/equinix_network_ssh_key"

  # name - (required) is a type of string
  name = null
  # public_key - (required) is a type of string
  public_key = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of SSH key used for identification"
  type        = string
}

variable "public_key" {
  description = "(required) - The SSH public key. If this is a file, it can be read using the file interpolation function"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "equinix_network_ssh_key" "this" {
  # name - (required) is a type of string
  name = var.name
  # public_key - (required) is a type of string
  public_key = var.public_key

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = equinix_network_ssh_key.this.id
}

output "uuid" {
  description = "returns a string"
  value       = equinix_network_ssh_key.this.uuid
}

output "this" {
  value = equinix_network_ssh_key.this
}
```

[top](#index)