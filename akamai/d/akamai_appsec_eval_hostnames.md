# akamai_appsec_eval_hostnames

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_eval_hostnames" {
  source = "./modules/akamai/d/akamai_appsec_eval_hostnames"

  # config_id - (required) is a type of number
  config_id = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_eval_hostnames" "this" {
  config_id = var.config_id
  version   = var.version
}
```

[top](#index)

### Outputs

```terraform
output "hostnames" {
  description = "returns a list of string"
  value       = data.akamai_appsec_eval_hostnames.this.hostnames
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_eval_hostnames.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_eval_hostnames.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_eval_hostnames.this.output_text
}

output "this" {
  value = akamai_appsec_eval_hostnames.this
}
```

[top](#index)