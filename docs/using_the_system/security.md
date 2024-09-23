# Safety and Security

The safety and security of data stored at the DNP is of utmost importance.
We implement a number of security features to provide defense-in-depth for access to the computer systems and data.

## Physical Access and Safety

All DNP servers and workstations are located within locked areas of the Douglas Research Centre. Servers are stored
in locked and access restricted server rooms within the Douglas.

All workstations auto-lock when users leave them unattended for more than 5 minutes.
No data is stored directly on workstations, ensuring data-exfiltration risk from theft is minimized.

Servers are physically separated across the Douglas campus with continuous backups between them for disaster recovery.

## Data Safety and Security

Access to storage servers is restricted via hostname and IP, relying on the access controls to the network managed
by Douglas IT. Storage allocations are mounted on-demand providing some obfuscation for mount names. All mount exports
are exported with `root_squash` to enforce minimal permissions to workstations in the event of local compromise.

Permissions for all storage allocations are user and research-group based (UNIX users/groups), with default
permissions for newly created files owned by the user and group, and default read-only access for research group
members. Access Control Lists (ACLs) advanced permissions are available to provide additional targeted access for
other groups or users in addition to the owning user and research group.

All data storage has fine-to-coarse historical snapshots enabled, allowing recovery of deleted or modified files out to
6 months prior.

## User Account Security

User accounts are password protected with minimum complexity requirements based on entropy measurements of passwords.
Passwords are regularly audited for weaknesses against compromised password wordlists.
User accounts on creation are set to expire on timeframes appropriate with the student or employment position of the
users.

Authentication is achieved via centralized NIS services with restricted access based on IP and user level.