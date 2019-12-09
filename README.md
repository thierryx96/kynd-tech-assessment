# kynd-tech-assessment

You are planning your next holiday for 2020, and want to know what is best time to take it in term of maximizing the length of the time away while minimizing your annual leave balance with your current employer.

Build a simple interface where the user can input the duration of the holiday (in number of days) and the system should provide you with the best option(s) over 2020.

- The first day is 1st jan 2020 and last is 31st of Dec. There is no span to 2019 or 2021.
- The public holidays (Queensland) will be fetched from our API using graphQL.
- holiday is > 4 

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








