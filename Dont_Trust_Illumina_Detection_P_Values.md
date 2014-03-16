Dont Trust Illumina Detection P-Values
========================================

- Based on XIST probe expression.
- XIST gene expressed only in Females
- Multiple projects, multiple tissues (Blood, Brain)
- If you build a rule 
-   _if(XIST_detection_p<0.01) then FEMALE_
