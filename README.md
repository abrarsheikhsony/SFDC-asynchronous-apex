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
global with sharing class SampleClass implements Schedulable {
global void execute(SchedulableContext ctx) {
// Your code here
}
}
```

</td>
	</tr>
	<tr>
		<td>Schedulable Methods</td>
		<td></td>
	</tr>
	<tr>
		<td>Batchable Methods</td>
		<td></td>
	</tr>
	<tr>
		<td>Queueable Methods</td>
		<td></td>
	</tr>
</table>
