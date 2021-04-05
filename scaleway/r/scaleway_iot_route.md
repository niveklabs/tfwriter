# scaleway_iot_route

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_iot_route" {
  source = "./modules/scaleway/r/scaleway_iot_route"

  # hub_id - (required) is a type of string
  hub_id = null
  # name - (required) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
  # topic - (required) is a type of string
  topic = null

  database = [{
    dbname   = null
    host     = null
    password = null
    port     = null
    query    = null
    username = null
  }]

  rest = [{
    headers = {}
    uri     = null
    verb    = null
  }]

  s3 = [{
    bucket_name   = null
    bucket_region = null
    object_prefix = null
    strategy      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "hub_id" {
  description = "(required) - The ID of the route's hub"
  type        = string
}

variable "name" {
  description = "(required) - The name of the route"
  type        = string
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "topic" {
  description = "(required) - The Topic the route subscribes to (wildcards allowed)"
  type        = string
}

variable "database" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dbname   = string
      host     = string
      password = string
      port     = number
      query    = string
      username = string
    }
  ))
  default = []
}

variable "rest" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers = map(string)
      uri     = string
      verb    = string
    }
  ))
  default = []
}

variable "s3" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_name   = string
      bucket_region = string
      object_prefix = string
      strategy      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_iot_route" "this" {
  hub_id = var.hub_id
  name   = var.name
  region = var.region
  topic  = var.topic

  dynamic "database" {
    for_each = var.database
    content {
      dbname   = database.value["dbname"]
      host     = database.value["host"]
      password = database.value["password"]
      port     = database.value["port"]
      query    = database.value["query"]
      username = database.value["username"]
    }
  }

  dynamic "rest" {
    for_each = var.rest
    content {
      headers = rest.value["headers"]
      uri     = rest.value["uri"]
      verb    = rest.value["verb"]
    }
  }

  dynamic "s3" {
    for_each = var.s3
    content {
      bucket_name   = s3.value["bucket_name"]
      bucket_region = s3.value["bucket_region"]
      object_prefix = s3.value["object_prefix"]
      strategy      = s3.value["strategy"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = scaleway_iot_route.this.created_at
}

output "id" {
  description = "returns a string"
  value       = scaleway_iot_route.this.id
}

output "region" {
  description = "returns a string"
  value       = scaleway_iot_route.this.region
}

output "this" {
  value = scaleway_iot_route.this
}
```

[top](#index)