# results

## previous

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

## both agree implies result is good

agree 74% of the time
right when agree 88% of the time

## predict on all_rights

tracker_all_rights
5cv accuracy: 0.78

              precision    recall  f1-score   support

         0.0       0.73      0.67      0.70       211
         1.0       0.83      0.87      0.85       395

   micro avg       0.80      0.80      0.80       606
   macro avg       0.78      0.77      0.78       606
weighted avg       0.80      0.80      0.80       606

urgence_all_rights
5cv accuracy: 0.73

              precision    recall  f1-score   support

         0.0       0.76      0.81      0.78       347
         1.0       0.72      0.66      0.69       259

   micro avg       0.74      0.74      0.74       606
   macro avg       0.74      0.73      0.73       606
weighted avg       0.74      0.74      0.74       606

## probability tree

```text
                        tracker
                 | 65%                      | 35%                   < predict tracker all right
        auto-qualification               human-qualification
        | 83%            | 17%                                      < predict tracker scikit
good-qualification    bad-qualification
        54%                 11%                 35%  (accuracy)
```

```text
                            tracker
            | 61%                            | 29%                    < predict ri
        demande                         anomaly
      |          |                          |
    good        bad                    human-qualification
     60%         1%                         39%
```

```text
                            tracker
            | 61%                            | 39%                    < predict ri
        demande                         anomaly
      | 99%      | 1%                | 63%         | 37%              < predict ss
    good        bad               demand         anomaly
     60%         1%              | 92%  | 8%    | 44%   | 56%
                                good   bad     good    bad
                                 23%    2%      6%      8%
```

```text
                            tracker
            | 61%                            | 39%                    < predict ri
        demande                         anomaly
      | 99%      | 1%                | 63%         | 37%              < predict ss
    good        bad               demand         anomaly
     60%         1%              | 92%  | 8%       |
                                good   bad        human
                                 23%    2%          14%
```
