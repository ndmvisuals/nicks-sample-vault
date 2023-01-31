---
id: a1881142-0267-44da-b5b6-074e1bc9b943
created: 1675140258538
updated: 1675140726311
---

This python code prints out the text calendar that I use here: [[home.calendar.2023]]

```python

from datetime import datetime
import calendar
import pandas as pd
import re
import numpy as np


def conditions(s):
    if (s['week_number'] == 52) & (s["month_full"] == "January"):
        return 0
    else:
        return s['week_number']

  
  

year = "2023"

df_dates = pd.DataFrame(pd.date_range(f'{year}-01-01', f'{year}-12-31', freq='D'), columns=["date"])

df_dates['month_full'] = df_dates['date'].dt.month_name()

df_dates["week_number"] = df_dates["date"].dt.isocalendar().week

df_dates["day_name"] = df_dates["date"].dt.day_name()

df_dates['week_number'] = df_dates.apply(conditions, axis = 1)

df_dates['week_number'] = df_dates['week_number'] + 1

ls_months = df_dates.month_full.unique()

calendar_string = f"Calendar {year}{chr(10)}## Archive{chr(10)}## Current"


for month in ls_months:
    filtered_month = df_dates.loc[(df_dates['month_full']  == month)]
    ls_dates = filtered_month.date.to_list()
    ls_day_names = filtered_month.day_name.to_list()
    ls_week_numbers = filtered_month.week_number.to_list()

    month_string = ""
    week_queue = []
    month_string = month_string + f"{chr(10)}### {month}"
    counter = 0 
        
    for i in range(len(ls_dates)):
        
        date = ls_dates[i].strftime("%Y-%m-%d")
        day = ls_day_names[i]
        week_number = ls_week_numbers[i]


        
        counter = counter +1 
        
        if counter == 1:
            month_string = month_string + f"{chr(10)}#### W{week_number-1}"
            week_queue.append(week_number)
        else:
            last_week = week_queue.pop()
            week_queue.append(week_number)
            if week_number != last_week:
                month_string = month_string + f"{chr(10)}#### W{week_number-1}"            
        
        month_string = month_string + f"{chr(10)}- {date} {day[0:3]}"
    calendar_string = calendar_string + month_string

print(calendar_string)

  

```