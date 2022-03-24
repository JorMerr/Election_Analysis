# Election Analysis

## Overview of Election Audit
The purpose of this project is to provide a clear and accurate summary of the results of a recent local congressional election for the Colorado Board of Elections. The desired outcome of the analysis, as stated by the Colorado Board of Elections is as follows:
  - Determine the total number of votes cast in the election.
  - Determine the list of all candidates who received votes.
    - For each candidate:
      - List the total number of votes received.
      - List the percentage of votes received.
  - List the winner of the election by popular vote, including their vote percentage and number of votes received.
Additionally, the Colorado Board of Elections requested the following data summary regarding the Counties involved in the election:
  - The list of Counties in the election.
  - Each County's total number of votes cast.
  - Each County's percentage of total votes cast.
  - List the County with the largest voter turnout.

## Resources
The analysis includes script which was built using the following:
- Data Source: election_results.csv
- Software: Python 3.7.6, Visual Studio Code, 1.65.2
It is recommended that the script be executed using the same Software as indicated, otherwise the analyst may encounter unexpected errors.

## Election Audit Results

### Results by Candidate
The analysis of the election shows that:
- There were **369,711** votes cast in the election.
- The Candidates were:
  - *Charles Casper Stockham*
  - *Diana DeGette*
  - *Raymon Anthony Doane*
- The canddiate results were:
  - *Charles Casper Stockham* received **23.0%** of the vote and **85,213** votes.
  - *Diana DeGette* received **73.8%** of the vote and **272,892** votes.
  - *Raymon Anthony Doane* received **3.1%** of the vote and **11,606** votes.
- The winner of the election was:
  - *Diane DeGette*, who received **73.8%** of the vote and **272,892** votes.


### Results by County
The analysis of the election shows that of the total **396,711** votes cast in the election:
- The counties were:
  - *Jefferson County*
  - *Denver County*
  - *Arapahoe County*
- The Voter Turnouts were:
  - *Jefferson County* received **10.5%** of the vote and **38,855** votes.
  - *Denver County* received **82.8%** of the vote and **306,055** votes.
  - *Arapahoe County* received **6.7%** of the vote and **24,881** votes.
- The County with the largest Voter Turnout was:
  - *Denver County*, which received **82.8%** of the vote and **306,055** votes.




An Image of the Summary data has been included for ease of viewing.

![Election Data Summary](https://github.com/JorMerr/Election_Analysis/blob/main/analysis/election_analysis.PNG)

## Election Audit Summary

The script used in this analysis can be used by the election commission for analysis of future elections. In order for the commission to use this script, there are some minor requirements and modifications will need to be made.

First, the dataset referenced must be a .CSV file, with the information laid out similarly to "election_results.csv" with the first item as "Ballot ID", the second as "County", and the third as "Candidate". This will ensure that the data is read correctly when using the index references in the following location:
  ```
   # For each row in the CSV file.
    for row in reader:

        # Add to the total vote count
        total_votes = total_votes + 1

        # Get the candidate name from each row.
        candidate_name = row[2]

        # 3: Extract the county name from each row.
        county_name = row[1]
  ```
If the commission would like to use the script in referencing a different layout of the referenced dataset, the index locations for each row `row[x]` must be modified to ensure effective reading of the data.

Second, it is advised that line 9, `file_to_load = os.path.join("Resources", "election_results.csv")`, be confirmed as the correct path to the dataset file. Any change in file name, or folder location, will cause a reference error when the script is run. It is advised that the script be located in a Main folder, such as has been created with "Election_Analysis", and the dataset be located within a folder within "Election_Analysis" named "Resources". Correct reference to file paths wil ensure that the script is executed correctly.

Third, in the event that the election commission requires the script to be used for an election wherein the locations are not counties, and are instead some other region for analysis (state, municipal, etc.), it is advised that all references to "county" within the script be changed accordingly for ease of reading, writing, and printing of results. While not entirely necessary for the script to execute correctly, there may be some confusion for future analysts to review state election data with the script making reference to counties.

Finally, a portion of the script which was not requested has been commented out to streamline the printing of results to "election_analysis.txt". Lines 118 and 119 would print the percentage of votes received by the county with the largest voter turnout, as well as the total number of votes received by the county. In order to have the information save to "election_analysis.txt", ensure that the hash mark "#" before each of line 118 and line 119 is removed, the python script saved, and the script executed. The following information will print for the election results:

![Additional County Information](https://github.com/JorMerr/Election_Analysis/blob/main/analysis/alternate_largest_county.PNG)


