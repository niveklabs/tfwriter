---
layout: resource
title: mso
type: provider
resource: mso
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "mso" {
  version = "0.1.5"

  # domain - (optional) is a type of string
  domain = null
  # insecure - (optional) is a type of bool
  insecure = null
  # password - (required) is a type of string
  password = null
  # proxy_url - (optional) is a type of string
  proxy_url = null
  # url - (required) is a type of string
  url = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Resources


- [mso_label](./r/mso_label.md)

- [mso_rest](./r/mso_rest.md)

- [mso_schema](./r/mso_schema.md)

- [mso_schema_site](./r/mso_schema_site.md)

- [mso_schema_site_anp](./r/mso_schema_site_anp.md)

- [mso_schema_site_anp_epg](./r/mso_schema_site_anp_epg.md)

- [mso_schema_site_anp_epg_domain](./r/mso_schema_site_anp_epg_domain.md)

- [mso_schema_site_anp_epg_selector](./r/mso_schema_site_anp_epg_selector.md)

- [mso_schema_site_anp_epg_static_leaf](./r/mso_schema_site_anp_epg_static_leaf.md)

- [mso_schema_site_anp_epg_static_port](./r/mso_schema_site_anp_epg_static_port.md)

- [mso_schema_site_anp_epg_subnet](./r/mso_schema_site_anp_epg_subnet.md)

- [mso_schema_site_bd](./r/mso_schema_site_bd.md)

- [mso_schema_site_bd_l3out](./r/mso_schema_site_bd_l3out.md)

- [mso_schema_site_bd_subnet](./r/mso_schema_site_bd_subnet.md)

- [mso_schema_site_external_epg_selector](./r/mso_schema_site_external_epg_selector.md)

- [mso_schema_site_service_graph_node](./r/mso_schema_site_service_graph_node.md)

- [mso_schema_site_vrf](./r/mso_schema_site_vrf.md)

- [mso_schema_site_vrf_region](./r/mso_schema_site_vrf_region.md)

- [mso_schema_site_vrf_region_cidr](./r/mso_schema_site_vrf_region_cidr.md)

- [mso_schema_site_vrf_region_cidr_subnet](./r/mso_schema_site_vrf_region_cidr_subnet.md)

- [mso_schema_template](./r/mso_schema_template.md)

- [mso_schema_template_anp](./r/mso_schema_template_anp.md)

- [mso_schema_template_anp_epg](./r/mso_schema_template_anp_epg.md)

- [mso_schema_template_anp_epg_contract](./r/mso_schema_template_anp_epg_contract.md)

- [mso_schema_template_anp_epg_selector](./r/mso_schema_template_anp_epg_selector.md)

- [mso_schema_template_anp_epg_subnet](./r/mso_schema_template_anp_epg_subnet.md)

- [mso_schema_template_anp_epg_useg_attr](./r/mso_schema_template_anp_epg_useg_attr.md)

- [mso_schema_template_bd](./r/mso_schema_template_bd.md)

- [mso_schema_template_bd_subnet](./r/mso_schema_template_bd_subnet.md)

- [mso_schema_template_contract](./r/mso_schema_template_contract.md)

- [mso_schema_template_contract_filter](./r/mso_schema_template_contract_filter.md)

- [mso_schema_template_contract_service_graph](./r/mso_schema_template_contract_service_graph.md)

- [mso_schema_template_deploy](./r/mso_schema_template_deploy.md)

- [mso_schema_template_external_epg](./r/mso_schema_template_external_epg.md)

- [mso_schema_template_external_epg_contract](./r/mso_schema_template_external_epg_contract.md)

- [mso_schema_template_external_epg_selector](./r/mso_schema_template_external_epg_selector.md)

- [mso_schema_template_external_epg_subnet](./r/mso_schema_template_external_epg_subnet.md)

- [mso_schema_template_filter_entry](./r/mso_schema_template_filter_entry.md)

- [mso_schema_template_l3out](./r/mso_schema_template_l3out.md)

- [mso_schema_template_service_graph](./r/mso_schema_template_service_graph.md)

- [mso_schema_template_vrf](./r/mso_schema_template_vrf.md)

- [mso_schema_template_vrf_contract](./r/mso_schema_template_vrf_contract.md)

- [mso_service_node_type](./r/mso_service_node_type.md)

- [mso_site](./r/mso_site.md)

- [mso_tenant](./r/mso_tenant.md)

- [mso_user](./r/mso_user.md)


[top](#index)

### Datasources


- [mso_label](./d/mso_label.md)

- [mso_role](./d/mso_role.md)

- [mso_schema](./d/mso_schema.md)

- [mso_schema_site](./d/mso_schema_site.md)

- [mso_schema_site_anp](./d/mso_schema_site_anp.md)

- [mso_schema_site_anp_epg](./d/mso_schema_site_anp_epg.md)

- [mso_schema_site_anp_epg_domain](./d/mso_schema_site_anp_epg_domain.md)

- [mso_schema_site_anp_epg_selector](./d/mso_schema_site_anp_epg_selector.md)

- [mso_schema_site_anp_epg_static_leaf](./d/mso_schema_site_anp_epg_static_leaf.md)

- [mso_schema_site_anp_epg_static_port](./d/mso_schema_site_anp_epg_static_port.md)

- [mso_schema_site_anp_epg_subnet](./d/mso_schema_site_anp_epg_subnet.md)

- [mso_schema_site_bd](./d/mso_schema_site_bd.md)

- [mso_schema_site_bd_l3out](./d/mso_schema_site_bd_l3out.md)

- [mso_schema_site_bd_subnet](./d/mso_schema_site_bd_subnet.md)

- [mso_schema_site_external_epg_selector](./d/mso_schema_site_external_epg_selector.md)

- [mso_schema_site_vrf](./d/mso_schema_site_vrf.md)

- [mso_schema_site_vrf_region](./d/mso_schema_site_vrf_region.md)

- [mso_schema_site_vrf_region_cidr](./d/mso_schema_site_vrf_region_cidr.md)

- [mso_schema_site_vrf_region_cidr_subnet](./d/mso_schema_site_vrf_region_cidr_subnet.md)

- [mso_schema_template](./d/mso_schema_template.md)

- [mso_schema_template_anp](./d/mso_schema_template_anp.md)

- [mso_schema_template_anp_epg](./d/mso_schema_template_anp_epg.md)

- [mso_schema_template_anp_epg_contract](./d/mso_schema_template_anp_epg_contract.md)

- [mso_schema_template_anp_epg_selector](./d/mso_schema_template_anp_epg_selector.md)

- [mso_schema_template_anp_epg_subnet](./d/mso_schema_template_anp_epg_subnet.md)

- [mso_schema_template_anp_epg_useg_attr](./d/mso_schema_template_anp_epg_useg_attr.md)

- [mso_schema_template_bd](./d/mso_schema_template_bd.md)

- [mso_schema_template_bd_subnet](./d/mso_schema_template_bd_subnet.md)

- [mso_schema_template_contract](./d/mso_schema_template_contract.md)

- [mso_schema_template_contract_filter](./d/mso_schema_template_contract_filter.md)

- [mso_schema_template_contract_service_graph](./d/mso_schema_template_contract_service_graph.md)

- [mso_schema_template_external_epg](./d/mso_schema_template_external_epg.md)

- [mso_schema_template_external_epg_contract](./d/mso_schema_template_external_epg_contract.md)

- [mso_schema_template_external_epg_selector](./d/mso_schema_template_external_epg_selector.md)

- [mso_schema_template_external_epg_subnet](./d/mso_schema_template_external_epg_subnet.md)

- [mso_schema_template_filter_entry](./d/mso_schema_template_filter_entry.md)

- [mso_schema_template_l3out](./d/mso_schema_template_l3out.md)

- [mso_schema_template_service_graph](./d/mso_schema_template_service_graph.md)

- [mso_schema_template_vrf](./d/mso_schema_template_vrf.md)

- [mso_schema_template_vrf_contract](./d/mso_schema_template_vrf_contract.md)

- [mso_service_node_type](./d/mso_service_node_type.md)

- [mso_site](./d/mso_site.md)

- [mso_tenant](./d/mso_tenant.md)

- [mso_user](./d/mso_user.md)


[top](#index)