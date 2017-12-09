# Salesforce Asynchronous Apex

Here you will find different flavors of Salesforce Asynchronous Apex approaches.

## Salesforce Trailmixes
(1) <a href="https://trailhead.salesforce.com/en/users/00550000006G25XAAS/trailmixes/integration-with-salesforce" target="_blank" alt="Integration with Salesforce">Integration with Salesforce</a><br/>

## Salesforce Asynchronous Apex Approaches
Salesforce Asynchronous Apex approaches come in a number of different flavors. Here’s a high level overview.

<table>
	<tr>
		<th colspan="7">Salesforce Asynchronous Apex Approaches (High Level Overview)</th>
	</tr>
	<tr>
		<th>Type</th>
		<th>Example</th>
	</tr>
	<tr>
		<td>Future Methods</td>
<td>

```
public with sharing class SampleFutureMethods {

    // Call asynchronous processing from Triggers
    @future(callout=false)
    public static void updateAccounts(Set<Id> setAccountIds) {
        // Your code here
    }

    // Call synchronous processing from Controllers
    public static String updateAccount(Id accountId) {
        // Your code here
        Set<Id> setAccountIds = new Set<Id>();
        setAccountIds.add(accountId);
        updateAccounts(setAccountIds);
    }

    // Call asynchronous processing from Triggers
    @future(callout=true)
    public static void sendSMS(Set<Id> setAccountIds) {
        // Your code here
    }

    // Call synchronous processing from Controllers
    public static String sendSMS(Id accountId) {
        // Your code here
        Set<Id> setAccountIds = new Set<Id>();
        setAccountIds.add(accountId);
        sendSMS(setAccountIds);
    }

}
```

</td>
	</tr>
	<tr>
		<td>Schedulable Methods</td>
<td>

```
global with sharing class SampleBatchSchedule implements Schedulable {
	global void execute(SchedulableContext ctx) {
		// Your code here
	}
}
```

</td>
	</tr>
	<tr>
		<td>Batchable Methods</td>
<td>

```
global with sharing class SampleBatch implements Database.Batchable<sObject> {

    global (Database.QueryLocator | Iterable<sObject>) start(Database.BatchableContext bc) {
        // Your code here
    }

    global void execute(Database.BatchableContext bc, List<sObject> records){
        // Your code here
    }    

    global void finish(Database.BatchableContext bc){
        // Your code here
    }    

}
```

</td>
	</tr>
	<tr>
		<td>Queueable Methods</td>
<td>

```
global with sharing class SampleQueueable implements Queueable { 
    global void execute(QueueableContext context) {
        // Your code here
    }
}
```

</td>
	</tr>
</table>
