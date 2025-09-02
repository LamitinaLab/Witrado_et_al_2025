Project code for of analysis of ASH GCamP6s data in Witrado et al, 2025. 
The 'combining ROI data' pulls the FIJI quantified ROI data from multiple files into a single csv file neuron and background ROIs are paired in adjacent columns. First column is the frame #
The 'single stim pipeline' performs all background subtraction, photobleach correction, and conversion to %deltaF/F0 data for each neuron, which is output as a csv file for comparative analysis. Heat map plots for every neuron are generated.
The 'comparing deltaF/F0 data between groups' performs comparative plotting and statistics for two or more groups. Also calculates peak %deltaF/F0 values during the stimulation period. Input is the time-corrected %deltaF/F0 data for each neuron csv file, one file per group.
