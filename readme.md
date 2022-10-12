At Workday we run millions of jobs and reports for our customers in our datacenters and we need to do this in a performant and fair manner. The system responsible for this task contains 3 crucial interfaces:
* Job: Defines a piece of work to be executed on behalf of a customer. In the real codebase there would be many different implementations for the different types of jobs our customers need to execute.
* JobQueue: Provides an abstraction for fetching the jobs as they are submitted by customers. In the real codebase there would be an implementation that connects to a message broker system.
* JobRunner: Provides the logic to schedule the execution of jobs that are fetched from a JobQueue. This is the heart of the system as it decides when to consume the job queue and what jobs to execute.
 
 
 In this test you are presented with a simplified version of these 3 interfaces but not their real implementations. You will be provided with a naive implementation of them for testing purposes only. You do not need to implement the Job or JobQueue interfaces except for your own testing needs if any, also you do not need to implement the code that starts the system and wires together the different interface implementations.
 

Your task will be to implement a JobRunner that meets the following requirements:
* The job runner shall work with any implementation of Job and JobQueue interfaces.
* The job runner shall be resilient to failures. It shall always attempt to execute jobs once and only once if they have been consumed from the queue and it will never abort the execution of a job.
* The job runner shall perform efficiently in a multi-core processor environment equivalent to your work laptop.
* The job runner shall schedule the execution of jobs in a fair manner to our customers so that no single customer can have an oversized impact on the availability of the resources to other customer. The definition of fairness is up to you, so be sure to document it. An example of an unfair scenario would be to allow one customer to hog all of the resources to the point where other customers do not get to execute jobs.
* The Job runner shall be implemented to what you consider a production ready standard and be ready for a code review.
 

The presented project structure contains the following files:
* Interface definitions src/main/java/com/workday/java/ please do not change these.
* An empty implementation of JobRunner in src/main/java/com/workday/java/ you can change this file as you please and add other classes as you need.
* A naive implementation of the interfaces in src/test/java/com/workday/java please read these and understand why it does not meet the requirements, you are free to modify this code.
* An integration test of the naive implementation in src/test/java/com/workday/java you can copy or adapt it to your JobRunner.
* A maven project file in /pom.xml please add any needed dependencies here and be sure to justify them in your documentation.
* A readme.txt file, please be sure to spend at least 15 minutes documenting your submission here in a coherent and brief manner. The file contains a list of topics that we are interested in seeing documented.
