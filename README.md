# intro-epidemiology
Lecture-specific R programs for generating data to teach epidemiological study designs &amp; topics  
  
For lectures where programs were created, the corresponding lecture number and a brief description of the program are provided. Lecture content (not provided here) is adapted from *Epidemiology, 4th Edition* by Leon Gordis (2008).   
  
**Lecture \#5**: Validity &amp; Reliability of Diagnostic Tests  
  Description: Students were tasked with designing their own diagnostic test(s) to screen for a given disease. Students were given 100 points to allocate between sensitivity and specificity of their diagnostic test. Prevalence of the disease was unknown to the students and students were allowed to modify sensitivity and specificity through trial-and-error. Students were also allowed to design approaches utilizing simultaneous and sequential testing. Once a test had been designed, the program was used to generate data, which the students would then use to calculate the positive predictive value (PPV), negtive predictive value (NPV), and other values of interest.  
    
  Program functions: `diagnostic.test.design(sensitivity, specificity, prevalence, samp.size, test.type, seed, I)`  
    `sensitivity`: Desired test sensitivity. If `test.type = c(simultaneous, sequential)`, two values must be provided  
    `specificity`: Desired test specificity. If `test.type = c(simultaneous, sequential)`, two values must be provided
    `prevalence`: Desired prevalence. Prevalence = (value + 5) / 100; "+5" added so students cannot guess prevalence from input
    `samp.size`: Desired sample size  
    `test.type`: Type of diagnostic test being used. Options are `c(simultaneous, sequential, none)`. Default is `none`.  
    `seed`: Set seed for reproducability. In team-based learning, use team number for simplicity.
    `I`: Instructor output. Includes row/column totals, PPV/NPV, and brief explanations of how answers were reached.  
