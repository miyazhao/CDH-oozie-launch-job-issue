# CDH-oozie-launch-job-issue


We have a CDH 5.2.0 installed and try to use a web application Studio to upload files into CDH component hive to create a hive table, then it automatically uses oozie to launch Mapreduce workflow jobs.

while in the process of processing data using oozie, error occurs:

2015-01-26 10:33:26,706 INFO org.apache.oozie.command.wf.ActionStartXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@:start:] Start action [0000000-150126103201917-oozie-oozi-W@:start:] with user-retry state : userRetryCount [0], userRetryMax [0], userRetryInterval [10]
2015-01-26 10:33:26,707 INFO org.apache.oozie.command.wf.ActionStartXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@:start:] [***0000000-150126103201917-oozie-oozi-W@:start:***]Action status=DONE
2015-01-26 10:33:26,707 INFO org.apache.oozie.command.wf.ActionStartXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@:start:] [***0000000-150126103201917-oozie-oozi-W@:start:***]Action updated in DB!
2015-01-26 10:33:27,075 INFO org.apache.oozie.command.wf.ActionStartXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask] Start action [0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask] with user-retry state : userRetryCount [0], userRetryMax [0], userRetryInterval [10]
2015-01-26 10:33:28,543 INFO org.apache.oozie.action.hadoop.JavaActionExecutor: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask] checking action, hadoop job ID [job_1422113225210_0003] status [RUNNING]
2015-01-26 10:33:28,545 INFO org.apache.oozie.command.wf.ActionStartXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask] [***0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask***]Action status=RUNNING
2015-01-26 10:33:28,545 INFO org.apache.oozie.command.wf.ActionStartXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask] [***0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask***]Action updated in DB!
2015-01-26 10:33:54,818 INFO org.apache.oozie.servlet.CallbackServlet: SERVER[slc08aei.us.oracle.com] USER[-] GROUP[-] TOKEN[-] APP[-] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask] callback for action [0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask]
2015-01-26 10:33:55,111 INFO org.apache.oozie.action.hadoop.JavaActionExecutor: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask] action completed, external ID [job_1422113225210_0003]
-------------------------------------- error lines --------------------------------
2015-01-26 10:33:55,178 WARN org.apache.oozie.action.hadoop.JavaActionExecutor: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask] Launcher ERROR, reason: Main class [org.apache.oozie.action.hadoop.JavaMain], exit code [1]
-------------------------------------- error lines --------------------------------
2015-01-26 10:33:55,268 INFO org.apache.oozie.command.wf.ActionEndXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@DataProcessingJavaTask] ERROR is considered as FAILED for SLA

2015-01-26 10:33:55,344 INFO org.apache.oozie.command.wf.ActionStartXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@kill5] Start action [0000000-150126103201917-oozie-oozi-W@kill5] with user-retry state : userRetryCount [0], userRetryMax [0], userRetryInterval [10]
2015-01-26 10:33:55,345 INFO org.apache.oozie.command.wf.ActionStartXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@kill5] [***0000000-150126103201917-oozie-oozi-W@kill5***]Action status=DONE
2015-01-26 10:33:55,345 INFO org.apache.oozie.command.wf.ActionStartXCommand: SERVER[slc08aei.us.oracle.com] USER[cdctest] GROUP[-] TOKEN[] APP[edp-a50f4e6c-0895-4b2e-8ca0-ecb02e238caf] JOB[0000000-150126103201917-oozie-oozi-W] ACTION[0000000-150126103201917-oozie-oozi-W@kill5] [***0000000-150126103201917-oozie-oozi-W@kill5***]Action updated in DB!



Wish I could get some suggestion here~ 

Thank you


