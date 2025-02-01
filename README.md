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

### Velocity

### PR Flow Ratio

### PR Time to Merge

### PR Discussions

### PR Size

### PR Lead Time


