Dont Trust Illumina Detection P-Values
========================================

- Based on XIST probe expression.
- XIST gene expressed only in Females
- Observations from multiple projects and multiple tissues (Blood, Brain)
- If you build a rule in R as follows :- 

```    
GENDER <- ifelse( XIST_detection_p <= 0.01, "FEAMLE","MALE")
```

- The majority of your samples will be miss-classified as FEMALE
