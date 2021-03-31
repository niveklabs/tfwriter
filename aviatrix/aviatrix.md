# aviatrix

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "aviatrix" {
  version = "2.18.2"

  # controller_ip - (required) is a type of string
  controller_ip = null
  # password - (required) is a type of string
  password = null
  # skip_version_validation - (optional) is a type of bool
  skip_version_validation = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Resources


- [aviatrix_account](./r/aviatrix_account.md)

- [aviatrix_account_user](./r/aviatrix_account_user.md)

- [aviatrix_arm_peer](./r/aviatrix_arm_peer.md)

- [aviatrix_aws_guard_duty](./r/aviatrix_aws_guard_duty.md)

- [aviatrix_aws_peer](./r/aviatrix_aws_peer.md)

- [aviatrix_aws_tgw](./r/aviatrix_aws_tgw.md)

- [aviatrix_aws_tgw_connect](./r/aviatrix_aws_tgw_connect.md)

- [aviatrix_aws_tgw_connect_peer](./r/aviatrix_aws_tgw_connect_peer.md)

- [aviatrix_aws_tgw_directconnect](./r/aviatrix_aws_tgw_directconnect.md)

- [aviatrix_aws_tgw_peering](./r/aviatrix_aws_tgw_peering.md)

- [aviatrix_aws_tgw_peering_domain_conn](./r/aviatrix_aws_tgw_peering_domain_conn.md)

- [aviatrix_aws_tgw_transit_gateway_attachment](./r/aviatrix_aws_tgw_transit_gateway_attachment.md)

- [aviatrix_aws_tgw_vpc_attachment](./r/aviatrix_aws_tgw_vpc_attachment.md)

- [aviatrix_aws_tgw_vpn_conn](./r/aviatrix_aws_tgw_vpn_conn.md)

- [aviatrix_azure_peer](./r/aviatrix_azure_peer.md)

- [aviatrix_azure_spoke_native_peering](./r/aviatrix_azure_spoke_native_peering.md)

- [aviatrix_azure_vng_conn](./r/aviatrix_azure_vng_conn.md)

- [aviatrix_cloudwatch_agent](./r/aviatrix_cloudwatch_agent.md)

- [aviatrix_controller_config](./r/aviatrix_controller_config.md)

- [aviatrix_controller_private_oob](./r/aviatrix_controller_private_oob.md)

- [aviatrix_datadog_agent](./r/aviatrix_datadog_agent.md)

- [aviatrix_device_aws_tgw_attachment](./r/aviatrix_device_aws_tgw_attachment.md)

- [aviatrix_device_interface_config](./r/aviatrix_device_interface_config.md)

- [aviatrix_device_registration](./r/aviatrix_device_registration.md)

- [aviatrix_device_tag](./r/aviatrix_device_tag.md)

- [aviatrix_device_transit_gateway_attachment](./r/aviatrix_device_transit_gateway_attachment.md)

- [aviatrix_device_virtual_wan_attachment](./r/aviatrix_device_virtual_wan_attachment.md)

- [aviatrix_filebeat_forwarder](./r/aviatrix_filebeat_forwarder.md)

- [aviatrix_firenet](./r/aviatrix_firenet.md)

- [aviatrix_firewall](./r/aviatrix_firewall.md)

- [aviatrix_firewall_instance](./r/aviatrix_firewall_instance.md)

- [aviatrix_firewall_instance_association](./r/aviatrix_firewall_instance_association.md)

- [aviatrix_firewall_management_access](./r/aviatrix_firewall_management_access.md)

- [aviatrix_firewall_policy](./r/aviatrix_firewall_policy.md)

- [aviatrix_firewall_tag](./r/aviatrix_firewall_tag.md)

- [aviatrix_fqdn](./r/aviatrix_fqdn.md)

- [aviatrix_fqdn_pass_through](./r/aviatrix_fqdn_pass_through.md)

- [aviatrix_fqdn_tag_rule](./r/aviatrix_fqdn_tag_rule.md)

- [aviatrix_gateway](./r/aviatrix_gateway.md)

- [aviatrix_gateway_certificate_config](./r/aviatrix_gateway_certificate_config.md)

- [aviatrix_gateway_dnat](./r/aviatrix_gateway_dnat.md)

- [aviatrix_gateway_snat](./r/aviatrix_gateway_snat.md)

- [aviatrix_geo_vpn](./r/aviatrix_geo_vpn.md)

- [aviatrix_netflow_agent](./r/aviatrix_netflow_agent.md)

- [aviatrix_periodic_ping](./r/aviatrix_periodic_ping.md)

- [aviatrix_proxy_config](./r/aviatrix_proxy_config.md)

- [aviatrix_rbac_group](./r/aviatrix_rbac_group.md)

- [aviatrix_rbac_group_access_account_attachment](./r/aviatrix_rbac_group_access_account_attachment.md)

- [aviatrix_rbac_group_permission_attachment](./r/aviatrix_rbac_group_permission_attachment.md)

- [aviatrix_rbac_group_user_attachment](./r/aviatrix_rbac_group_user_attachment.md)

- [aviatrix_remote_syslog](./r/aviatrix_remote_syslog.md)

- [aviatrix_saml_endpoint](./r/aviatrix_saml_endpoint.md)

- [aviatrix_segmentation_security_domain](./r/aviatrix_segmentation_security_domain.md)

- [aviatrix_segmentation_security_domain_association](./r/aviatrix_segmentation_security_domain_association.md)

- [aviatrix_segmentation_security_domain_connection_policy](./r/aviatrix_segmentation_security_domain_connection_policy.md)

- [aviatrix_site2cloud](./r/aviatrix_site2cloud.md)

- [aviatrix_splunk_logging](./r/aviatrix_splunk_logging.md)

- [aviatrix_spoke_gateway](./r/aviatrix_spoke_gateway.md)

- [aviatrix_spoke_transit_attachment](./r/aviatrix_spoke_transit_attachment.md)

- [aviatrix_spoke_vpc](./r/aviatrix_spoke_vpc.md)

- [aviatrix_sumologic_forwarder](./r/aviatrix_sumologic_forwarder.md)

- [aviatrix_trans_peer](./r/aviatrix_trans_peer.md)

- [aviatrix_transit_external_device_conn](./r/aviatrix_transit_external_device_conn.md)

- [aviatrix_transit_firenet_policy](./r/aviatrix_transit_firenet_policy.md)

- [aviatrix_transit_gateway](./r/aviatrix_transit_gateway.md)

- [aviatrix_transit_gateway_peering](./r/aviatrix_transit_gateway_peering.md)

- [aviatrix_transit_vpc](./r/aviatrix_transit_vpc.md)

- [aviatrix_tunnel](./r/aviatrix_tunnel.md)

- [aviatrix_vgw_conn](./r/aviatrix_vgw_conn.md)

- [aviatrix_vpc](./r/aviatrix_vpc.md)

- [aviatrix_vpn_cert_download](./r/aviatrix_vpn_cert_download.md)

- [aviatrix_vpn_profile](./r/aviatrix_vpn_profile.md)

- [aviatrix_vpn_user](./r/aviatrix_vpn_user.md)

- [aviatrix_vpn_user_accelerator](./r/aviatrix_vpn_user_accelerator.md)


[top](#index)

### Datasources


- [aviatrix_account](./d/aviatrix_account.md)

- [aviatrix_caller_identity](./d/aviatrix_caller_identity.md)

- [aviatrix_firenet](./d/aviatrix_firenet.md)

- [aviatrix_firenet_vendor_integration](./d/aviatrix_firenet_vendor_integration.md)

- [aviatrix_firewall](./d/aviatrix_firewall.md)

- [aviatrix_gateway](./d/aviatrix_gateway.md)

- [aviatrix_spoke_gateway](./d/aviatrix_spoke_gateway.md)

- [aviatrix_transit_gateway](./d/aviatrix_transit_gateway.md)

- [aviatrix_vpc](./d/aviatrix_vpc.md)

- [aviatrix_vpc_tracker](./d/aviatrix_vpc_tracker.md)


[top](#index)