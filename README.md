# DPDK-Project
DNS server based on DPDK 

# steps to follow

## Phase-1
 - setup pktgen
 - setup simple example skeleton applciation
 - use physical NIC or memif interface
 - send DNS PCAP packet to sample applciation

## Phase-2
 - If Physcial NIC is used, use RTE_FLOW and PTYPE to parse UDP header
 - create DNS header - refer kernel.org
 - parse headers in Software - DNS request | response
 - update counters for request & response
 - use hash|LPM tables for storing request|response from MAC-IP address

## phase-3
 - use reges or hyperscan to parse DNS request
 - enable multicore with UDP RSS (can move to phase2)

## phase-4:
 - use primary-secondary DPDK
 - where secondary does rx_burst and processing
 - and primary is initlialization.
