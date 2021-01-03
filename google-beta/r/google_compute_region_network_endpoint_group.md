# google_compute_region_network_endpoint_group

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_region_network_endpoint_group" {
  source = "./modules/google-beta/r/google_compute_region_network_endpoint_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # network_endpoint_type - (optional) is a type of string
  network_endpoint_type = null
  # project - (optional) is a type of string
  project = null
  # region - (required) is a type of string
  region = null

  app_engine = [{
    service  = null
    url_mask = null
    version  = null
  }]

  cloud_function = [{
    function = null
    url_mask = null
  }]

  cloud_run = [{
    service  = null
    tag      = null
    url_mask = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - An optional description of this resource. Provide this property when\nyou create the resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource; provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "network_endpoint_type" {
  description = "(optional) - Type of network endpoints in this network endpoint group. Defaults to SERVERLESS Default value: \"SERVERLESS\" Possible values: [\"SERVERLESS\"]"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(required) - A reference to the region where the Serverless NEGs Reside."
  type        = string
}

variable "app_engine" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      service  = string
      url_mask = string
      version  = string
    }
  ))
  default = []
}

variable "cloud_function" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      function = string
      url_mask = string
    }
  ))
  default = []
}

variable "cloud_run" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      service  = string
      tag      = string
      url_mask = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_compute_region_network_endpoint_group" "this" {
  description           = var.description
  name                  = var.name
  network_endpoint_type = var.network_endpoint_type
  project               = var.project
  region                = var.region

  dynamic "app_engine" {
    for_each = var.app_engine
    content {
      service  = app_engine.value["service"]
      url_mask = app_engine.value["url_mask"]
      version  = app_engine.value["version"]
    }
  }

  dynamic "cloud_function" {
    for_each = var.cloud_function
    content {
      function = cloud_function.value["function"]
      url_mask = cloud_function.value["url_mask"]
    }
  }

  dynamic "cloud_run" {
    for_each = var.cloud_run
    content {
      service  = cloud_run.value["service"]
      tag      = cloud_run.value["tag"]
      url_mask = cloud_run.value["url_mask"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_compute_region_network_endpoint_group.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_network_endpoint_group.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_region_network_endpoint_group.this.self_link
}

output "this" {
  value = google_compute_region_network_endpoint_group.this
}
```

[top](#index)