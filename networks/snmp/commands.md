# SNMP COMMANDS

## GET Command

**Technical Operation:** 
- Retrieves a specific single OID value directly from the agent's MIB using a precise OID reference

**Example Use Cases:**
- Getting current CPU utilization: Read exact current CPU usage percentage
- Checking a specific interface status: Verify if a particular network port is up/down

## GETNEXT Command

**Technical Operation:**
- Retrieves the next lexicographically ordered OID value from the specified OID in the MIB tree hierarchy

**Example Use Cases:**
- Finding next interface in routing table: Discover next available route entry
- Locating next available VLAN: Find next configured VLAN in sequence

## WALK Command

**Technical Operation:**
- Performs sequential GETNEXT operations automatically, traversing through a specified MIB subtree branch until completion

**Example Use Cases:**
- Collecting all storage mount points: Get complete list of mounted filesystems
- Gathering all configured VLANs: Retrieve all VLAN configurations

## BULKWALK Command

**Technical Operation:**
- Uses GETBULK operations to retrieve large blocks of data in fewer network transactions, optimizing the data retrieval process

**Use Cases:**
- Retrieving large routing tables: Efficiently collect thousands of routes
- Getting complete switch port statistics: Gather data from all interfaces at once

## SET Command

**Technical Operation:**
- Modifies specific OID values in the agent's MIB, requiring appropriate write permissions and correct value typing
**Example Use Cases:**
- Changing interface description: Update port description on network device
- Setting system location: Update physical location information of device
