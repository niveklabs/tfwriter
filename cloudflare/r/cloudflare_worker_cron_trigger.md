# cloudflare_worker_cron_trigger

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_worker_cron_trigger" {
  source = "./modules/cloudflare/r/cloudflare_worker_cron_trigger"

  # schedules - (required) is a type of set of string
  schedules = []
  # script_name - (required) is a type of string
  script_name = null
}
```

[top](#index)

### Variables

```terraform
variable "schedules" {
  description = "(required)"
  type        = set(string)
}

variable "script_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_worker_cron_trigger" "this" {
  # schedules - (required) is a type of set of string
  schedules = var.schedules
  # script_name - (required) is a type of string
  script_name = var.script_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_worker_cron_trigger.this.id
}

output "this" {
  value = cloudflare_worker_cron_trigger.this
}
```

[top](#index)