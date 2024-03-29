# SP_LAB
Collaborative GitHub


# NOTES
Important: all functions have to be created in separate notebooks and called from the main. Keep in mind that you may need to import some modules inside the function so it can properly work (even when the modules are imported in the main). 

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Collaborator 1 
• Function renamevars (df, dict_names) Rename variables on a given dataframe df. The function returns a df who’s columns names are as detailed in dict_names Inputs:  df: a given data frame dict_names: a dictionary for mapping 
the actual names of the columns in the dataframe (each key of the dictionary) to a given new simpler name (i.e. the values of the dictionary). You can follow the example in the notebook numpy_pandas_sklearn.ipynb for the Lab 4. 
Output:  renamed_df: returns the input dataframe but with the columns renamed as in dict_names Please work with a version of the dataset that uses simple names for the rest of the analysis

• Summarize the data after cleaning (that is, after removing some correlations) when the data is ready. Annotate your observations. For example, how many observations do you have? Are there apparent differences between controls 
and patients? Is the variability comparable? If you check the minimum and maximum values are there outliers? If so, what will you do with them? 

• Using the function group_and_average, create a dataframe for aggregating each variable of the cleaned_dataframe across trials for each subject. 
The resulting dataframe should consist on 32 observations, one for each subject.  

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Collaborator 2 
• Function scat_plt (var1, var2, groups) Given the variables var1 and var2, creates a scatterplot of the two variables, displaying the information given on groups using different colors (or symbols). That is, observations belonging 
to a given group 1 will be displayed on a given color, observations belonging to group 2 will be displayed with a different color and so on.  var1 is displayed in the xaxis and var2 in the y-axis. The obtained plot should contain a 
legend displaying the information regarding to groups  Inputs: var1 and var2: Two given variables of the same length groups: A variable the same size as var1 and var2 where the information regarding to group belonging is contained. 
  
• Based on the variable ‘name’ write some code in the main that creates two new columns in the dataframe: one displaying the subject id (S1, S2, S3…) and another displaying the trial (t1, t2, t3, …, t6 or t7 in some cases). Remover 
the column name from the dataframe. 

• Function normalize (df, op) Given a dataframe df, normalizes all variables according to the options in op. op can only take two values, 0 for normalizing the variables based on the z-score and 1 for normalizing the variables based 
on the min_max approach. The function returns a dataframe consisting on normalized variables. Be aware of avoiding normalizing variables that are supposed to be categorical, even if the type of such variables is not specifically categorical 
(that is, a variable can be of type numerical even when it represents categories) Inputs: df: A given dataframe op: numeric variable (either 0 or 1) Output norm_df: normalized dataframe   


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Collaborator 3 
• Look for correlations between the variables related to the fundamental frequency ('MDVP:Fo(Hz)', 'MDVP:Fhi(Hz)’ and MDVP:Flo(Hz) in the original dataframe) using the scat_plot function. Use the scat_plot function created by your 
collaborators for this purpose. If the variables are correlated keep only a subset that are representative (one or some of them). Discard the others by removing them from the dataframe. Do the same for the variables related to Jitter 
('MDVP:Jitter(Abs)', 'MDVP:RAP', 'MDVP:PPQ', 'Jitter:DDP') and Shimmer (   'MDVP:Shimmer', 'MDVP:Shimmer(dB)', 'Shimmer:APQ3', 'Shimmer:APQ5',  'MDVP:APQ', 'Shimmer:DDA',). Name this dataframe as cleaned_df and work with it from here on. 
  
• Function group_and_average(df, gv) This function averages all variables on a given dataframe by aggregating them according to the variable gv. You can use the group_by operation from pandas. The function returns the averaged and aggregated 
dataframe. Inputs: df: a dataframe gv: the name of the grouping variable Outputs: av_df: averaged df   
  
• Implement the instructions in the main code to classify the DataFrame data into patients or controls using k-nearest neighbors with k=3. Compare the outcomes across three scenarios: 1) utilizing cleaned and aggregated data, 2) cleaned, 
aggregated, and z-score normalized data, and lastly, 3 the same, but normalized using the min-max option. Are there differences? 
