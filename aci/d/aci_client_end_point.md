# aci_client_end_point

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_client_end_point" {
  source = "./modules/aci/d/aci_client_end_point"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # ip - (optional) is a type of string
  ip = null
  # mac - (optional) is a type of string
  mac = null
  # name - (optional) is a type of string
  name = null
  # vlan - (optional) is a type of string
  vlan = null

  fvcep_objects = [{
    application_profile_name = null
    endpoint_path            = []
    epg_name                 = null
    instance_profile_name    = null
    ip                       = null
    l2out_name               = null
    mac                      = null
    name                     = null
    tenant_name              = null
    vlan                     = null
    vrf_name                 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fvcep_objects" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      application_profile_name = string
      endpoint_path            = list(string)
      epg_name                 = string
      instance_profile_name    = string
      ip                       = string
      l2out_name               = string
      mac                      = string
      name                     = string
      tenant_name              = string
      vlan                     = string
      vrf_name                 = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aci_client_end_point" "this" {
  annotation  = var.annotation
  description = var.description
  ip          = var.ip
  mac         = var.mac
  name        = var.name
  vlan        = var.vlan

  dynamic "fvcep_objects" {
    for_each = var.fvcep_objects
    content {
      application_profile_name = fvcep_objects.value["application_profile_name"]
      endpoint_path            = fvcep_objects.value["endpoint_path"]
      epg_name                 = fvcep_objects.value["epg_name"]
      instance_profile_name    = fvcep_objects.value["instance_profile_name"]
      ip                       = fvcep_objects.value["ip"]
      l2out_name               = fvcep_objects.value["l2out_name"]
      mac                      = fvcep_objects.value["mac"]
      name                     = fvcep_objects.value["name"]
      tenant_name              = fvcep_objects.value["tenant_name"]
      vlan                     = fvcep_objects.value["vlan"]
      vrf_name                 = fvcep_objects.value["vrf_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_client_end_point.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_client_end_point.this.id
}

output "ip" {
  description = "returns a string"
  value       = data.aci_client_end_point.this.ip
}

output "mac" {
  description = "returns a string"
  value       = data.aci_client_end_point.this.mac
}

output "name" {
  description = "returns a string"
  value       = data.aci_client_end_point.this.name
}

output "vlan" {
  description = "returns a string"
  value       = data.aci_client_end_point.this.vlan
}

output "this" {
  value = aci_client_end_point.this
}
```

[top](#index)