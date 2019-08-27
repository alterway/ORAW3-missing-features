# Resultat des experiences avec differents treshold

    threshold .75  precision recall    f1-score  support

    Anomaly        0.58      0.50      0.54       274
    Demand         0.95      0.96      0.96      2760

    accuracy                           0.92      3034
    macro avg      0.77      0.73      0.75      3034
    weighted avg   0.92      0.92      0.92      3034


    threshold .8   precision recall    f1-score  support

    Anomaly        0.64      0.42      0.51       274
    Demand         0.94      0.98      0.96      2760

    accuracy                           0.93      3034
    macro avg      0.79      0.70      0.73      3034
    weighted avg   0.92      0.93      0.92      3034

    pred\true Anomaly   Demand  Human
    Anomaly   114       64      96
    Demand    63        2431    266
    Human     0         0       0

- Human prediction 12%  (anom 27%; dem 73%)
- Demand prediction 82% (good 97%; bad 3%)
- Anomaly prediction 6% (good 64%; bad 36%)

.

    treshold .85   precision recall    f1-score  support

    Anomaly        0.66      0.29      0.41       274
    Demand         0.93      0.99      0.96      2760

    accuracy                           0.92      3034
    macro avg      0.80      0.64      0.68      3034
    weighted avg   0.91      0.92      0.91      3034
