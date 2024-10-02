(Source: Udacity Enrollment Project, Final Project of the Course)

# Udacity Free Trial Experiment

## 1. Experiment Overview

At the time of this experiment, Udacity's course homepages offered two main options:

- **Start Free Trial**: Enrolling students in a 14-day free trial after entering payment details, which automatically leads to billing unless canceled.
- **Access Course Materials**: Granting access to course content without benefits such as coaching support, verified certification, or feedback.

### Experiment Design
In this experiment, Udacity tested a modification: when users clicked "Start Free Trial," they were asked how many hours they planned to dedicate to studying each week.

- **If students committed 5 or more hours/week**: They would proceed through the checkout as usual.
- **If students committed fewer than 5 hours/week**: They were shown a message suggesting a higher time commitment for success and encouraged to access the free course materials. They were still given the option to proceed with the trial or access the free content.

The rationale behind this change was to:
- Improve the student experience.
- Optimize coaching resources by focusing on students more likely to complete the course, without significantly reducing post-trial enrollments.

---

## 2. Experiment Design and Metrics

### Randomization
Users were divided into two groups based on unique cookies:
- **Experiment Group**: Asked for time commitment.
- **Control Group**: Proceeded as usual.

Once a user enrolled, they were tracked by a unique user ID, and this ID could not be reused for multiple enrollments.

### Metrics

#### 1. **Invariant Metrics** (For validation and sanity checks):
- **Number of Cookies**: The number of unique cookies visiting the course overview page.
- **Number of Clicks**: The number of users clicking "Start Free Trial."
- **Click-through Probability**: The ratio of cookies clicking "Start Free Trial" to cookies viewing the overview page.

These metrics are expected to be evenly distributed between groups and validate the experimental setup.

#### 2. **Evaluation Metrics**:
- **Gross Conversion**: The proportion of user IDs that complete checkout and enroll in the free trial.
- **Retention**: The proportion of students that remain enrolled after the 14-day trial period and make at least one payment.
- **Net Conversion**: The proportion of user IDs that complete the 14-day trial and make a payment.

For the experiment to succeed:
- The null hypothesis (no difference between groups) must be rejected for **all evaluation metrics**.
- The observed differences must exceed **practical significance thresholds**.

### Unused Metrics:
- **Number of User IDs**: Tracking only begins after enrollment, which makes this metric unsuitable for pre-enrollment analysis.

---

## 3. Measuring Standard Deviation

| **Evaluation Metric** | **Standard Deviation** |
|-----------------------|------------------------|
| Gross Conversion       | 0.0202                 |
| Retention              | 0.0549                 |
| Net Conversion         | 0.0156                 |

The analytical standard deviation estimates for Gross Conversion and Net Conversion are close to their empirical values, but Retention's deviation must be determined empirically.

---

## 4. Sizing for Experiment

### Sample Size vs. Statistical Power
The following sample sizes and pageviews were calculated using an alpha level of 0.05 and beta of 0.2 (80% power).

| **Metric**         | **Baseline Conversion** | **Minimum Detectable Effect** | **Sample Size (per group)** | **Pageviews Required** |
|--------------------|-------------------------|-------------------------------|-----------------------------|------------------------|
| Gross Conversion    | 20.625%                 | 1%                            | 25,835                       | 645,875                |
| Retention           | 53%                     | 1%                            | 39,155                       | 4,741,212              |
| Net Conversion      | 10.9313%                | 0.75%                         | 27,413                       | 685,325                |

### Total Pageviews Required: 4,741,212

### Duration vs. Exposure
If 100% of traffic (40,000 pageviews/day) is diverted:
- The experiment would take **119 days**.
- Omitting Retention would reduce the required pageviews to **685,325**, shortening the experiment to **18 days** (or **35 days** at 50% diversion).

---

## 5. Experiment Analysis

### Sanity Checks (Invariant Metrics)

| **Metric**                              | **Expected Value** | **Observed Value** | **CI Lower Bound** | **CI Upper Bound** | **Result** |
|-----------------------------------------|--------------------|--------------------|--------------------|--------------------|------------|
| Number of Cookies                       | 0.5000             | 0.5006             | 0.4988             | 0.5012             | Pass       |
| Number of Clicks on "Start Free Trial"  | 0.5000             | 0.5005             | 0.4959             | 0.5042             | Pass       |
| Click-through Probability               | 0.0821             | 0.0822             | 0.0812             | 0.0830             | Pass       |

---

### Result Analysis (Evaluation Metrics)

| **Metric**         | **dmin** | **Observed Difference** | **CI Lower Bound** | **CI Upper Bound** | **Result**                                     |
|--------------------|----------|-------------------------|--------------------|--------------------|------------------------------------------------|
| Gross Conversion    | 0.01     | -0.0205                 | -0.0291            | -0.0120            | Statistically and Practically Significant       |
| Net Conversion      | 0.0075   | -0.0048                 | -0.0116            | 0.0019             | Neither Statistically nor Practically Significant |

### Sign Tests

| **Metric**         | **p-value for Sign Test** | **Statistically Significant at alpha = 0.05?** |
|--------------------|---------------------------|-----------------------------------------------|
| Gross Conversion    | 0.0026                    | Yes                                           |
| Net Conversion      | 0.6776                    | No                                            |

---

## 6. Summary

The experiment aimed to determine if filtering students based on their study time commitment would improve the student experience and better allocate coaching resources. The analysis showed the following results:

- **Gross Conversion**: A statistically and practically significant decrease was observed. However, this led to a drop in enrollments without an increase in students continuing through the free trial.
- **Net Conversion**: Neither statistically nor practically significant, indicating that fewer students stayed long enough to make a payment.

### Conclusion
While the decrease in Gross Conversion was statistically significant, the lack of improvement in Net Conversion means fewer students are enrolling and staying past the free trial period. Therefore, **I recommend not launching** this experiment and suggest focusing on alternative approaches.
