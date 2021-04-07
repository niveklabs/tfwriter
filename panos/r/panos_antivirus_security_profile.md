# panos_antivirus_security_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_antivirus_security_profile" {
  source = "./modules/panos/r/panos_antivirus_security_profile"

  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # packet_capture - (optional) is a type of bool
  packet_capture = null
  # threat_exceptions - (optional) is a type of list of string
  threat_exceptions = []
  # vsys - (optional) is a type of string
  vsys = null

  application_exception = [{
    action      = null
    application = null
  }]

  decoder = [{
    action                  = null
    machine_learning_action = null
    name                    = null
    wildfire_action         = null
  }]

  machine_learning_exception = [{
    description = null
    filename    = null
    name        = null
  }]

  machine_learning_model = [{
    action = null
    model  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "packet_capture" {
  description = "(optional) - Set to true to enable packet capture"
  type        = bool
  default     = null
}

variable "threat_exceptions" {
  description = "(optional) - List of threat exceptions"
  type        = list(string)
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_exception" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action      = string
      application = string
    }
  ))
  default = []
}

variable "decoder" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action                  = string
      machine_learning_action = string
      name                    = string
      wildfire_action         = string
    }
  ))
  default = []
}

variable "machine_learning_exception" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      filename    = string
      name        = string
    }
  ))
  default = []
}

variable "machine_learning_model" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      model  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_antivirus_security_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # packet_capture - (optional) is a type of bool
  packet_capture = var.packet_capture
  # threat_exceptions - (optional) is a type of list of string
  threat_exceptions = var.threat_exceptions
  # vsys - (optional) is a type of string
  vsys = var.vsys

  dynamic "application_exception" {
    for_each = var.application_exception
    content {
      # action - (optional) is a type of string
      action = application_exception.value["action"]
      # application - (required) is a type of string
      application = application_exception.value["application"]
    }
  }

  dynamic "decoder" {
    for_each = var.decoder
    content {
      # action - (optional) is a type of string
      action = decoder.value["action"]
      # machine_learning_action - (optional) is a type of string
      machine_learning_action = decoder.value["machine_learning_action"]
      # name - (required) is a type of string
      name = decoder.value["name"]
      # wildfire_action - (optional) is a type of string
      wildfire_action = decoder.value["wildfire_action"]
    }
  }

  dynamic "machine_learning_exception" {
    for_each = var.machine_learning_exception
    content {
      # description - (optional) is a type of string
      description = machine_learning_exception.value["description"]
      # filename - (optional) is a type of string
      filename = machine_learning_exception.value["filename"]
      # name - (required) is a type of string
      name = machine_learning_exception.value["name"]
    }
  }

  dynamic "machine_learning_model" {
    for_each = var.machine_learning_model
    content {
      # action - (required) is a type of string
      action = machine_learning_model.value["action"]
      # model - (required) is a type of string
      model = machine_learning_model.value["model"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_antivirus_security_profile.this.id
}

output "this" {
  value = panos_antivirus_security_profile.this
}
```

[top](#index)