# aws-rds-oracle-database-12c-stig-baseline

InSpec profile testing secure configuration of AWS Oracle 12c Database Server.

## Description

This InSpec compliance profile is a collection of automated tests for secure configuration of the AWS Oracle 12c Database Server.

InSpec is an open-source run-time framework and rule language used to specify compliance, security, and policy requirements for testing any node in your infrastructure.

## Requirements

- [ruby](https://www.ruby-lang.org/en/) version 2.4  or greater
- [InSpec](http://inspec.io/) version 3.x or greater
    - Install via ruby gem: `gem install inspec`


## Usage
InSpec makes it easy to run tests wherever you need. More options listed here: [InSpec cli](http://inspec.io/docs/reference/cli/)

The following attributes must be configured in an attributes file for the profile to run correctly. More information about InSpec attributes can be found in the [InSpec Profile Documentation](https://www.inspec.io/docs/reference/profiles/).

### Configuring the inputs in your inputs.yml file
```yaml
# description: Username Oracle DB (e.g., 'system')
user: ''

# description: Password Oracle DB (e.g., 'xvIA7zonxGM=1')
password: ''

# description: Hostname Oracle DB (e.g., 'localhost')
host: ''

# description: Service name Oracle DB (e.g., 'ORCLCDB')
service: ''

# description: Location of sqlplus tool (e.g., '/opt/oracle/product/12.2.0.1/dbhome_1/bin/sqlplus')
sqlplus_bin: ''

# description: Set to true if standard auditing is used
standard_auditing_used: false 

# description: Set to true if unified auditing is used
unified_auditing_used: false

# description: List of allowed database links
allowed_db_links: []

# description: List of allowed database admins
allowed_dbadmin_users: []

# description: List of users allowed access to PUBLIC
users_allowed_access_to_public: []

# description: List of users allowed the dba role
allowed_users_dba_role: []

# description: List of users allowed the system tablespace
allowed_users_system_tablespace: []

# description: List of application owners
allowed_application_owners: []

# description: List of allowed unlocked Oracle db accounts
allowed_unlocked_oracledb_accounts: []

# description: List of users allowed access to the dictionary table
users_allowed_access_to_dictionary_table: []

# description: List of users allowed admin privileges
allowed_users_with_admin_privs: []

# description: List of users allowed audit access
allowed_audit_users: []

# description: List of allowed dba object owners
allowed_dbaobject_owners: []

# description: List of allowed Oracle db components
allowed_oracledb_components: []

# description: List of Oracle db components allowed to be intregrated into the dbms
allowed_oracledb_components_integrated_into_dbms: []

# description: List of allowed Oracle dba's
oracle_dbas: []
```

### Run with remote profile:
You may choose to run the profile via a remote url, this has the advantage of always being up to date.
The disadvantage is you may wish to modify controls, which is only possible when downloaded.
Also, the remote profile is unintuitive for passing in attributes, which modify the default values of the profile.
``` bash
inspec exec https://github.com/mitre/aws-rds-oracle-database-12c-stig-baseline.git
```

Another option is to download the profile then run it, this allows you to edit specific instructions and view the profile code.
``` bash
# Clone Inspec Profile
$ git clone https://github.com/mitre/aws-rds-oracle-database-12c-stig-baseline.git

# Run profile locally (assuming you have not changed directories since cloning)
# This will display compliance level at the prompt, and generate a JSON file 
# for export called output.json
$ inspec exec aws-rds-oracle-database-12c-stig-baseline --input-file inputs.yml --reporter cli json:output.json

# Run profile with custom settings defined in attributes.yml against the target 
# server example.com. 
$ inspec exec aws-rds-oracle-database-12c-stig-baseline -t ssh://user@password:example.com --input-file inputs.yml --reporter cli json:output.json

# Run profile with: custom attributes, ssh keyed into a custom target, and sudo.
$ inspec exec aws-rds-oracle-database-12c-stig-baseline -t ssh://user@hostname -i /path/to/key --sudo --input-file inputs.yml --reporter cli json:output.json
```

## Contributors + Kudos

- Aaron Lippold
- Eugene Aronne
- The MITRE InSpec Team

## License and Author

### Authors
- Author:: Mohamed El-Sharkawi

### License  

* This project is licensed under the terms of the Apache license 2.0 (apache-2.0)

### NOTICE  

© 2018 The MITRE Corporation.  

Approved for Public Release; Distribution Unlimited. Case Number 18-3678.  

## NOTICE  

MITRE hereby grants express written permission to use, reproduce, distribute, modify, and otherwise leverage this software to the extent permitted by the licensed terms provided in the [LICENSE.md](../LICENSE.md) file included with this project.

### NOTICE  

This software was produced for the U. S. Government under Contract Number HHSM-500-2012-00008I, and is subject to Federal Acquisition Regulation Clause 52.227-14, Rights in Data-General.  

No other use other than that granted to the U. S. Government, or to those acting on behalf of the U. S. Government under that Clause is authorized without the express written permission of The MITRE Corporation. 

For further information, please contact The MITRE Corporation, Contracts Management Office, 7515 Colshire Drive, McLean, VA  22102-7539, (703) 983-6000.  

## NOTICE  

CIS Benchmarks are published by the Center for Internet Security (CIS), see: https://www.cisecurity.org/cis-benchmarks/.   