Some Useful XQuery for IATI data
================================

Counts
------
Place queries in the brackets of count() to return the number found

Count number of activities

    count(//iati-activity)

Budgets
-------

Find budgets that have start dates after a certain date  
(replace yyyymmdd with year, month, and day. e.g. 1st Sept. 2013 would be 20130901])

    //budget[number(translate(period-start/@iso-date,'-','')) > yyyymmdd]

Find the activities that have a budget with a start date after a certain date  
(append /.. )
    
    //budget[number(translate(period-start/@iso-date,'-','')) > yyyymmdd]/..

Find the iati-identifiers of budgets that have start dates after a certain date
    
    //budget[number(translate(period-start/@iso-date,'-','')) > yyyymmdd]/..//iati-identifier
