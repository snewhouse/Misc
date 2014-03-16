Dont Trust Illumina Detection P-Values at Th=0.01
==================================================

- Based on XIST probe expression.
- XIST gene expressed only in Females
- Observations from multiple projects and multiple tissues (Blood, Brain)
- If you build a rule in R as follows :- 

```    
GENDER <- ifelse( XIST_detection_p <= 0.01, "FEAMLE","MALE")
```

- The majority of your samples will be miss-classified as FEMALE
- This is all the evidence you need to see that using a threshold of 0.05 or 0.01 is just plain wrong
- You will be analysing data and building prediction models based on noise

******

The Smart thing to do!
======================================================

## Option A

- Set detection pvalue threshold to 0

## Option B

- Use negative bead data
- Background correct your data using ***MBCB (Model-based Background Correction for Beadarray)***
- http://www.bioconductor.org/packages/release/bioc/html/MBCB.html
- Make a rule where:


if `PROBE.i` in `SAMPLE.j` is `>=` the `MEAN` of the `NEGAVTIVE_BEADS.SAMPLE.j` then `PROBE.i` is `DETECTED` in `SAMPLE.j`


