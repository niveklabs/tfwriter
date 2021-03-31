# fortios_switchcontroller_location

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
module "fortios_switchcontroller_location" {
  source = "./modules/fortios/r/fortios_switchcontroller_location"

  # name - (optional) is a type of string
  name = null

  address_civic = [{
    additional           = null
    additional_code      = null
    block                = null
    branch_road          = null
    building             = null
    city                 = null
    city_division        = null
    country              = null
    country_subdivision  = null
    county               = null
    direction            = null
    floor                = null
    landmark             = null
    language             = null
    name                 = null
    number               = null
    number_suffix        = null
    parent_key           = null
    place_type           = null
    post_office_box      = null
    postal_community     = null
    primary_road         = null
    road_section         = null
    room                 = null
    script               = null
    seat                 = null
    street               = null
    street_name_post_mod = null
    street_name_pre_mod  = null
    street_suffix        = null
    sub_branch_road      = null
    trailing_str_suffix  = null
    unit                 = null
    zip                  = null
  }]

  coordinates = [{
    altitude      = null
    altitude_unit = null
    datum         = null
    latitude      = null
    longitude     = null
    parent_key    = null
  }]

  elin_number = [{
    elin_num   = null
    parent_key = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "address_civic" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      additional           = string
      additional_code      = string
      block                = string
      branch_road          = string
      building             = string
      city                 = string
      city_division        = string
      country              = string
      country_subdivision  = string
      county               = string
      direction            = string
      floor                = string
      landmark             = string
      language             = string
      name                 = string
      number               = string
      number_suffix        = string
      parent_key           = string
      place_type           = string
      post_office_box      = string
      postal_community     = string
      primary_road         = string
      road_section         = string
      room                 = string
      script               = string
      seat                 = string
      street               = string
      street_name_post_mod = string
      street_name_pre_mod  = string
      street_suffix        = string
      sub_branch_road      = string
      trailing_str_suffix  = string
      unit                 = string
      zip                  = string
    }
  ))
  default = []
}

variable "coordinates" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      altitude      = string
      altitude_unit = string
      datum         = string
      latitude      = string
      longitude     = string
      parent_key    = string
    }
  ))
  default = []
}

variable "elin_number" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      elin_num   = string
      parent_key = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_location" "this" {
  name = var.name

  dynamic "address_civic" {
    for_each = var.address_civic
    content {
      additional           = address_civic.value["additional"]
      additional_code      = address_civic.value["additional_code"]
      block                = address_civic.value["block"]
      branch_road          = address_civic.value["branch_road"]
      building             = address_civic.value["building"]
      city                 = address_civic.value["city"]
      city_division        = address_civic.value["city_division"]
      country              = address_civic.value["country"]
      country_subdivision  = address_civic.value["country_subdivision"]
      county               = address_civic.value["county"]
      direction            = address_civic.value["direction"]
      floor                = address_civic.value["floor"]
      landmark             = address_civic.value["landmark"]
      language             = address_civic.value["language"]
      name                 = address_civic.value["name"]
      number               = address_civic.value["number"]
      number_suffix        = address_civic.value["number_suffix"]
      parent_key           = address_civic.value["parent_key"]
      place_type           = address_civic.value["place_type"]
      post_office_box      = address_civic.value["post_office_box"]
      postal_community     = address_civic.value["postal_community"]
      primary_road         = address_civic.value["primary_road"]
      road_section         = address_civic.value["road_section"]
      room                 = address_civic.value["room"]
      script               = address_civic.value["script"]
      seat                 = address_civic.value["seat"]
      street               = address_civic.value["street"]
      street_name_post_mod = address_civic.value["street_name_post_mod"]
      street_name_pre_mod  = address_civic.value["street_name_pre_mod"]
      street_suffix        = address_civic.value["street_suffix"]
      sub_branch_road      = address_civic.value["sub_branch_road"]
      trailing_str_suffix  = address_civic.value["trailing_str_suffix"]
      unit                 = address_civic.value["unit"]
      zip                  = address_civic.value["zip"]
    }
  }

  dynamic "coordinates" {
    for_each = var.coordinates
    content {
      altitude      = coordinates.value["altitude"]
      altitude_unit = coordinates.value["altitude_unit"]
      datum         = coordinates.value["datum"]
      latitude      = coordinates.value["latitude"]
      longitude     = coordinates.value["longitude"]
      parent_key    = coordinates.value["parent_key"]
    }
  }

  dynamic "elin_number" {
    for_each = var.elin_number
    content {
      elin_num   = elin_number.value["elin_num"]
      parent_key = elin_number.value["parent_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_location.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_location.this.name
}

output "this" {
  value = fortios_switchcontroller_location.this
}
```

[top](#index)