# monthlymean_windspeed_forecasting
INTRODUCTION:

The code provides monthly average wind speed forecasts, 1-12 months ahead into the future begining from the month after the last date in the provided observation wind speed data.

Time series forecasting approach is used with model types statistical models(2), regression models(2), RNN-based(2).



SYSTEM REQUIREMENTS:

The following code is developed in ipython notebook using some of the external packages (not included in default python3) which are required
to be installed by the user.

STEPS:

1. Anaconda installation

	for all windows, linux and mac (please follow the instructions provided in the link below);
	
	https://docs.anaconda.com/anaconda/install/

	Also refer to the following link for quick start guide

	http://www.cdt-pv.org/media/resources/Anaconda-Quickstart.pdf

	NOTE: Python version installed should be >=3.7. 
	
	      verify this using the following command in terminal or command prompt.
	
	      python3 -V


2. Launch jupyter notebook

	for linux and mac users;

	once after installing the anaconda, open terminal and enter the following command.
	
	jupyter notebook
	
	On  successful installation of anaconda it will open a new tab in your browser.
	
	for windows users;
	
	please refer this video: https://www.youtube.com/watch?v=EbYGBANqDdY


3. Installing packages: 

	After successfully opening jupyter notebook, please terminate the jupyter notebook command
	and install the following package through the terminal or command prompt.

	(Linux, Mac)

        pip install darts==0.19.0
	
        (Windows)

	pip install pyyaml==5.4.1
        
	pip install darts

	python -m pip install prophet
	
	NOTE: Since most of the packages such as pandas, numpy and matplotlib etc. are dependencies
	      to darts package they will be automatically installed.


After installation of following packages please restart (close and reopen) your terminal or command
prompt and open the jupyter notebook using following command.

	jupyter notebook


Once it opens, redirect to the forecast directory downloaded and click on the file named CODE.ipynb.
It opens the code file.


The following code is didvided into sections and sub-sections and with some code cells or snippets below each.
These code cells are to be executed (using run button on the toolbar above or shortcut key shift + enter) in sequence as arranged.



INPUT:


Code requires wind speed observation data in the file named obs_data.csv placed in the same directory or folder.

	Data specifications:
        
        
        File format: CSV (comma seperated value)
        
        
		Columns: DATE (YYYY-MM-DD), windspeed (real number)
	
            Example:
	
			DATE, windspeed
			2014-01-01, 0.6173328
			2014-01-02, 0.4115552
			2014-01-03, 0.9774436
			2014-01-04, 0.6173328
			2014-01-05, 0.771666
            
            
		Frequency: Daily average
		
		Length: Atleast two years i.e 2 * 365 data-points or rows excluding nan values.
		
		Threshold for missing values: 
			
			1. Maximum of 10% within the provided time frame (start date to end date).
	
			2. Length of maximum gap should be <= 5 days. 
	
	NOTE: Saving data using excel is changing DATE format to DD-MM-YYYY which  gives semantic error.  	
