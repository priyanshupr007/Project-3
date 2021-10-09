from datetime import datetime
import calendar

D = {   
        '2020-01-01':6,'2020-01-04':12,'2020-01-05':14,'2020-01-06':2,'2020-01-07':4
    }
val = {'Mon':0, 'Tue':0, 'Wed':0, 'Thu':0, 'Fri':0, 'Sat':0, 'Sun':0 }
    
for x, y in D.items():
    curr_date = datetime.strptime(x, "%Y-%m-%d")
    
    ans =  calendar.day_name[curr_date.weekday()]
    if ans == 'Monday':
        val['Mon'] = val['Mon'] + y
    elif ans == 'Tuesday':
        val['Tue'] = val['Tue'] + y
    elif ans == 'Wednesday':
        val['Wed'] = val['Wed'] + y
    elif ans == 'Thursday':
        val['Thu'] = val['Thu'] + y
    elif ans == 'Friday':
        val['Fri'] = val['Fri'] + y
    elif ans == 'Saturday':
        val['Sat'] = val['Sat'] + y
    elif ans == 'Sunday':
        val['Sun'] = val['Sun'] + y

d=0
y=0
t=0
par=0
temp_p = 0
for a,b in val.items():
    temp2 = b
    
    if  b == 0 and par == 1:
        t=t+1
    if b == 0 and par == 0:
        t = t + 1
        d = 1
        par =1
        temp_p = temp1
    if d == 1 and b != 0:
        t = t + 1
        x = temp2 - temp_p
        y= x/t
        break
    temp1 = b

for a,b in val.items():
    
    if b == 0:
        val[a] = int(temp) + int(y)
    temp = val[a]
print(val)
