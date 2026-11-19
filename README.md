# econ3916-lab17-classification

# Classification: When 90% Accurate Is Worthless

## Objective

I wanted to see how accuracy can be misleading when defaults are rare and how the cost of each error can help me choose a better threshold.

## Methodology

- I worked with 6,000 simulated loan applications with a 9.6% default rate.
- I fitted a logistic regression and compared its accuracy at the 0.5 threshold with a rule that approves everyone.
- I interpreted the coefficients as log-odds and odds ratios. I used the 1.63 odds ratio for one more prior default to show how the same odds ratio can lead to different changes in probability depending on the starting probability.
- I compared precision and recall across six thresholds and chose the threshold that minimized the expected cost of approving a loan that defaults or declining a loan that would have been repaid.
- I wrote `precision_recall_at()` to calculate a classifier's precision and recall at any threshold.

## Key Findings

- My model was 90.4% accurate at the 0.5 threshold and predicted zero defaults. The rule that approves everyone also had 90.4% accuracy.
- The cost-minimizing threshold I found was 0.121, close to the closed-form threshold of 0.118. On the test set, the expected cost was $944 per applicant at 0.121, compared with $1,147 at 0.5.
- At the closed-form threshold of 0.118, I got a precision of 0.181 and a recall of 0.477.
