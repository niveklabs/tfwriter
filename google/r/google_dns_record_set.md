# google_dns_record_set

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_dns_record_set" {
  source = "./modules/google/r/google_dns_record_set"

  # managed_zone - (required) is a type of string
  managed_zone = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # rrdatas - (required) is a type of list of string
  rrdatas = []
  # ttl - (required) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```hcl
variable "managed_zone" {
  description = "(required) - The name of the zone in which this record set will reside."
  type        = string
}

variable "name" {
  description = "(required) - The DNS name this record set will apply to."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "rrdatas" {
  description = "(required) - The string data for the records in this record set whose meaning depends on the DNS type. For TXT record, if the string data contains spaces, add surrounding \\\" if you don't want your string to get split on spaces. To specify a single record value longer than 255 characters such as a TXT record for DKIM, add \\\"\\\" inside the Terraform configuration string (e.g. \"first255characters\\\"\\\"morecharacters\")."
  type        = list(string)
}

variable "ttl" {
  description = "(required) - The time-to-live of this record set (seconds)."
  type        = number
}

variable "type" {
  description = "(required) - The DNS record set type."
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "google_dns_record_set" "this" {
  managed_zone = var.managed_zone
  name         = var.name
  project      = var.project
  rrdatas      = var.rrdatas
  ttl          = var.ttl
  type         = var.type
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = google_dns_record_set.this.id
}

output "project" {
  description = "returns a string"
  value       = google_dns_record_set.this.project
}

output "this" {
  value = google_dns_record_set.this
}
```

[top](#index)