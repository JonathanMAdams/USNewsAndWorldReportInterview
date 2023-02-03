# US News and World Report Interview
Reflections Screening Assessment for US News and World Report

In December 2022, I completed this technical assessment as part of an interview with U.S. News and World Report. The questions I was tasked to answer were as follows:

> 1) Subset the dataset to the population at risk, admissions for patients undergoing isolated coronary artery bypass grafts (CABG), identified by procedure codes of 3610, 3611, 3612, 3613, 3614, 3615, 3616, 3617, or 3619.
> 2) Identify comorbidities present in the diagnosis codes using either the Elixhauser (available from AHRQ for SAS, or on SSC for Stata) or Charlson index (either is fine for this exercise).
> 3) Identify whether each admission involved a readmission. A readmission here is defined as a subsequent hospitalization for the same patientId within 30 days of the index admission.
> 4) Specify and run a regression model that estimates the likelihood of readmission among patients admitted for CABG surgery. Control for age, systolic blood pressure, and the number of comorbidities present in the admission record.
> 5) Interpret the model output and explain your model choice over the alternatives. Discuss the assumptions that must hold in order to obtain unbiased estimates from your choice of model.

The assignment and accompanying report had to be completed within 72 hours.

Obviously, hindsight is 20/20, and I would have made different decisions if given the chance. 

First, I answered questions 1-5 sequentially. Testing assumptions (Question 5) should have been completed prior to a final model specification (Question 4). While completing Question 5, I discovered results from a Box-Tidwell test revealed that the relationship between systolic blood pressure and the logit of the outcome variable (rehospitalization) wasn't linear. Had I known this prior to completing Question 4, then I would have used a logistic regression additive model.  

Second, Question 4 wasn't exactly clear. Rereading it now, I probably would have subset the dataframe to include only individuals who had received CABG surgery, and modeled their risk of rehospitalization as a function of age, systolic blood pressure, and the number of comorbidities in the admission record. Instead, I included CABG as a predictor, because I interpreted the question as asking me to compare the effect of CABG surgery vs. no CABG surgery on rehospitalization. In addition, removing those who didn't receive CABG surgery would have truncated the data, which can diminish effect sizes. 

I also believe that deadlines are parts of assignments. In most business settings, data aren't going to meet 

All in all, this was a whirlwind of an exercise, and a great chance to flex my R skills! I ultimately wasn't moved on to the final round--I'm not sure if that's because of my misinterpretation of Question 4 or their strong preference for someone fluent in Stata. Nonetheless, it was an extremely valuable learning opportunity, and I'm glad I get to add this project to my portfolio!
