# Project

Data Modeling Project

## Description

This project is an extension of the previous Data Prep Project. It features a larger
dataset, a simpler design structure, a more streamlined dataflow, and most importantly
it sets up a fact-dimension (star schema) table series for advanced data modeling.
For this project, the input is a medium-sized dataset and the output is an initial profile
report and csv files. The profile report provides a multitude of summary sections
with important high-level details. The csv files contain specific columns from the
original dataset that can be connected and used to model data in another program. The
data modeling program for this project is Microsoft Power BI. Pictures of the models are included
below to show that the data was processed and prepared successfully. Power BI was used to
connect the fact table to the dimension tables through foreign keys. The fact table
remains denormalized while the dimension tables undergo duplicate removal before and
after importing them into Power BI. The dimension tables are connected to the fact
table in a one-to-many relationship. Foreign keys from each dimension table were added
to the fact table. Then columns of different tables were selected based on questions
relevant to the context of the dataset itself. The models are intended to answer basic
questions about the data over time. The reports include counts and percentages to present
various statistical facts about the data trends.

## Getting Started

### Dependencies

* This program utilizes several Python libraries including:
  * pandas
  * pathlib
  * ydata_profiling
  * requests
  * io
* The program is designed for Windows 11

### Installing
* To install the program from GitHub, run the following code:
```
git clone https://github.com/AbsoluteAI/Data-Modeling-LA-Crime-Stats.git
```

### Executing program
* From the terminal, run the following code to install all required libraries to run the program:
```
pip install -r requirements.txt
```
* Run the program using the following command:
```
python src/main.py
```
* The program will present a menu to prompt users to view each step of the data
processing phase.
![data modeling project menu img](snippets/data_modeling_menu.png)
* The first step is to extract the data by entering "1" when prompted to initiate the
extraction process.
  * Enter the corresponding number to activate each step in order
  * If the file already exists then the contents will be written to a new dataframe
  * If the file does not exist then it will be downloaded directly from the website
* The second step is to profile the data
  * Below shows an example of the profile report which can be opened using a web browser
  of your choosing
  ![profil report img](snippets/ydata_profile_report.png)
* The third step is to transform the data
  * This process currently only involves removing empty rows before exporting the data
for modeling
* The fourth step is to load the data
  * The data is written to separate csv files with selected columns for visualization
* Once all files are viewed, copied, etc. the user can either type "5" to remove the temporary
files or type "6" to end the program and retain the files
* The next steps involve importing the csv files into Microsoft Power BI or the user's
desired data modeling application.
* This snippet shows the star schema and relationships between the fact and dimension
tables
![star schema structure img](snippets/star_schema_structure.png)
* The reports are located below
* Each report visualizes specific trends in the data
![la crime stats reports pdf](reports/la_crime_stats_reports.pdf)
* At this point there are currently four report items:
  * Victim Sex Trends
    * Intended to show the number of victims over time by sex
  * Weapon Types Used
    * Intended to show the types of weapons used throughout the dataset timeframe
  * Total Incidents by Description
    * Intended to show the types of crimes committed within the dataset timeframe
  * Count of Crime by Area
    * Intended to show the concentration of crimes by area using longitude, latitude,
and a map of Los Angeles as the backdrop of a scatterplot

## Authors

Alexander Dodd
[@linkedin.com](www.linkedin.com/in/alexander-j-dodd93)

## Version History

* 1.1
    * Various bug fixes, restructuring, and optimizations
    * See [commit changes](https://github.com/AbsoluteAI/data_prep_project/commits/master/) or See [release history]()
* 1.0
    * Initial Release

## License

This project is licensed under the MIT License - see the LICENSE.md file for details

## Acknowledgments

This program uses a dataset downloaded directly from data.gov with the Python requests library
* [LA Crime Statistics from 2020 to the Present](https://data.lacity.org/api/views/2nrs-mtv8/rows.csv?accessType=DOWNLOAD)