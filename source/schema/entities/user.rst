User Fields
===========

 - Possible Field Prefixes: source_* (e.g., “source_user_name”) or destination_* (e.g., "destination_user_name")
 - Where messages describe an action taken by one account impacting another account, the actor (account taking the action) will be described by the “source_user_*” fields and the subject (account for which the action was taken) will be described by the “user_*” fields; Examples include:
 
   * Authentication, where the authenticating service account context is provided
   * IAM events, where a user or service has performed an action that impacts a user or group

.. csv-table:: User Fields
   :file: user.csv
   :widths: 10, 15, 10, 65
   :header-rows: 1
   :delim: ,

.. csv-table:: Derived and Enriched Fields (values will be derived or added from external sources)
   :file: user_derived.csv
   :widths: 10, 15, 10, 65
   :header-rows: 1
   :delim: ,
