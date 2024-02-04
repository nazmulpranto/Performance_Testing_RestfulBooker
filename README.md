# Performance Testing (Restful Booker)

Hello and welcome! This GitHub repository contains the performance testing documentation for restful-booker.herokuapp.com, for a collection of API with various HTTP methods. Here, performance testing is done using Jmeter to determine the maximum load capacity of this collection of API to be called without any errors when a huge number of concurrent threads(users) are made.

All the test files (jmx, jtl & html files) are included in this repository and the following is a report of all the test procedures and reports.


## Summary

- While executing 300 concurrent threads(users), a total of 900 requests are made with error rate 0.00%.

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/s300.png)

- While executing 400 concurrent threads(users), a total of 1200 requests are made with error rate 33.33%.

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/s400.png)

- While executing 500 concurrent threads(users), a total of 1500 requests are made with error rate 33.33%.

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/s500.png)


## Collection of API

A set of API for restful-booker.herokuapp.com covering various HTTP methods i.e. POST, GET, DELETE, and PUT are used for test data. Data is set, called, then updated using token and then deleted using token all within this set of API for this test coverage.

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/1.png)

## Load Testing

For finding the maximum load capacity of restful-booker.herokuapp.com when reqesting a collection of API, Jmeter is used where Thread Groups of huge number of threads(users) are made. For this test, Thread Groups of 300, 400 and 500 threads are found to be suitable data. For all Thread Groups, Ramp-up period is set to 10s with loop count of 1.

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/2.png)

Using the command-line interface, the following command-line is used for making JTL files where we can see the load testing results in command-line interface.

```bash
  jmeter -n -t nazmul_300.jmx -l report\nazmul_300.jtl
```

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/t300.png)

Afterwards using the above JTL files, using the command-line interface the following command-line is used for making HTML reports.

```bash
  jmeter -g report\nazmul_300.jtl -o report\nazmul_300.html
```

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/t300_html.png)

## First Thread Group

Number of Threads: 300, Ramp-up Period: 10s

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/t300.png)

After running the load testing in command-line interface we can see the APIs are requested without any errors. Below is the HTML report view and errors.
![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/rs300.png)
![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/e300.png)

## Second Thread Group

Number of Threads: 400, Ramp-up Period: 10s

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/cmd400.png)

We can see here that, this collection of API run with very minor errors for 1200 threads and still can be accepted to have passed the load test.
![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/s400.png)
![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/e400.png)

## Third Thread Group

Number of Threads: 500, Ramp-up Period: 10s

![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/cmd500.png)

After running the load testing in command-line interface we can see the APIs are requested with a lot of errors. Below is the HTML report view and errors.
![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/s400.png)
![App Screenshot](https://github.com/nazmulpranto/Performance_Testing_RestfulBooker/blob/main/pictures/e500.png)

We can see here that, this collection of API run with a lot of errors (more than 35%) for 500 threads and therefore can be determined to have failed the load test.

## Conclusion

Therefore from this in-depth performance testing of restful-booker.herokuapp.com for a collection of API using three Thread Groups, it is determined that the maximum load capacity of running the aforementioned collection of APIs without any errors is 500 concurrent threads and with errors. Using threads any more than this causes significant amount of errors.
