---
title: Logic bomb
---
_Source : P. 90 of the Sec+ [course notes](/learning/sec+/assets/Course_Notes.pdf)_

A piece of code intentionally inserted into a software system that will set off a malicious function when specified conditions are met.

Unlike [viruses](Viruses.md), logic bombs do not replicate themselves.

They are dormant until triggered by a specific event, such as a date/time, the launch of a program, the deletion of a user account, or a certain command.

## Characteristics of Logic Bombs

- **Condition-based Trigger:** They are activated by conditions written into the code.
- **Malicious Intent:** Once activated, they perform destructive activities, such as deleting files or corrupting data.
- **Stealth:** Logic bombs can be hard to detect as they lie dormant until triggered.
- **[Insider Threat](Insider%20Threat.md):** Often, logic bombs are deployed by disgruntled employees with legitimate access to the system.

## Measures

- Code Reviews and Auditing
- Access Controls
- Change Management
- Regular Backups
- Security Awareness Training
- Antivirus and Antimalware Software
