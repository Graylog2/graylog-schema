# Graylog Schema

This is the starting point for the Graylog Information Model (GIM).  The Schema is broken down into sections, like "File" or "Destination" with all meta data fields below that link.

This is version 1.0

# Graylog Template

During processing of the logs, data from the logs are inserted into Elasticsearch as "keywords", meaning hthye are not modified in any way, and stored as-is.  This means the follow data points are unique:

`Administrator`  or `administrator`

If you are doing a search in the Graylog UI, you would have to search for both of the terms, or know exactly which one to search for.  Fields like `user_name` make sense to have the ability to search without worrying about the case of the word.

In order to ensure these options are accounted for, a custom analyzer has been included in the Graylog Schema template, called "loweronly".  Fields normalized with "loweronly" will be converted to lowercase before the data is indexed, and search query strings for thse fields will be converted to lowercase as well when ran.  Pages in the schema, will list these fields as `keyword/loweronly` for reference.

# Graylog Help

If you see any suggestions, or feature requests for this project, please submit a issue [here](https://github.com/Graylog2/graylog-schema/issues).

Happy Logging! Atom
