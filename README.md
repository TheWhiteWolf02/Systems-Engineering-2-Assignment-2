# Systems Engineering - Assignment #2 #

There are two options of working with the provided repository:
1. using the eclipse project file provided in the top-level directory or,
2. using your favorite editor coupled with the Dockerfile in the toplevel directory
Since option 1 is trivial, the below provided instructions are to help you work with the docker file.

    * Install docker in your machine
    * In the toplevel directory with the Dockefile, run 
        * `docker image build -t se_assignment:2 .`   
        the above command will build the image, download all the data needed for the assignment, run ant build command and then runAllExamples.
        * ``docker run --user 1000:1000 --rm -it -v `realpath ./se2-w-2019-assignment2`:/Source se_assignment:2  bash``   
        will create a docker container which one could use to execute the code.   
        * Navigate to /Source directory and execute `ant init` command.
        * To run the provided examples, execute `ant runAllExamples` or `runMapRedWordFrequencyCount` for WordFrequencyCount example. The available targets can be seen in the `build.xml` file.
        * Modify the source code in the solutions directory corresponding to task 1 or task 2.
        * Execute `ant runMapSolution1` or, `ant runMapSolution2`  and/or `ant runAllSolutions` to test the solution you have developed.   
        The output of the tasks should inform you of success or failure of the given/your solution.

In order to complete the tasks below, please fill the gaps code wise in the src/solutions package. Note: You can use Eclipse or any favorite Java IDE to accomplish those tasks.

## Task #1 Page view frequency ##
### Problem Description ###
You are provided with an apache log showing links that have been accessed by clients.
The task is to create a MapReduce program that counts the total number of times a given url has been accessed.
If the url you get does not start with a valid hostname, you should prepend it with *http://localhost/* (see general notes).

**Expected Output:** URL → frequency

```
#!csv

http://localhost/tikiwiki-2.1/css/admin.css 7
http://localhost/tikiwiki-2.1/tiki-admin.php 308
…
```

### Task #2 Frequency of NYC taxi rides within a 1 hour window ###
###Task Description###
You have been provided csv data that describes taxi services in the city of Newyork.   
For each hourly period, or hour, of the day, determine the number of taxis in operation during the period.  
The hourly period is defined as the period between the start of an hour and the last second of that hour e.g. from 12.00.00 to 12.59.59.   
Some taxi services can span more than one hour period. In that case, consider the operation in each different time period as unique/different operation.  

**Expected Output:** timeslot/window → frequency

```
#!csv

1am 301935
1pm 548485
10am 504387
…
…
```
