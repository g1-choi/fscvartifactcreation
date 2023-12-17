All files used to create the artifacts are in artifact_creation. The files are labeled by their respective artifact type: 
createfscvartifactrctype_railtype creates a rail type artifact and saves as a CSC file for processing in plexon, for a clean input CSC file. 
createfscvartifactrctype_RCtype creates an RC type artifact and saves as a CSC file for processing in plexon, for a clean input CSC file. 
createfscvartifactrctype_rtype creates an r type artifact and saves as a CSC file for processing in plexon, for a clean input CSC file. 

These files work on a per channel basis after running  the script example_getephysdata to load the csc files. An example of the loop I use for one session can be seen below:
session='98b'; % string that has all the 
channels=[4 5 8 9 12]; % all the csc channel numbers that you want to add and remove artifact from   % from the spreadsheet for corresponding CSC. a cell or strings. commasep 
for u=1:length(channels)
    selectcsc=channels(u);   %CSC channel number change here
    pathnlx=['Z:\data_MIT\patra_fscv\patra_chronic98b_07022018\spikes\']; % where you have the original CSC
    example_getephysdata
    createfscvartifactrctype_RCtype
end 

Additional code needed for these to run are in Nlx_411 and dg_lib

All the data used for the analysis is in the data files folder uploaded on Zenodo. 
In the data files folder the data is organized by session. In each session folder is the .mat files used for percent recovery calculations. The R, RC, and Rail folders contain the channels with the simulated artifacts saved as plexon files. The interpolated versions of these files are under the interp folder, separated into folders by artifact type. All the data used for the PC plots in the paper are under session 65 in the PC_plots folder 


