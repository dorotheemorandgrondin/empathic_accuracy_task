Development and validation of an adapted version of the Empathic Accuracy Task (EAT)

=== CONTEXT ===

First, we created video stimuli depicting individuals ('targets') narrating emotional autobiographical events. Heart rate was continuously recorded during the narratives. 
Second, targets watched their own videos and rated their emotional experience, including (1) a continuous valence rating through the video, and (2) an evaluation of the specific emotions they experienced. 
Third, other individuals ('observers') watched the videos and inferred the targets' emotional states on the same continuous and discrete scale. 

=== DATA ANALYSIS IN ORDER ===

'behavioral_analysis_1'
	Here we smooth the continuous emotional valence ratings of targets and observers in a window of 10s to reduce noise. And make graphs for visual representation of the data.
	Output = smoothed data

'behavioral_analysis_2'
	Here we take the continuous and discrete ratings, and calculate correspondance between targets and observers for every trial (all pairs, including surrogate ones for further analysis). For exploratory purposes, we also compute the max correlation with a lag of +/-5s for the perceiver's evaluation (to account for the fact that targets might know or recognize their own emotions before observers can pick them up).
	Output = EA scores per trial (both continuous rating and specific emotion recognition)

'behavioral_analysis_3'
	First, we z-transform correlation values. 
	Second, we assess specificity of the evaluations for continuous EA (i.e., correlations between continuous valence ratings of target and observers) and discrete EA (100 - sum of distance between target and observer evaluation for each emotion on the Geneva Emotion Wheel). To do so, we do a one-sample t-test. Then we do the same (with correction for multiple comparisons) on target-level. With graphs. 
	Output = adding a percentile column for every trial score to the original EA scores data (relative to target distribution + to the full distribution) 

'physiological_analysis_1'
	Here I make functions to identify R-R intervals, and then ectopic beats (removing them). I save the R-R intervals in a new file. 
	Output = cleaned R-R intervals

'physiological_analysis_2'
	Create smoothing functions to smooth bpm and rmssd signals. 
	Then perform correlations between target-observer pairs, including surrogate pairs. 
	Output = HR-HRV one-shot metrics for targets and observers; smoothed bpm and rmssd, synchrony scores per trial

'physiological_analysis_3' 
	First, we z-transform correlation values. 
	Second, we assess the specificity of HR and HRV synchrony (i.e., correlations between HR and HRV of targets and observers). To do so, we do a one-sample t-test. Then we do the same on target-level. With graphs. 
	Output = adding a percentile column for every trial score to the original HR and HRV scores (relative to the target distribution + to the full distribution).

	
