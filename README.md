# 1 DATA CLEANING

    ## 1.2 Remove non-wanted columns

        After checking every single column of the dataframe we have found that some of the columns don't add any value, so we have decided to remove them. Here is a summary

        - **Case Number** : For the name of the column you cound deduce that it contains an unique id, but it does not. This column is a "dirty version" of the column date, so we have decided to get rid of it. 
        - **Unnamed: 22 & Unnamed** : 23: Both columns are empty, so we will also deleate them. 
        - **Investigator or Source** : Name of the investigator or source won't be relevant for our analysis
        - **pdf** : Not relevant. It is a concat of the name and date
        - **href & href formula** : Contains a link with the pdf of the attack. We won't need it
        - **Oringinal order**: No clue what this is 
        - **Case number 1 & 2**: We will also get rid of these two columns

        ### 1.2.1 Dropping non-wanted columns

    ## 1.3 Removing empty rows

        ### 1.3.1 Dropping nan rows

    ## 1.4 Column Cleaning

        ### 1.4.1 Function to check column values

        We have created a function that enables us to have a quick look at some relevant kpi's from a column and its values. Fins below the information we are extracting with this function:

        - TOTAL NUMBER OF ROWS
        - NUMBER OF UNIQUE VALUES
        - NUMBER OF UNIQUE VALUES DIVIDED BY TOTAL VALUES
        - % OF NAN VALUES IS
        - COLUMN DATA TYPE
        - COLUMN UNIQUE VALUES
        - VARIABLE WEIGHT WITHIN THE TOTAL OF THE COLUMN

        ### 1.4.2 Cleaning column names

            -  df.rename(columns={"Species ":"Species","Sex ":"Sex","Fatal (Y/N)":"Fatal"},inplace=True)
    
        ### 1.4.3 Cleaning column values

            In this section we are going to perform the cleaning of the variables inside the columns so we can better analyse them afterwards

        ### 1.4.3.1 Date & Month

            After seeing the data, we have decidet to clean this column and create a new one from it. Called moth

            In order to clean this variable we will have to eprform the following changes: 
            - Remove the word "reported" and "Before"
            - Get rid of the year. We already have it the fowwoing column, 
            - We will focus on the month, since we don't have any interest on the day

            On the other hand we are going to clean this new column a litte bit by:

            - Modify July,Sept and March so they can fit into their corrsponsding month
            - Add the random numbers into "month_not_found"

        ### 1.4.3.1 Year

            - Fist we get rid of the .0 from the end of the years
            - Now, we get rid of the corrupted values like "500"

        ### 1.4.3.2 Type

            - Cleaning names like "boating" since they had typos

        ### 1.4.3.3 Sex

            - Removed blank spaces

        ### 1.4.3.4 Fatal 

            - Grouped the variables by removing sapces and uppercases. 
            - Also looked for fatal word in injuries to fill some blanks 

    ## 1.5 Remove duplicates
        - We jsut had two duplicate vales left



2 # HYPETHESES STUDY AND VISUALIZATION

    ## 2.1 HYPOTHESIS 1: Is a surfing attack more fatal than swimming or fishing?

        ### 2.1.2 Creating a df with just info of surfing, skimming and fishing
        - Before that we use a split function in order to get the first word of the sentences from activity. This has been usefull since we had more data into these 3 activities as a result
     
        ### 2.1.3 Creating ad-hoc df for visualization and visualization of the hypothesis

    ## 2.2 HYPOTHESIS 2: Which is the most dangerous Q?

        ### 2.2.1 Created a column names month from the date one selcting the mont in between "-"

        ### 2.2.2 Created a dictionary with the values for each month: 

           - q_dict = {"Jan":"Q1","Feb":"Q1","Mar":"Q1","Apr":"Q2","May":"Q2","Jun":"Q2","Jul":"Q3","Aug":"Q3","Sep":"Q3","Oct":"Q4","Nov":"Q4","Dec":"Q4","month_not_found":"Q_not_found"}

        ### 2.2.3 df creation with crosstab and visualization

    ## 2.3 HYPOTHESIS 3: Is surfing in Australia more dangerous than in USA?

        ### Creating a specific df with the values of the 2 countries & surfers

        ### Visualization













