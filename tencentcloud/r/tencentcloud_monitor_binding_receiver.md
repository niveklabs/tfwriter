# tencentcloud_monitor_binding_receiver

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tencentcloud_monitor_binding_receiver" {
  source = "./modules/tencentcloud/r/tencentcloud_monitor_binding_receiver"

  # group_id - (required) is a type of number
  group_id = null

  receivers = [{
    end_time            = null
    notify_way          = []
    receive_language    = null
    receiver_group_list = []
    receiver_type       = null
    receiver_user_list  = []
    start_time          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required) - Policy group ID for binding receivers."
  type        = number
}

variable "receivers" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      end_time            = number
      notify_way          = list(string)
      receive_language    = string
      receiver_group_list = list(number)
      receiver_type       = string
      receiver_user_list  = list(number)
      start_time          = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_monitor_binding_receiver" "this" {
  # group_id - (required) is a type of number
  group_id = var.group_id

  dynamic "receivers" {
    for_each = var.receivers
    content {
      # end_time - (optional) is a type of number
      end_time = receivers.value["end_time"]
      # notify_way - (required) is a type of list of string
      notify_way = receivers.value["notify_way"]
      # receive_language - (optional) is a type of string
      receive_language = receivers.value["receive_language"]
      # receiver_group_list - (optional) is a type of list of number
      receiver_group_list = receivers.value["receiver_group_list"]
      # receiver_type - (required) is a type of string
      receiver_type = receivers.value["receiver_type"]
      # receiver_user_list - (optional) is a type of list of number
      receiver_user_list = receivers.value["receiver_user_list"]
      # start_time - (optional) is a type of number
      start_time = receivers.value["start_time"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_monitor_binding_receiver.this.id
}

output "this" {
  value = tencentcloud_monitor_binding_receiver.this
}
```

[top](#index)