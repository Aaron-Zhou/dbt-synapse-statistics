# Synapse Statistics

This project can create statistic views to Azure Synapse Dedicated SQL Pool.
Sqls used in models were created base on Azure synapse dedicated sql pool development guide.

## Prerequisites
### dbt and plugin install
1. pip install dbt-core==1.3.0
2. pip install dbt-synapse==1.3.0

### ODBC driver install
Refer to Microsoftware's guide to [download and install driver](https://learn.microsoft.com/en-us/sql/connect/odbc/download-odbc-driver-for-sql-server?view=sql-server-ver16)

### dbt profile setup
Get Azure synapse dedicated sql pool connection details from synapse workspace management.
Adding those info to dbt profile yml - profiles.yml. Sample config is like:

Profile location: $HOME/.dbt/profiles.yml

```
default:
  target: synapse
  outputs:
    synapse:
      type: synapse
      driver: 'ODBC Driver 18 for SQL Server' # (The ODBC Driver installed on your system)
      server: "host" # (Dedicated SQL endpoint of your workspace here)
      port: 1433
      database: "db name"
      schema: "db schema"
      user: "user"
      password: "password"
```
## Running the project
Verify synapse connection:
- dbt debug

Try running the following commands:
- dbt run
- dbt test


## Resources
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Learn about [synapse dedicated sql pool](https://learn.microsoft.com/en-us/azure/synapse-analytics/sql-data-warehouse/sql-data-warehouse-overview-what-is)

## License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/Aaron-Zhou/dbt-synapse-statistics/blob/main/LICENSE)
