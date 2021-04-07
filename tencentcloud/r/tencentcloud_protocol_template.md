# tencentcloud_protocol_template

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
module "tencentcloud_protocol_template" {
  source = "./modules/tencentcloud/r/tencentcloud_protocol_template"

  # name - (required) is a type of string
  name = null
  # protocols - (required) is a type of set of string
  protocols = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the protocol template."
  type        = string
}

variable "protocols" {
  description = "(required) - Protocol list. Valid protocols are  `tcp`, `udp`, `icmp`, `gre`. Single port(tcp:80), multi-port(tcp:80,443), port range(tcp:3306-20000), all(tcp:all) format are support. Protocol `icmp` and `gre` cannot specify port."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_protocol_template" "this" {
  # name - (required) is a type of string
  name = var.name
  # protocols - (required) is a type of set of string
  protocols = var.protocols
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_protocol_template.this.id
}

output "this" {
  value = tencentcloud_protocol_template.this
}
```

[top](#index)