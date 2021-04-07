# sdm_ssh_ca_pubkey

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sdm = ">= 1.0.19"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sdm_ssh_ca_pubkey" {
  source = "./modules/sdm/d/sdm_ssh_ca_pubkey"

  # public_key - (optional) is a type of string
  public_key = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "public_key" {
  description = "(optional) - The SSH Certificate Authority Public Key."
  type        = string
  default     = null
}

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
data "sdm_ssh_ca_pubkey" "this" {
  # public_key - (optional) is a type of string
  public_key = var.public_key

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
output "id" {
  description = "returns a string"
  value       = data.sdm_ssh_ca_pubkey.this.id
}

output "this" {
  value = sdm_ssh_ca_pubkey.this
}
```

[top](#index)