# previous

Through the project [oraw2_issue-weight](https://git.rnd.alterway.fr/overboard/openreq/oraw2_issue-weight) we built two classifier capable of classifing french issue reports as "Demand" or "Anomaly".

## Classication report

- scikit-sentistrength 15k

| tracker      | precision | recall | support |
|--------------|-----------|--------|---------|
| Demand       | 0.97      | 0.90   | 2760    |
| Anomaly      | 0.42      | 0.72   | 274     |
| Weighted avg | 0.92      | 0.88   | 3034    |

| urgence      | precision | recall | support |
|--------------|-----------|--------|---------|
| Basse        | 0.56      | 0.41   | 524     |
| Normale      | 0.85      | 0.84   | 2311    |
| Haute        | 0.33      | 0.62   | 199     |
| Weighted avg | 0.77      | 0.75   | 3034    |

- ri-analytics 15k

| tracker      | precision | recall | support |
|--------------|-----------|--------|---------|
| Demand       | 0.99      | 0.66   | 2760    |
| Anomaly      | 0.21      | 0.92   | 274     |
| Weighted avg | 0.92      | 0.68   | 3034    |

| urgence      | precision | recall | support |
|--------------|-----------|--------|---------|
| Basse        | 0.37      | 0.59   | 524     |
| Normale      | 0.95      | 0.94   | 2311    |
| Haute        | 0.16      | 0.94   | 199     |
| Weighted avg | 0.80      | 0.50   | 3034    |

