# tencentcloud_security_group_lite_rule

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tencentcloud_security_group_lite_rule" {
  source = "./modules/tencentcloud/r/tencentcloud_security_group_lite_rule"

  # egress - (optional) is a type of list of string
  egress = []
  # ingress - (optional) is a type of list of string
  ingress = []
  # security_group_id - (required) is a type of string
  security_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "egress" {
  description = "(optional) - Egress rules set. A rule must match the following format: [action]#[cidr_ip]#[port]#[protocol]. The available value of 'action' is `ACCEPT` and `DROP`. The 'cidr_ip' must be an IP address network or segment. The 'port' valid format is `80`, `80,443`, `80-90` or `ALL`. The available value of 'protocol' is `TCP`, `UDP`, `ICMP` and `ALL`. When 'protocol' is `ICMP` or `ALL`, the 'port' must be `ALL`."
  type        = list(string)
  default     = null
}

variable "ingress" {
  description = "(optional) - Ingress rules set. A rule must match the following format: [action]#[cidr_ip]#[port]#[protocol]. The available value of 'action' is `ACCEPT` and `DROP`. The 'cidr_ip' must be an IP address network or segment. The 'port' valid format is `80`, `80,443`, `80-90` or `ALL`. The available value of 'protocol' is `TCP`, `UDP`, `ICMP` and `ALL`. When 'protocol' is `ICMP` or `ALL`, the 'port' must be `ALL`."
  type        = list(string)
  default     = null
}

variable "security_group_id" {
  description = "(required) - ID of the security group."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_security_group_lite_rule" "this" {
  # egress - (optional) is a type of list of string
  egress = var.egress
  # ingress - (optional) is a type of list of string
  ingress = var.ingress
  # security_group_id - (required) is a type of string
  security_group_id = var.security_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_security_group_lite_rule.this.id
}

output "this" {
  value = tencentcloud_security_group_lite_rule.this
}
```

[top](#index)