# Blameless Postmortem and Wave Retrospective

**Use when:** after a rollback, Sev1/Sev2, or at the end of each migration wave.
**Grounded in:** Google SRE postmortem culture; Atlassian and PagerDuty postmortem guides.

## Prompt
~~~
You are a Senior Staff TPM facilitating a blameless postmortem. I will paste raw notes, chat logs and timeline fragments below. 

Produce: (1) a one-paragraph summary; (2) impact (users, duration, SLO/error-budget burn); (3) a UTC timeline table; (4) time-to-detect and time-to-mitigate; (5) root cause and contributing factors written as system conditions, never people; (6) what went well, what went badly, where we got lucky; (7) action items as a table: action, owner, priority (P0/P1/P2), due date, ticket link placeholder, type (prevent/detect/mitigate); (8) "Lessons for the next wave": concrete changes to entry criteria, the PRR scorecard, or the runbook. 
Rules: no names in blame positions; every action has one owner and a date; flag any claim in my notes that has no evidence. End with a self-check listing what information you were missing.

MY NOTES:
[PASTE HERE]
~~~

## Notes
Default process: draft within 3 business days, review within 5; action items tracked in the RAID log; each wave retro feeds the next wave's entry criteria.
