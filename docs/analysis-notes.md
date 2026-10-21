# Analysis notes

## Workflow shown in the screenshots

1. Import a CSV into R and remove the `rnd` and `count` fields for analysis.
2. Group transaction totals by `paymentType`, `city`, and `age` with dplyr.
3. Display payment totals as a pie chart, age totals as a scatter plot, city totals as a horizontal bar chart, and transaction totals as a box plot.
4. Create a numeric matrix from `total` and `age`, choose two to four centers, and run K-means.
5. Split comma-separated item baskets and invoke Apriori with user-entered minimum support and confidence.

## Interpretation

The screenshots show transaction-level clustering, not aggregation by a stable customer identifier. Names repeat and are not unique customer IDs. The displayed between-cluster sum-of-squares ratio is about 75.5% for a two-cluster run. This is a clustering statistic, not predictive accuracy.

The code shown uses unscaled total and age features. Spending may dominate Euclidean distances because the feature scales differ. No fixed random seed is visible, so reruns may produce different assignments.

The city bar chart code uses separately computed city labels after sorting totals. Labels should be derived from the same sorted table before interpreting city rankings. No city-ranking claim is made here.

The Apriori screenshot reads an Excel input, but only a CSV dataset survives in these materials. Its exact execution and output cannot be reproduced from the screenshots alone.

## Data dictionary

| Field | Description |
| --- | --- |
| items | Comma-separated grocery items |
| count | Supplied basket item-count field |
| total | Transaction spending value, currency unspecified |
| rnd | Auxiliary field, removed in the shown workflow |
| customer | Customer name, not a unique identifier |
| age | Recorded customer age |
| city | Recorded city |
| paymentType | Cash or Credit |

## Public materials

Only aggregate payment totals and screenshots without customer names are published. Individual transaction records and name-bearing screenshots are excluded. Dataset-level observations above describe the supplied materials, not a public downloadable customer dataset.
