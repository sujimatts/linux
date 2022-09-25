
```
0 0 0/1 1/1 * ? *
| |  |   |  | | | 
| |  |   |  | | +-- Year              (range: 1970-2099)
| |  |   |  | +---- Day of the Week   (range: 1-7 or SUN-SAT)
| |  |   |  +------ Month of the Year (range: 0-11 or JAN-DEC)
| |  |   +--------- Day of the Month  (range: 1-31)
| |  +------------- Hour              (range: 0-23)
| +---------------- Minute            (range: 0-59)
+------------------ Second            (range: 0-59)
```

```* (“all values”)```

used to select all values within a field. For example, “” in the minute field means *“every minute”.

```? (“no specific value”)```

useful when you need to specify something in one of the two fields in which the character is allowed, but not the other. For example, if I want my trigger to fire on a particular day of the month (say, the 10th), but don’t care what day of the week that happens to be, I would put “10” in the day-of-month field, and “?” in the day-of-week field.

```/```

used to specify increments. For example, “0/15” in the seconds field means “the seconds 0, 15, 30, and 45”. And “5/15” in the seconds field means “the seconds 5, 20, 35, and 50”. You can also specify ‘/’ after the ‘’ character - in this case ‘’ is equivalent to having ‘0’ before the ‘/’. ‘1/3’ in the day-of-month field means “fire every 3 days starting on the first day of the month”.

