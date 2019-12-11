# kynd-tech-assessment

You are planning your next holiday for 2020, and want to know what is best time to take it in term of maximizing the length of the time away while minimizing your annual leave balance with your current employer.

Build a simple interface where the user can input the duration of the holiday (in number of days) and the system should provide you with the best option(s) over 2020.

- A holiday is a consecutive number of days
- The first day is 1st jan 2020 and last is 31st of Dec. There is no span to 2019 or 2021.
- The public holidays (Queensland) will be fetched from our API using graphQL.
- Holiday is > 4 

```
Example 1: duration of holiday is 4 days.
2 best options: 
- 10/04/2020 to 13/04/2020 (0 days of annual leave)
- 25/12/2020 to 28/12/2020 (0 days of annual leave)

Example 2: duration of holiday is 5 days.
4 best options: 
- 09/04/2020 to 13/04/2020 (1 day of annual leave)
- 10/04/2020 to 14/04/2020 (1 day of annual leave)
- 24/12/2020 to 28/12/2020 (1 day of annual leave)
- 25/12/2020 to 29/12/2020 (1 day of annual leave)

--TODO
Example 3: duration of holiday is 10 days.
4 best options: 
- 09/04/2020 to 13/04/2020 (1 day of annual leave)
- 10/04/2020 to 14/04/2020 (1 day of annual leave)
- 24/12/2020 to 28/12/2020 (1 day of annual leave)
- 25/12/2020 to 29/12/2020 (1 day of annual leave)
```

## GraphQL

Use the playground there : https://lfym1mly5f.execute-api.us-east-2.amazonaws.com/dev/graphql. This documents the endpoint.

There, you can type and execute the following query :
```
query {
  publicHolidays(jurisdictions: [QLD]) {
    date
    name
    day
    description
    jurisdiction
  }
}
```

Which should give the following output:
```
{
  "data": {
    "publicHolidays": [
      {
        "date": "2020-01-01T00:00:00.000Z",
        "name": "New Year's Day",
        "day": "2020-01-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-01-01T00:00:00.000Z",
        "name": "Australia Day",
        "day": "2020-01-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-01T00:00:00.000Z",
        "name": "Good Friday",
        "day": "2020-04-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-01T00:00:00.000Z",
        "name": "Easter Saturday",
        "day": "2020-04-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-01T00:00:00.000Z",
        "name": "Easter Sunday",
        "day": "2020-04-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-01T00:00:00.000Z",
        "name": "Easter Monday",
        "day": "2020-04-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-01T00:00:00.000Z",
        "name": "Anzac Day",
        "day": "2020-04-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-05-01T00:00:00.000Z",
        "name": "Labour Day",
        "day": "2020-05-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-10-01T00:00:00.000Z",
        "name": "Queen's Birthday",
        "day": "2020-10-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-12-01T00:00:00.000Z",
        "name": "Christmas Day",
        "day": "2020-12-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-12-01T00:00:00.000Z",
        "name": "Boxing Day",
        "day": "2020-12-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-12-01T00:00:00.000Z",
        "name": "Boxing Day (Additional day)",
        "day": "2020-12-01",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      }
    ]
  }
}
```




