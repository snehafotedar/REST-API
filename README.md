REST API - Weather Details

Database information : daily.csv file was save in sqlite database(weather.db) and data is retrived by querying the database.

Functions implemented are as below :

1. To get all the historical data available:
End Point : /historical
Web URL : http://ec2-52-41-156-167.us-west-2.compute.amazonaws.com:5000/historical

2. To get all the data for a particular date:
End Point : /historical/<YYYYMMDD>
Web URL : http://ec2-52-41-156-167.us-west-2.compute.amazonaws.com:5000/historical/<YYYYMMDD>
ex: http://ec2-52-41-156-167.us-west-2.compute.amazonaws.com:5000/historical/20160302

3. To insert or update data for a particular date:
End Point : /historical/<YYYYMMDD,Tmax,Tmin>
Web URL : http://ec2-52-41-156-167.us-west-2.compute.amazonaws.com:5000/historical/<YYYYMMDD,Tmax,Tmin>
ex: http://ec2-52-41-156-167.us-west-2.compute.amazonaws.com:5000/historical/20160302,40,27

4. To delete data for a particular date:
End Point : /historical/delete/<YYYYMMDD>
Web URL : http://ec2-52-41-156-167.us-west-2.compute.amazonaws.com:5000/historical/delete/<YYYYMMDD>
ex: http://ec2-52-41-156-167.us-west-2.compute.amazonaws.com:5000/historical/delete/20160302

5. To predict data for next 7 days:
End Point : /forecast/<YYYYMMDD>
Web URL : http://ec2-52-41-156-167.us-west-2.compute.amazonaws.com:5000/forecast/<YYYYMMDD>
ex: http://ec2-52-41-156-167.us-west-2.compute.amazonaws.com:5000/forecast/20170102

Validations done are as below:
1. For an incorrect endpoint, the program will throw HTTP 404 - Not Found error.
2. If user tries to retrieve data for date which is not available, program will throw 404 - Not found error.
3. If user tries to insert data for date whose data is not available, program will insert data for that date and if data is already present, it will update the data with 201 HTTP code.
4. If user tries to insert some invalid values(alphabets), it will throw HTTP 400 - Bad Request error.
5. If user tries to delete data for date not present, it will throw HTTP 400 - Bad Request error.
