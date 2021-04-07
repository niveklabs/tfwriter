# tencentcloud_gaap_proxies

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
module "tencentcloud_gaap_proxies" {
  source = "./modules/tencentcloud/d/tencentcloud_gaap_proxies"

  # access_region - (optional) is a type of string
  access_region = null
  # ids - (optional) is a type of set of string
  ids = []
  # project_id - (optional) is a type of number
  project_id = null
  # realserver_region - (optional) is a type of string
  realserver_region = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "access_region" {
  description = "(optional) - Access region of the GAAP proxy to be queried. Conflict with `ids`."
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional) - ID of the GAAP proxy to be queried. Conflict with `project_id`, `access_region` and `realserver_region`."
  type        = set(string)
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID of the GAAP proxy to be queried. Conflict with `ids`."
  type        = number
  default     = null
}

variable "realserver_region" {
  description = "(optional) - Region of the GAAP realserver to be queried. Conflict with `ids`."
  type        = string
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
data "tencentcloud_gaap_proxies" "this" {
  access_region      = var.access_region
  ids                = var.ids
  project_id         = var.project_id
  realserver_region  = var.realserver_region
  result_output_file = var.result_output_file
  tags               = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_proxies.this.id
}

output "proxies" {
  description = "returns a list of object"
  value       = data.tencentcloud_gaap_proxies.this.proxies
}

output "this" {
  value = tencentcloud_gaap_proxies.this
}
```

[top](#index)