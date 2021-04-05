# ecl_sss_tenant_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_sss_tenant_v1" {
  source = "./modules/ecl/d/ecl_sss_tenant_v1"

  # tenant_name - (required) is a type of string
  tenant_name = null
}
```

[top](#index)

### Variables

```terraform
variable "tenant_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ecl_sss_tenant_v1" "this" {
  tenant_name = var.tenant_name
}
```

[top](#index)

### Outputs

```terraform
output "contract_id" {
  description = "returns a string"
  value       = data.ecl_sss_tenant_v1.this.contract_id
}

output "description" {
  description = "returns a string"
  value       = data.ecl_sss_tenant_v1.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ecl_sss_tenant_v1.this.id
}

output "region" {
  description = "returns a string"
  value       = data.ecl_sss_tenant_v1.this.region
}

output "start_time" {
  description = "returns a string"
  value       = data.ecl_sss_tenant_v1.this.start_time
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_sss_tenant_v1.this.tenant_id
}

output "this" {
  value = ecl_sss_tenant_v1.this
}
```

[top](#index)