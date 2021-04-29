Graylog Message Categories 
============

The below table shows how Graylog is mapping ``gl2_event_type_code`` created in a pipeline, to a normalized category in our Illuminate Content.  Normalized categories allow for dashboards, searches, alert rules to use a common name across all device types utilizing this format.  An example of how this line looks like in the lookup tables is:

``"100000","|authentication|","|logon|","logon"``

The Code 100000, is attached to the log in the processing pipeline, and allows for the lookup function to attach a category, sub cateory and event type further down the processing chain.  

The Category in the above case is ``|authentication|``, where many types of events can fall.  Logon, Logoff and Session Disconnect all fall under authentication for easy grouping on dashboards.  A Subcategory of ``|logon|`` is applied as well to this log to signify this is happening during the logon process.  There can be many under logon, like a logon sucess, logon failure.  Finally the event type is added ``logon`` for further granularity of what this event was processed as.

Notes:
******
 - This document is a work in progress and fields will be added as content is developed.  If you have a suggestion, please open a GitHub ticket `HERE <https://github.com/Graylog2/graylog-schema/issues>`_. 


.. csv-table:: Graylog Message Categories 
   :file: categories.csv
   :widths: 10, 15, 10, 65
   :header-rows: 1
   :delim: ,
