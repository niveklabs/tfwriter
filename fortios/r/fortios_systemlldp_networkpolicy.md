# fortios_systemlldp_networkpolicy

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_systemlldp_networkpolicy" {
  source = "./modules/fortios/r/fortios_systemlldp_networkpolicy"

  # comment - (optional) is a type of string
  comment = null
  # name - (required) is a type of string
  name = null

  guest = [{
    dscp     = null
    priority = null
    status   = null
    tag      = null
    vlan     = null
  }]

  guest_voice_signaling = [{
    dscp     = null
    priority = null
    status   = null
    tag      = null
    vlan     = null
  }]

  softphone = [{
    dscp     = null
    priority = null
    status   = null
    tag      = null
    vlan     = null
  }]

  streaming_video = [{
    dscp     = null
    priority = null
    status   = null
    tag      = null
    vlan     = null
  }]

  video_conferencing = [{
    dscp     = null
    priority = null
    status   = null
    tag      = null
    vlan     = null
  }]

  video_signaling = [{
    dscp     = null
    priority = null
    status   = null
    tag      = null
    vlan     = null
  }]

  voice = [{
    dscp     = null
    priority = null
    status   = null
    tag      = null
    vlan     = null
  }]

  voice_signaling = [{
    dscp     = null
    priority = null
    status   = null
    tag      = null
    vlan     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "guest" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dscp     = number
      priority = number
      status   = string
      tag      = string
      vlan     = number
    }
  ))
  default = []
}

variable "guest_voice_signaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dscp     = number
      priority = number
      status   = string
      tag      = string
      vlan     = number
    }
  ))
  default = []
}

variable "softphone" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dscp     = number
      priority = number
      status   = string
      tag      = string
      vlan     = number
    }
  ))
  default = []
}

variable "streaming_video" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dscp     = number
      priority = number
      status   = string
      tag      = string
      vlan     = number
    }
  ))
  default = []
}

variable "video_conferencing" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dscp     = number
      priority = number
      status   = string
      tag      = string
      vlan     = number
    }
  ))
  default = []
}

variable "video_signaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dscp     = number
      priority = number
      status   = string
      tag      = string
      vlan     = number
    }
  ))
  default = []
}

variable "voice" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dscp     = number
      priority = number
      status   = string
      tag      = string
      vlan     = number
    }
  ))
  default = []
}

variable "voice_signaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dscp     = number
      priority = number
      status   = string
      tag      = string
      vlan     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_systemlldp_networkpolicy" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # name - (required) is a type of string
  name = var.name

  dynamic "guest" {
    for_each = var.guest
    content {
      # dscp - (optional) is a type of number
      dscp = guest.value["dscp"]
      # priority - (optional) is a type of number
      priority = guest.value["priority"]
      # status - (optional) is a type of string
      status = guest.value["status"]
      # tag - (optional) is a type of string
      tag = guest.value["tag"]
      # vlan - (optional) is a type of number
      vlan = guest.value["vlan"]
    }
  }

  dynamic "guest_voice_signaling" {
    for_each = var.guest_voice_signaling
    content {
      # dscp - (optional) is a type of number
      dscp = guest_voice_signaling.value["dscp"]
      # priority - (optional) is a type of number
      priority = guest_voice_signaling.value["priority"]
      # status - (optional) is a type of string
      status = guest_voice_signaling.value["status"]
      # tag - (optional) is a type of string
      tag = guest_voice_signaling.value["tag"]
      # vlan - (optional) is a type of number
      vlan = guest_voice_signaling.value["vlan"]
    }
  }

  dynamic "softphone" {
    for_each = var.softphone
    content {
      # dscp - (optional) is a type of number
      dscp = softphone.value["dscp"]
      # priority - (optional) is a type of number
      priority = softphone.value["priority"]
      # status - (optional) is a type of string
      status = softphone.value["status"]
      # tag - (optional) is a type of string
      tag = softphone.value["tag"]
      # vlan - (optional) is a type of number
      vlan = softphone.value["vlan"]
    }
  }

  dynamic "streaming_video" {
    for_each = var.streaming_video
    content {
      # dscp - (optional) is a type of number
      dscp = streaming_video.value["dscp"]
      # priority - (optional) is a type of number
      priority = streaming_video.value["priority"]
      # status - (optional) is a type of string
      status = streaming_video.value["status"]
      # tag - (optional) is a type of string
      tag = streaming_video.value["tag"]
      # vlan - (optional) is a type of number
      vlan = streaming_video.value["vlan"]
    }
  }

  dynamic "video_conferencing" {
    for_each = var.video_conferencing
    content {
      # dscp - (optional) is a type of number
      dscp = video_conferencing.value["dscp"]
      # priority - (optional) is a type of number
      priority = video_conferencing.value["priority"]
      # status - (optional) is a type of string
      status = video_conferencing.value["status"]
      # tag - (optional) is a type of string
      tag = video_conferencing.value["tag"]
      # vlan - (optional) is a type of number
      vlan = video_conferencing.value["vlan"]
    }
  }

  dynamic "video_signaling" {
    for_each = var.video_signaling
    content {
      # dscp - (optional) is a type of number
      dscp = video_signaling.value["dscp"]
      # priority - (optional) is a type of number
      priority = video_signaling.value["priority"]
      # status - (optional) is a type of string
      status = video_signaling.value["status"]
      # tag - (optional) is a type of string
      tag = video_signaling.value["tag"]
      # vlan - (optional) is a type of number
      vlan = video_signaling.value["vlan"]
    }
  }

  dynamic "voice" {
    for_each = var.voice
    content {
      # dscp - (optional) is a type of number
      dscp = voice.value["dscp"]
      # priority - (optional) is a type of number
      priority = voice.value["priority"]
      # status - (optional) is a type of string
      status = voice.value["status"]
      # tag - (optional) is a type of string
      tag = voice.value["tag"]
      # vlan - (optional) is a type of number
      vlan = voice.value["vlan"]
    }
  }

  dynamic "voice_signaling" {
    for_each = var.voice_signaling
    content {
      # dscp - (optional) is a type of number
      dscp = voice_signaling.value["dscp"]
      # priority - (optional) is a type of number
      priority = voice_signaling.value["priority"]
      # status - (optional) is a type of string
      status = voice_signaling.value["status"]
      # tag - (optional) is a type of string
      tag = voice_signaling.value["tag"]
      # vlan - (optional) is a type of number
      vlan = voice_signaling.value["vlan"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_systemlldp_networkpolicy.this.id
}

output "this" {
  value = fortios_systemlldp_networkpolicy.this
}
```

[top](#index)