# Holiday planner

## Instructions

You are planning your next holiday for 2020, and want to know what is best time to take it in term of maximizing the length of the time away while minimizing your annual leave balance with your current employer.

Build a simple interface where the user can input the duration of the holiday (in number of days) and the system should provide you with the best option(s) for 2020.

- A holiday is a consecutive number of days duration >= 4 and <= 25 days
- The year period starts on the 1st of Jan 2020 and ends 31st of Dec 2020.
- The public holidays (Queensland) will be fetched from our API using graphQL (https://lfym1mly5f.execute-api.us-east-2.amazonaws.com/dev/graphql)
- Keep it simple, i.e. UI-wise a simple number input for the holiday duration with a list of options (see example below) is enough.
- Preferrably use our the Kynd FrontEnd Stack with consists of `VueJS`, `vue-cli`, `Vuex`, `Apollo` (http://apollo.vuejs.org/) and `Typescript`. 
- Share a private repository or with your code, with a brief instruction on how to run it locally.


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
        "date": "2020-01-27T00:00:00.000Z",
        "name": "Australia Day",
        "day": "2020-01-27",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-10T00:00:00.000Z",
        "name": "Good Friday",
        "day": "2020-04-10",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-11T00:00:00.000Z",
        "name": "Easter Saturday",
        "day": "2020-04-11",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-12T00:00:00.000Z",
        "name": "Easter Sunday",
        "day": "2020-04-12",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-13T00:00:00.000Z",
        "name": "Easter Monday",
        "day": "2020-04-13",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-04-25T00:00:00.000Z",
        "name": "Anzac Day",
        "day": "2020-04-25",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-05-04T00:00:00.000Z",
        "name": "Labour Day",
        "day": "2020-05-04",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-10-05T00:00:00.000Z",
        "name": "Queen's Birthday",
        "day": "2020-10-05",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-12-25T00:00:00.000Z",
        "name": "Christmas Day",
        "day": "2020-12-25",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-12-26T00:00:00.000Z",
        "name": "Boxing Day",
        "day": "2020-12-26",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      },
      {
        "date": "2020-12-28T00:00:00.000Z",
        "name": "Boxing Day (Additional day)",
        "day": "2020-12-28",
        "description": "https://www.qld.gov.au/recreation/travel/holidays/public",
        "jurisdiction": "QLD"
      }
    ]
  }
}
```


## Bonus points 

- use Vuex as as a state management store
- allow the user to choose between differents jurisdiction (QLD, NSW) in Australia using the enum type from graphql to populate the dropdown.


## References

- Apollo Vue JS: http://apollo.vuejs.org/




