# akamai_appsec_failover_hostnames

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
module "akamai_appsec_failover_hostnames" {
  source = "./modules/akamai/d/akamai_appsec_failover_hostnames"

  # config_id - (required) is a type of number
  config_id = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_failover_hostnames" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
}
```

[top](#index)

### Outputs

```terraform
output "hostnames" {
  description = "returns a list of string"
  value       = data.akamai_appsec_failover_hostnames.this.hostnames
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_failover_hostnames.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_failover_hostnames.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_failover_hostnames.this.output_text
}

output "this" {
  value = akamai_appsec_failover_hostnames.this
}
```

[top](#index)