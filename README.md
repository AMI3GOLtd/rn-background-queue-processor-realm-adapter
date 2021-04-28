# React Native Queue Processor Realm Adapter

This package is designed for [rn-background-queue-processor](https://github.com/technogise/rn-background-queue-processor) to store Jobs in persistent Realm storage.

## Compatibility

Our current version works well for `Realm: v10.4.0`

## Usage

This packages is forked from @technogise. Here is a [working demo app](https://github.com/technogise/rn-background-queue-processor/tree/master/examples/rnqpSample)

- Two schema are there to store all jobs and Failed jobs 
- Job Schema contains all the Jobs ready for execution 
- Failed Schema have all the failed jobs after queue execution
- Jobs are sent for execution according to its priority

Functions that are used in [rn-background-queue-processor](https://github.com/technogise/rn-background-queue-processor) are -
- `addItem(job)`: Method to add a job in JobSchema
- `addFailedItem(job)`: Method to add a job in FailedJobSchema
- `remove(jobId)`: Method to remove job
- `getLength()`: Method to get length 
- `getTopItem`: Method to get high priority Job
- `getAllItems`: To get all jobs
- `getJobInstance`: Method to get job instance
- `addFailedItems`: Method to add failed jobs in JobSchema


#### Installation steps

`npm i rn-background-queue-processor-realm-adapter`

#### Example import

```
import { RealmAdapter } from 'rn-background-queue-processor-realm-adapter';

constructor() {
    const dbAdapter = new RealmAdapter(ExampleJob.prototype);
    this.queue = new Queue(dbAdapter);
  }
```
