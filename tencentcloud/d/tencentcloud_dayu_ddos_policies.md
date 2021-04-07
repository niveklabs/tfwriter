# tencentcloud_dayu_ddos_policies

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_dayu_ddos_policies" {
  source = "./modules/tencentcloud/d/tencentcloud_dayu_ddos_policies"

  # policy_id - (optional) is a type of string
  policy_id = null
  # resource_type - (required) is a type of string
  resource_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_id" {
  description = "(optional) - ID of the DDoS policy to be query."
  type        = string
  default     = null
}

variable "resource_type" {
  description = "(required) - Type of the resource that the DDoS policy works for, valid values are `bgpip`, `bgp`, `bgp-multip` and `net`."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_dayu_ddos_policies" "this" {
  policy_id          = var.policy_id
  resource_type      = var.resource_type
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_dayu_ddos_policies.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_dayu_ddos_policies.this.list
}

output "this" {
  value = tencentcloud_dayu_ddos_policies.this
}
```

[top](#index)