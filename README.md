# intro-epidemiology
Lecture-specific R programs for generating data to teach epidemiological study designs &amp; topics  
  
For lectures where programs were created, the corresponding lecture number and a brief description of the program are provided. Lecture content (not provided here) is adapted from *Epidemiology, 4th Edition* by Leon Gordis (2008).   
  
**Lecture \#5**: Validity &amp; Reliability of Diagnostic Tests  
  *Description*: Students were tasked with designing their own diagnostic test(s) to screen for a given disease. Students were given 100 points to allocate between sensitivity and specificity of their diagnostic test. Prevalence of the disease was unknown to the students and students were allowed to modify sensitivity and specificity through trial-and-error. Students were also allowed to design approaches utilizing simultaneous and sequential testing. Once a test had been designed, the program was used to generate data, which the students would then use to calculate the positive predictive value (PPV), negtive predictive value (NPV), and other values of interest.  
    
  Program functions: `diagnostic.test.design(sensitivity, specificity, prevalence, samp.size, test.type, seed, I)`  
    `sensitivity`: Desired test sensitivity. If `test.type = c(simultaneous, sequential)`, two values must be provided    
    `specificity`: Desired test specificity. If `test.type = c(simultaneous, sequential)`, two values must be provided  
    `prevalence`: Desired prevalence. Prevalence = (value + 5) / 100; "+5" added so students cannot guess prevalence from input  
    `samp.size`: Desired sample size  
    `test.type`: Type of diagnostic test being used. Options are `c(simultaneous, sequential, none)`. Default is `none`.  
    `seed`: Set seed for reproducability. In team-based learning, use team number for simplicity.  
    `I`: Instructor output. Includes row/column totals, PPV/NPV, and brief explanations of how answers were reached.  
  
    
**Lecture \#6**: Ecological Studies
  *Description*: Students were asked to design their own ecological study. Students were given a field within medicine from which to choose an exposure and an outcome. Students were asked to specify a target population, sample size, and a valid/plausible source for their population-level data. Once the study had been designed, the program was used to generate data. The resulting output would be the Pearson correlation coefficient and an accompanying graphic, both of which students were expected to interpret.    
    
    Program funtions: `ecological.study.design(exposure, outcome, samp.size, exp.scale, group.type, k.groups, corr, seed)`  
      `exposure`: Exposure name. Entered as string.  
      `outcome`: Outcome name. Entered as string.  
      `samp.size`: Desired sample size.  
      `exp.scale`: Mean value for scale of exposure &amp; outcome, respectively; two values must be provided. Accepted values include 1 - 4: 1 = 1, 2 = 10, 3 = 100, 4 = 1000; values used as mean in `rnorm` with appropriate standard deviation.  
      `group.type`: Grouping variable for data (if applicable). Options are `c('countries', 'time', 'none')`. Default is `none`.  
      `k.groups`: Number of groups desired (if applicable). Error if specified while `group.type == none`.  
      `corr`: Pearson correlation coefficient for data. Options are `c('positive', 'negative', 'none')`.  
      `seed`: Set seed for reproducability. In team-based learning, use team number for simplicity. Default is `1`.    
