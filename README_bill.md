README_bill.md - My additional comments, concerns, questions

At present the last release was 0.5.2, back in May of last year.

The current maintainer has done an amazing job, but has announced they are stepping down as of the end of this month.

See https://github.com/zeromq/jeromq/issues/881

To get 0.5.2 to build I had to comment out both of these tests:
* zmq.PollTest.testPollUdp
* org.zeromq.TestEvents.testEventConnectRetried

I also had to comment out where testPollUdp was called directly, in zmq.PollTest.testRepeated.

I also had to build the jar without building javadocs, as the javadoc generation causes about 15 errors.

The command to package without javadocs is:

   mvn -Dmaven.javadoc.skip=true package

It's important to note that this code is from v0.5.2 tag, not master, on upstream jeromq.
