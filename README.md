# code snippets for EMC

# Specification:

As part of your interview process, would it be possible for you to complete a short code screening for us?

Please provide a sample project for review:
<br>1. The project should provide a web service.
  a. The web service accepts a number, n, as input and returns the first n Fibonacci numbers, starting from 0. I.e. given n = 5, appropriate output would represent the sequence "[0, 1, 1, 2, 3]".
  b. Given a negative number, it will respond with an appropriate error.
<br>2. Include whatever instructions are necessary to build and deploy/run the project, where "deploy/run" means the web service is accepting requests and responding to them as appropriate.
<br>3. Include some tests

While this project is admittedly trivial, approach it as representing a more complex problem that you'll have to put into production and maintain for 5 years.
Providing a link to a github/bitbucket repo with the project would probably be the easiest way to submit.


# Features:

  - cache of previous calculated ranges, does not repeat the math
  - cache of previously requested numbers (num=$x), does not have to calculate anything


# test by starting the http server, then manually requesting data, or using the test script

# in one terminal, start the web service
$ perl ./httpd

# in a seperate terminal, manually test, maming sure to set num=value

$ nc localhost 54321
GET /getfibb?num=5
<p>[0, 1, 1, 2, 3]

# or use the test script

$ perl ./testfibb
using: http://localhost:54321/getfibb?num=15
<p>Test Succeeded!


# test script will take arguments

$ ./testfibb -h
usage: ./testfibb [-h] [-o] [-u host] [-p port] [-n number]

    -h:  help (this output)
    -o:  output fibbinacci sequence
    -u host:  set connect host
    -p port:  set connect port
    -n:  number of items to retrive

    defaults are localhost, 54321, and num=15



# known issues:

  - server does not handle multiple input variables
  - server does not output proper headers to make real browsers happy
  - probable misspelling of Fibanacci
 
