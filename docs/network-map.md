# Hub-and-spoke network map

Owner: AntonioMisic77
Region: West Europe (weu)

| Network | Address space | Subnets | Peered with |
|---|---|---|---|
| vnet-hub-test-weu-001 | 10.0.0.0/16 | snet-shared 10.0.4.0/24 | spoke 1, spoke 2 |
| vnet-spoke1-test-weu-001 | 10.1.0.0/16 | snet-app 10.1.1.0/24, snet-pep 10.1.3.0/24 | hub |
| vnet-spoke2-test-weu-001 | 10.2.0.0/16 | snet-app 10.2.1.0/24 | hub |

Next free spoke address space: 10.3.0.0/16

## Name resolution

Private DNS zone hubspoke.internal is linked to all three networks.
Auto registration is on for spoke 1 only.

## Routing

Spoke 1 to hub: next hop VirtualNetworkPeering.
Spoke 1 to spoke 2: next hop None, because peering isn't transitive.