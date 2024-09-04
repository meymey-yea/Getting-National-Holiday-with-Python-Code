# install supporting library
pip install holidays

# import libraries
from datetime import date
import holidays
import pandas as pd

# getting dataframe of Cambodia National Holiday 
cambodia_2024_holiday = pd.DataFrame(holidays.KH(years=2024, language="en_US").items(), columns=['Date', 'DateValue']) # in English

cambodia_2024_holiday = pd.DataFrame(holidays.KH(years=2024, language="en_KH").items(), columns=['Date', 'DateValue']) # in Khmer

# getting DF dataframe of United States National Holiday
us_2024_holiday = pd.DataFrame(holidays.US(years=2024, language="en_US").items(), columns=['Date', 'DateValue'])


## Extra

us_holidays = holidays.US()  # this is a dict-like object
# the below is the same, but takes a string:
us_holidays = holidays.country_holidays('KH') # this is a dict-like object

nyse_holidays = holidays.NYSE()  # this is a dict-like object
# the below is the same, but takes a string:
nyse_holidays = holidays.financial_holidays('NYSE')  # this is a dict-like object

date(2015, 1, 1) in us_holidays  # True
date(2015, 1, 2) in us_holidays  # False
us_holidays.get('2014-01-01')  # "New Year's Day"


## Source to change the country

 https://python-holidays.readthedocs.io/en/latest/
 https://python-holidays.readthedocs.io/en/latest/examples.html
