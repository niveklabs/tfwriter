# tencentcloud_gaap_realserver

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
module "tencentcloud_gaap_realserver" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_realserver"

  # domain - (optional) is a type of string
  domain = null
  # ip - (optional) is a type of string
  ip = null
  # name - (required) is a type of string
  name = null
  # project_id - (optional) is a type of number
  project_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional) - Domain of the GAAP realserver, conflict with `ip`."
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional) - IP of the GAAP realserver, conflict with `domain`."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the GAAP realserver, the maximum length is 30."
  type        = string
}

variable "project_id" {
  description = "(optional) - ID of the project within the GAAP realserver, '0' means is default project."
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the GAAP realserver."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_gaap_realserver" "this" {
  # domain - (optional) is a type of string
  domain = var.domain
  # ip - (optional) is a type of string
  ip = var.ip
  # name - (required) is a type of string
  name = var.name
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_realserver.this.id
}

output "this" {
  value = tencentcloud_gaap_realserver.this
}
```

[top](#index)