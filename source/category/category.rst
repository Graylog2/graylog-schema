Graylog Message Categories 
============

Categorization of messages is a fundamental building block of Illuminate. Categorization is the process of identifying and labelling messages by class, category, subcategory and type. The fields are defined as:

* ``gim_event_type_code`` - This is the value assigned to an event log message that will be read by Illuminate core and used to enrich the remaining text fields with category information.
* ``gim_event_class`` - Optional: Different categories can be group as a common class of events, where they may not share common fields but have some other association such as being related to endpoint activity.
* ``gim_event_category`` - A GIM category is used to identify messages related to a common subject, such as authentication or http web traffic, which share a common set of fields.
* ``gim_event_subcategory`` - The GIM subcategory is a more specific grouping of events based on common types of events, which use the fields defined in the parent category but can also use additional fields common to that subcategory.
* ``gim_event_type`` - The specific type of event being categorized.

The process of categorization involves the assignment of an event type code (See the table below for the mapping of type codes to categorical data) to the field ``gim_event_type_code``. This must be done prior to the execution of Illuminate core. When Core detects a message with a type code assignment in the field ``gim_event_type_code`` it will attempt to map the fields ``gim_event_class``, ``gim_event_category``, ``gim_event_subcategory``, and ``gim_event_type`` according to the assigned type code(s). 

Illuminate core then 

The below table shows how Graylog is mapping ``gim_event_type_code`` created in a pipeline, to a normalized category in our Illuminate Content.  Normalized categories allow for dashboards, searches, alert rules to use a common name across all device types utilizing this format.  An example of how this line looks like in the lookup tables is:

``100000,"","authentication","authentication.logon","logon"``

The columns are ``gim_event_type_code``, ``gim_event_class``, ``gim_event_category``, ``gim_event_subcategory``, and ``gim_event_type``. The columns have the same name as the fields that will be stored a message being categorized.

The Category in the above example is ``authentication``, where many types of events can fall.  Logon, Logoff and Session Disconnect all fall under authentication for easy grouping on dashboards.  A Subcategory of ``logon`` is applied as well to this log to signify this is happening during the logon process.  There can be many under logon, like a logon success, logon failure.  Finally the event type is added ``logon`` for further granularity of what this event was processed as.


While the type codes are numeric values, they are treated as strings. A message can be given one or more type codes, when adding more than one code the value should be treated as a list of type code values. Type codes are six-character values where the first two pair of characters identify the category, the second pair of characters identify the subcategory, and the third pair of characters identify the event type.


Notes:
******
 - This document is a work in progress and fields will be added as content is developed.  If you have a suggestion, please open a GitHub ticket `HERE <https://github.com/Graylog2/graylog-schema/issues>`_. 


.. csv-table:: Graylog Message Categories 
   :file: categories.csv
   :widths: 10, 15, 10, 65
   :header-rows: 1
   :delim: ,
