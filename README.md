# Knowing When You've Got a Problem

_This was originally developed as a conference talk for Nebraska.Code() on July 25, 2025._

## Description

Intuition and experience are 2 of an engineering manager’s best friends. Managers typically rely on their understanding and observations to identify problems and solutions. After all, most managers were promoted because of being good engineers, and engineers are natural problem solvers, right?

Understanding and observation is great when you can see everything that is happening, but what do you do when there’s too much happening to be aware of? What if your team is remote? What if your team is too big? What if you manage multiple teams with tech leads that have natural biases and blind spots?

HOW DO YOU EVEN KNOW WHEN YOU HAVE A PROBLEM?

When there’s too much to observe naturally, we turn to data. We will discuss different data that can identify what is worth investigating, and how we can identify false positives. Then we will cover 5 mini-case studies showing how that data identified problems that the manager couldn’t easily see.

## Acronyms

* API - Application Programming Interface. Commonly, this is a web service on the Internet that can be called by software applications to retrieve data about a third-party system.
* OKR - Objective and Key Results. This is a common way for organizations to track outcomes to goals.
* PR - Pull Request. This is a standard artifact of team-based software development. It is a method of grouping changes for review so that they can be applied when they are ready.

## Brief Caution

Before we start talking about metrics and how you can use them, we need to discuss how you **should not** use them.

You should not use these metrics to judge individuals. These are TEAM metrics.

Metrics should not be the objectives themselves. They are things that can be measured, but they tell an incomplete story. Metrics can be used as key results in an OKR framework, but the goal is typically something like "increased productivity," "reduced time to market," or "fewer bugs found in production."

Beware of automating anything based on these metrics. Team metrics are about people, and people are inherently complex. Use the metrics to help you identify what to investigate. Use your cognition to empathy to determine what steps to take, if any.

### Feedback

These metrics should not replace holistic feedback mechanisms, such as 360 Reviews, 1 on 1's, or Skip-Levels. Broader feedback can capture information such as the impact of decisions, or the human cost to additional pressure. Maximum pressure for a sustained period of time causes burnout. Long-term, this results in high loss, such as decreased creativity, increased turnover, and increased team conflict.

## Metrics

All of these metrics can be calculated manually. Most metrics can be attained through API calls to your chosen project planning and code repository platforms. If you use systems like GitHub, GitLab, Jira, Azure, AWS, etc., all of these metrics can be captured through an API. However, you may still need to regroup or recalculate metrics depending on your specific use cases. You may choose to exclude Pull Requests related to documentation or release processes. You may choose to aggregate data every quarter, instead of following a 2-week sprint or month. I encourage you to look at the data in multiple periods, as well as using multiple statistical calculations. Mean and median are both useful for identifying outliers and anomalies.

### Ticket Velocity

### PR Flow Ratio

Flow ratio can be examined per day, but for a single team or a few small teams, I would examine per week or per sprint. Daily flow ratio can be helpful for teams that work in Kanban, have very small tickets, or have a lot of members.

### PR Time to Merge

### PR Discussions

### PR Size

### PR Lead Time

## Examples

All examples below will consist of a 5-dev team. They use story points to estimate and operate in 2-week sprints.

### Example 1

| Sprint   | Velocity | Mean PR Total Changes | Flow Ratio | Time To Merge |
| -------- | -------- | --------------------- | ---------- | ------------- |
| Sprint 1 | 62       | 304                   | 1.2        | 2.1           |
| Sprint 2 | 20       | 947                   | 5.1        | 5.8           |
| Sprint 3 | 86       | 1091                  | 0.4        | 6.1           |
| Sprint 4 | 31       | 827                   | ?          | 6.4           |
| Sprint 5 | 78       | 934                   | ?          | 6.9           |
| Sprint 6 | 44       | 975                   | ?          | 7.1           |

#### Example 1 analysis

The velocity is sporadic. Sprint 1 is pretty average. We can look to this as our reference point. Subsequent sprints oscillate between low velocity and high velocity. They follow the same pattern for low- and high-flow ratios. Low velocity sprints have more PRs created than are closed, and high velocity sprints are closing more PRs than are opened. The time to merge also indicates that PRs are taking a long time to review. The increasing TTM is very worrisome, and should be addressed immediately. It is likely that PRs created in the second half of a sprint would not get reviewed and merged in time to be completed during the sprint.

### Example 1 causes

Tickets are likely being carried over between sprints. If it weren't for the large PR size and the long Time to Merge, I would say sprints could be too short. Judging by the PR total changes, the cause is that the PRs are too big and reviews are taking too long. It is perfectly fine to have multiple PRs per ticket. Make the changes smaller, and if necessary make the tickets smaller too. Instruct the senior engineers to review PRs for potential opportunities to break them up into smaller, separate PRs. Encourage the team to set aside time daily to review PRs.

### Example 2

Time to merge. Lead time.

#### Example 2 causes

Devs aren't pushing code until it is done.

### Example 3

Flow ratio. Time to merge.

#### Example 3 causes

Too many open PRs, work is stalled.

### Example 4

Discussions. Time to merge.

#### Example 4 causes

PRs are taking forever because reviewers are nitpicking or disagreeing. This is likely due to communication issues, either from poorly written task assignments or a lack of clear standards. If it is due to conflict, then settle the disagreement, establish clear principles/goals, and lead your team.

### Example 5

Discussions. Time to merge.

#### Example 5 causes

Nobody is reviewing, just approving. Team members might be checked out. They also might not feel empowered to provide feedback to peers or superiors. Does your team have in-groups and out-groups? Is there a high power difference between team members? There's also a chance that sprints are too short or velocity is too aggressive to actually review work. If the velocity is too aggressive, the burndown of the sprint is usually still smooth. If the sprint is too short, there can be a steep cliff at the end of the sprint. Investigate the cause to make sure before declaring the cause.
