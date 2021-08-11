# aws-rds-oracle-database-12c-stig-baseline

InSpec Profile to validate the secure configuration of AWS RDS instance of Oracle 12c, against [DISA's](https://iase.disa.mil/stigs/Pages/index.aspx) Oracle Database 12c STIG Ver 2, Rel 1

## Getting Started  
It is intended and recommended that InSpec run this profile from a __"runner"__ host (such as a DevOps orchestration server, an administrative management system, or a developer's workstation/laptop) against the target remotely over __ssh__.

The latest versions and installation options are available at the [InSpec](http://inspec.io/) site.

## Tailoring to Your Environment
The following inputs must be configured in an inputs ".yml" file for the profile to run correctly for your specific environment. More information about InSpec inputs can be found in the [InSpec Profile Documentation](https://www.inspec.io/docs/reference/profiles/).

```yaml
# username Oracle DB
user: ''

# password Oracle DB
password: ''

# hostname Oracle DB
host: ''

# service name Oracle DB
service: ''

# Location of sqlplus tool
sqlplus_bin: ''

# Set to true if standard auditing is used
standard_auditing_used: true

# Set to true if unified auditing is used
unified_auditing_used: false

# List of allowed database links
allowed_db_links: []

# List of allowed database admins
allowed_dbadmin_users: []

# List of users allowed access to PUBLIC
users_allowed_access_to_public: []

# List of users allowed the dba role
allowed_users_dba_role: []

# List of users allowed the system tablespace
allowed_users_system_tablespace: []

# List of application owners
allowed_application_owners: []

# List of allowed unlocked oracle db accounts
allowed_unlocked_oracledb_accounts: []

# List of users allowed access to the dictionary table
users_allowed_access_to_dictionary_table: []

# List of users allowed admin privileges
allowed_users_with_admin_privs: []

# List of users allowed audit access
allowed_audit_users: []

# List of allowed dba object owners
allowed_dbaobject_owners: []

# List of allowed oracle db components
allowed_oracledb_components: []

# List of oracle db components allowed to be intregrated into the dbms
allowed_oracledb_components_integrated_into_dbms: []

# List of allowed oracle dba's
oracle_dbas: []
```

# Running This Baseline Directly from Github

```
# How to run
inspec exec https://github.com/mitre/aws-rds-oracle-database-12c-stig-baseline/archive/master.tar.gz -t ssh:// --input-file=<path_to_your_inputs_file/name_of_your_inputs_file.yml> --reporter=cli json:<path_to_your_output_file/name_of_your_output_file.json>
```

### Different Run Options

  [Full exec options](https://docs.chef.io/inspec/cli/#options-3)

## Running This Baseline from a local Archive copy 

If your runner is not always expected to have direct access to GitHub, use the following steps to create an archive bundle of this baseline and all of its dependent tests:

(Git is required to clone the InSpec profile using the instructions below. Git can be downloaded from the [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) site.)

When the __"runner"__ host uses this profile baseline for the first time, follow these steps: 

```
mkdir profiles
cd profiles
git clone https://github.com/mitre/aws-rds-oracle-database-12c-stig-baseline
inspec archive aws-rds-oracle-database-12c-stig-baseline
inspec exec <name of generated archive> -t ssh:// --input-file=<path_to_your_inputs_file/name_of_your_inputs_file.yml> --reporter=cli json:<path_to_your_output_file/name_of_your_output_file.json>
```
For every successive run, follow these steps to always have the latest version of this baseline:

```
cd aws-rds-oracle-database-12c-stig-baseline
git pull
cd ..
inspec archive aws-rds-oracle-database-12c-stig-baseline --overwrite
inspec exec <name of generated archive> -t ssh:// --input-file=<path_to_your_inputs_file/name_of_your_inputs_file.yml> --reporter=cli json:<path_to_your_output_file/name_of_your_output_file.json>
```

## Viewing the JSON Results

The JSON results output file can be loaded into __[heimdall-lite](https://heimdall-lite.mitre.org/)__ for a user-interactive, graphical view of the InSpec results. 

The JSON InSpec results file may also be loaded into a __[full heimdall server](https://github.com/mitre/heimdall)__, allowing for additional functionality such as to store and compare multiple profile runs.

## Authors
* Mohamed El-Sharkawi - [HackerShark](https://github.com/HackerShark)

## Special Thanks 
* Shivani Karikar - [karikarshivani](https://github.com/karikarshivani)

## Contributing and Getting Help
To report a bug or feature request, please open an [issue](https://github.com/mitre/aws-rds-oracle-database-12c-stig-baseline/issues/new).

### NOTICE  

© 2018-2020 The MITRE Corporation.

Approved for Public Release; Distribution Unlimited. Case Number 18-3678.

## NOTICE  

MITRE hereby grants express written permission to use, reproduce, distribute, modify, and otherwise leverage this software to the extent permitted by the licensed terms provided in the [LICENSE.md](../LICENSE.md) file included with this project.

### NOTICE  

This software was produced for the U. S. Government under Contract Number HHSM-500-2012-00008I, and is subject to Federal Acquisition Regulation Clause 52.227-14, Rights in Data-General.  

No other use other than that granted to the U. S. Government, or to those acting on behalf of the U. S. Government under that Clause is authorized without the express written permission of The MITRE Corporation. 

For further information, please contact The MITRE Corporation, Contracts Management Office, 7515 Colshire Drive, McLean, VA  22102-7539, (703) 983-6000.  

## NOTICE  

DISA STIGs are published by DISA IASE, see: https://iase.disa.mil/Pages/privacy_policy.aspx
