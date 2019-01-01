# datetime
## datetime module   
import   
```python
import datetime
```
## Date
create a date
```python
datetime.date(2019, 1, 1)
```
get the current date
```python
tday = datetime.date.today()
```
get more info of tday
```python
tday.year
tday.day
tday.weekday() # monday is 0, sunday is 6
tday.isoweekday() # monday is 1, sunday is 7
```
time delta
```python
# print the date of 7 days later from today
tdelta = datetime.timedelta(days=7)
print(tday + tdelta)
```
print how many days/total_seconds from my birthday
```python
bday = datetime.date(2019, 9, 12)
tday = datetime.date.today()
till_bday = bday - tday
print(till_bday.days)
print(till_bday.total_seconds())
```
## Time   
create a new time
```python
t = datetime.time(9, 30, 45, 100000)
print(t.hour)
```
## Datetime
create a new datetime
```python
dt = datetime.datetime(2019, 1, 1, 9, 30, 45, 100000)
# grab the date/time from datetime
dt.date()
dt.time()
# grab some attr
dt.year
# time delta
tdelta = datetime.timedelta(hours=12)
print(dt + tdelta)
```
```python
datetime.datetime.today() # current local datetime with timezone of none
datetime.datetime.now() # gives an option to pass in a timezone
dt_utcnow = datetime.datetime.utcnow()
```
# pytz
```python
import datetime
import pytz

dt = datetime.datetime(2019, 1, 1, 9, 30, 45, tzinfo=pytz.UTC)
# get the current utc time
datetime.datetime.now(tz=pytz.UTC)
datetime.datetime.utcnow().replace(tzinfo=pytz.UTC)
```
manipulate timezone
```python
dt_utcnow = datetime.datetime.now(tz=pytz.UTC)
# get the eastern time
dt_est = dt_utcnow.astimezone(pytz.timezone('US/Eastern'))
```
get all timezone in pytz
```python
for tz in pytz.all_timezones:
    print(tz)
```
localize a naive datetime to timzone-aware datetime
```python
dt = datetime.datetime.now()
mtn_tz = pytz.timezone('US/Mountain')
dt_mtn = mtn_tz.localize(dt)
```
convert between timezones
```python
dt_east = dt_mtn.astimezone(pytz.timezone('US/Eastern'))
```
get a timezone-aware datetime's iso format
```python
dt_mtn.isoformat()
```
datetime to string
```python
dt_mtn.strftime('%B %d, %Y')
```
string to datetime
```python
dt_str = 'July 26, 2018'
dt = datetime.datetime.strptime(dt_str, '%B %d, %Y')
```
