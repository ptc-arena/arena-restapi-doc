# Note on Date/Time Handling
All date/time fields in the API are UTC \(Zulu time\). The Arena application is based on Pacific Time, so Arena converts the date/time values to Pacific Time by subtracting the equivalent number of hours that UTC Time is ahead of Pacific. This is especially important for  editable fields effectivityPlannedDateTime, expirationDateTime and approvalDateTime in the  object . 

effectivityPlannedDateTime and expirationDateTime occur at 00:00:00 of the specified date after that conversion. 

approvalDateTime occurs at 23:59:59 of the specified date after the conversion.

Examples:

Specifying an expirationDateTime value of 2018\-02\-20T12:00:00Z would be converted to 2018/12/20, 04:00:00 Pacific Time, and the Change would expire at the first second of February 20, 2018.

Specifying an approvalDateTime value of 2018\-02\-20T12:00:00Z would be converted to 2018/12/20, 04:00:00 Pacific Time, and the Change approval deadine would pass at the last second of February 20, 2018.

