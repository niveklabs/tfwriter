# tencentcloud_gaap_realservers

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
module "tencentcloud_gaap_realservers" {
  source = "./modules/tencentcloud/d/tencentcloud_gaap_realservers"

  # domain - (optional) is a type of string
  domain = null
  # ip - (optional) is a type of string
  ip = null
  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional) - Domain of the GAAP realserver to be queried, conflict with `ip`."
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional) - IP of the GAAP realserver to be queried, conflict with `domain`."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the GAAP realserver to be queried, the maximum length is 30."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - ID of the project within the GAAP realserver to be queried, default value is `-1`, no set means all projects."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the GAAP proxy to be queried. Support up to 5, display the information as long as it matches one."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_gaap_realservers" "this" {
  domain             = var.domain
  ip                 = var.ip
  name               = var.name
  project_id         = var.project_id
  result_output_file = var.result_output_file
  tags               = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_realservers.this.id
}

output "realservers" {
  description = "returns a list of object"
  value       = data.tencentcloud_gaap_realservers.this.realservers
}

output "this" {
  value = tencentcloud_gaap_realservers.this
}
```

[top](#index)