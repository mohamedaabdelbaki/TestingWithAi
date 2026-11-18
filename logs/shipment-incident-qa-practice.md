# QA Practice: Investigating a Shipment Failure

I simulated a production bug where a user couldn’t complete an order. I used ChatGPT to find what went wrong in the service logs and summarize it in an incident report and dashboard.

## My prompt

> A user (`U-4471`) reported that they couldn’t create a shipment around 3 p.m. on August 14, 2026. Review the attached service logs and use request IDs to trace the attempts across services. Create an incident report that explains what failed, which service triggered the failure, and which service should own the fix. Include a timeline with the time zone, relevant HTTP status codes and logged response bodies, and any payment impact. Flag anything the logs can’t confirm and suggest what to check next.
