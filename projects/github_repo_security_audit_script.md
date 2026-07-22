# GitHub Repository Security Audit Script

## Problem Statement

The organisation maintains a large number of GitHub repositories, including both actively developed and inactive repositories.

Over time, security alerts can accumulate within these repositories. This is particularly concerning for inactive repositories, where there may be no active developers monitoring or addressing outstanding vulnerabilities, exposed secrets, or insecure code.

Previously, obtaining an organisation-wide view of these alerts required manually reviewing individual repositories. This made it difficult to determine the overall distribution of security alerts and identify whether inactive repositories accounted for a significant portion of the outstanding security exposure.

The script was developed to provide a consolidated view of:

* The number of repositories with open security alerts.
* The number of active and inactive repositories affected.
* The total number of open alerts per repository.
* The types and severity of security alerts present.
* The number of alerts associated with inactive repositories.
* Repositories with a potentially significant number of outstanding alerts.
* Recent contributors who may be useful contacts for follow-up.

This information provides a clearer view of where outstanding security alerts are concentrated and helps identify repositories that may require further investigation.

## Key Questions

The script was designed to provide visibility into several areas of the organisation's GitHub security posture.

### Repository-Level Visibility

* Which repositories currently have open security alerts?
* How many alerts does each repository have?
* What types of security alerts are present?
* What is the severity of the alerts affecting each repository?

### Active vs. Inactive Repository Analysis

* How many active repositories have open security alerts?
* How many inactive repositories have open security alerts?
* How many total alerts are associated with inactive repositories?
* Do inactive repositories account for a significant proportion of the organisation's outstanding alerts?

### Security Risk Identification

* Which inactive repositories have the highest number of outstanding alerts?
* Which inactive repositories contain higher-severity alerts?
* Which inactive repositories may require additional investigation due to unresolved alerts and a lack of ongoing maintenance?

### Follow-Up

* Who are the recent contributors associated with affected repositories?
* Who can the security team contact to determine the appropriate next steps?

Recent contributors are treated as potential points of contact rather than formal repository owners. They may help identify the current owner, determine whether the repository is still required, or provide information about its current status.

## Intended Workflow

The overall workflow can be summarised as follows:

### 1. Discover Repositories

* Retrieve repositories within the GitHub organisation.

### 2. Collect Security Alerts

* Retrieve available security alerts for each repository.
* Record information such as alert type, severity, and alert count.

### 3. Determine Repository Activity

* Review recent repository activity and commit history.
* Classify repositories as active or inactive based on the defined activity period.

### 4. Identify Recent Contributors

* Identify recent contributors associated with affected repositories.
* Record this information as a potential reference for follow-up.

### 5. Generate Reports

* Generate a report containing active repositories with outstanding security alerts.
* Generate a separate report containing inactive repositories with outstanding security alerts.

### 6. Review and Prioritise

* Compare security alert exposure between active and inactive repositories.
* Review alert counts and severity.
* Identify inactive repositories that may warrant further investigation.

### 7. Follow Up

Depending on the findings, the security team can contact relevant contributors, owners, or teams to determine whether repositories should be:

* Remediated and their security alerts addressed.
* Archived if they are no longer actively maintained.
* Deleted if they are no longer required and removal is appropriate.
* Escalated to the appropriate team or owner.

## Scope and Limitations

The script is a focused internal automation tool for security alert visibility and prioritisation.

It does not automatically determine whether a repository should be archived or deleted. Instead, it provides the information required for the security team and relevant repository owners to make those decisions.

An inactive classification does not necessarily indicate that a repository is abandoned. It is intended to highlight repositories that may require further investigation.

Similarly, recent contributors identified by the script should not automatically be considered the official repository owners. They are potential contacts who may have relevant knowledge of the repository or be able to direct the security team to the appropriate owner.

Minor inaccuracies in repository activity classification or contributor identification therefore do not fundamentally affect the script's role. Its primary function is to provide a high-level view of security alert exposure and highlight areas requiring human review.

Final decisions regarding remediation, archival, deletion, or escalation remain with the relevant repository owners and security team.

## Project Outcome

The completed script provides a consolidated view of the organisation's GitHub security alert landscape by combining:

* Repository activity status.
* Security alert counts.
* Alert types.
* Alert severity.
* Total alerts per repository.
* Recent repository contributors.

The resulting reports make it easier to identify where security alerts are concentrated and whether inactive repositories account for a significant portion of the organisation's outstanding alerts.

This allows the security team to move beyond simply identifying repositories with security alerts and instead prioritise areas that may require further investigation, particularly repositories that are inactive but contain a high number of or high-severity alerts.

The output can then support follow-up actions such as contacting relevant contributors or owners, investigating repository status, and determining whether outstanding alerts should be remediated or whether the repository should be archived or deleted.
