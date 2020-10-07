# scaling-workbook
Notes on how to scale.

## Define service level objectives
Service level objectives (SLOs) specify a target level for the reliability of your service. 

__100% reliability is the wrong target because:__
- There is a nonzero probability that one or more components of the system will fail simultaneously, resulting in less than 100% availability. 
- If you managed to guaranteee 100% uptime in some utopia without real physical machines, you could never update or improve your service. 

## Measure service level indicators
An SLI should be the number of good events divided by the total number of events. 
For example:
- Number of successful HTTP requests / total HTTP requests (success rate)
- Ratio of home page requests that loaded in < 100 ms / total home page requests

The SLI ranges from 0% to 100%, where 0% means nothing works, and 100% means nothing is broken.  If you have a 99.9% success ratio SLO, then a service that receives 3 million requests over a four-week period had a budget of 3,000 (0.1%) errors over that period.

<table>
<tbody>
<tr>
  <td><strong>Type of SLI</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr>
<td>Availability</td>
<td>The proportion of requests that resulted in a successful response.</td>
</tr>
<tr>
<td>Latency</td>
<td>The proportion of requests that were faster than some threshold.</td>
</tr>
<tr>
<td>Freshness</td>
<td>The proportion of the data that was updated more recently than some time threshold.</td>
</tr>
</tbody>
</table>

### Credit
These are my personal notes taken from [the SRE series](https://landing.google.com/sre/books/) and other blogs and books I will cite once I feel like it.
