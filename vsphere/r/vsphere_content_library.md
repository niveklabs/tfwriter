# vsphere_content_library

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_content_library" {
  source = "./modules/vsphere/r/vsphere_content_library"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # storage_backing - (required) is a type of set of string
  storage_backing = []

  publication = [{
    authentication_method = null
    password              = null
    publish_url           = null
    published             = null
    username              = null
  }]

  subscription = [{
    authentication_method = null
    automatic_sync        = null
    on_demand             = null
    password              = null
    subscription_url      = null
    username              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Optional description of the content library."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the content library."
  type        = string
}

variable "storage_backing" {
  description = "(required) - The name of the content library."
  type        = set(string)
}

variable "publication" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      authentication_method = string
      password              = string
      publish_url           = string
      published             = bool
      username              = string
    }
  ))
  default = []
}

variable "subscription" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      authentication_method = string
      automatic_sync        = bool
      on_demand             = bool
      password              = string
      subscription_url      = string
      username              = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_content_library" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # storage_backing - (required) is a type of set of string
  storage_backing = var.storage_backing

  dynamic "publication" {
    for_each = var.publication
    content {
      # authentication_method - (optional) is a type of string
      authentication_method = publication.value["authentication_method"]
      # password - (optional) is a type of string
      password = publication.value["password"]
      # published - (optional) is a type of bool
      published = publication.value["published"]
      # username - (optional) is a type of string
      username = publication.value["username"]
    }
  }

  dynamic "subscription" {
    for_each = var.subscription
    content {
      # authentication_method - (optional) is a type of string
      authentication_method = subscription.value["authentication_method"]
      # automatic_sync - (optional) is a type of bool
      automatic_sync = subscription.value["automatic_sync"]
      # on_demand - (optional) is a type of bool
      on_demand = subscription.value["on_demand"]
      # password - (optional) is a type of string
      password = subscription.value["password"]
      # subscription_url - (optional) is a type of string
      subscription_url = subscription.value["subscription_url"]
      # username - (optional) is a type of string
      username = subscription.value["username"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_content_library.this.id
}

output "this" {
  value = vsphere_content_library.this
}
```

[top](#index)