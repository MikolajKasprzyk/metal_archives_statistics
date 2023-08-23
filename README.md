# Metal Bands Data Analysis

## Project Overview

This data science project focuses on analyzing data scraped from the Metal Archives website to gain insights into various aspects of metal bands. The project includes web scraping, data cleaning, and database creation. The extracted data is then visualized using Tableau to create an interactive dashboard.

## Data Sources

The data for this project was scraped from the [Metal Archives website](https://www.metal-archives.com/). The website provides information about metal bands, including band names, discographies, genres, band members, and more.

## Methodology

The project involved the following steps:

1. Web Scraping: The web scraping process was conducted in two stages:

   a. Scraping Band URLs: Initially, the project involved scraping the URLs and bands names for every single band listed on the Metal Archives website. That was achived using Metal-Archives alphabetical list of bands, navigating letter by letter. The dataframe of urls and names was then exported to pickle file and used in the next step to navigate to every band in Metal-Archives website.

   b. Scraping Band Information: Once the band URLs were obtained, the code utilized Selenium and BeautifulSoup libraries to open each band's page and extract additional information such as discography, band members, and other details. Extracted data was then gathered into dataframe and exported to in pickle format. During data scraping database was updated every few bands, because there is lots of bands and it was not possible to scrape all of them in one session. Links to urls and raw scraped data below in 'Scraped data dataframes, section.

2. Data Cleaning: The scraped data was cleaned and processed to remove duplicates, format dates, handle missing values, and transform the data into a suitable format for analysis. The cleaning code is provided in the 'data_cleaning.py' file.

4. Database Creation: The cleaned data was used to create a relational database with tables for bands, records, genres, artists, lyrics, and band-year information. The database schema is represented in the ER diagram provided in the 'ER_diagram.png' file.

5. Additional database of 'world_population.csv' from Keggle was used to create visualiztions that needed those data.  

6. Visualization: The cleaned data was exported to CSV files and used to build an interactive dashboard in [Tableau](https://public.tableau.com/) containing various visualizations and insights derived from the data. The dashboard can be accessed [here](https://public.tableau.com/app/profile/miko.aj.kasprzyk/viz/metal_archives_statistics/Dashboard1).

## ER Diagram

![alt text](https://github.com/MikolajKasprzyk/metal_archives_statistics/blob/main/ER_diagram/metal_archives_ER_diagram.png)

## Files

- 'metal_archives_scraper.py': Python code for web scraping the Metal Archives website, `notebooks` directory.
- 'metal_archives_processing.py': Python code for cleaning and processing the scraped data, `notebooks` directory..
- 'metal_archives_ER_diagram.png': ER diagram illustrating the database schema, `ER_diagram` directory.
- 'world_population.csv': Keggle dataset with word population,  `data` directory
- 'README.md': This file providing an overview of the project.

## Usage

To reproduce the analysis and explore the data:

1. Run the 'scraping_code.py' file to scrape the data from the Metal Archives website. Ensure that the required libraries (Selenium, BeautifulSoup) are installed.

2. Run the 'data_cleaning.py' file to clean and process the scraped data. Make sure to adjust the file paths and dependencies as needed.

3. Use the cleaned CSV files ('band.csv', 'record.csv', etc.) as input to create the database. Load the CSV files into a database management system (e.g., MySQL, PostgreSQL) and execute the SQL statements provided in the 'database_creation.sql' file to create the tables and populate them with data.

4. Open the Tableau workbook file ('metal_bands_dashboard.twb') to explore the visualizations and insights derived from the data. Adjust the connection settings to connect to the created database if necessary. The interactive dashboard can be accessed [here](https://public.tableau.com/app/profile/miko.aj.kasprzyk/viz/metal_archives_statistics/Dashboard1).

## References

- [Tableau Public interactive dashboard](https://public.tableau.com/app/profile/miko.aj.kasprzyk/viz/metal_archives_statistics/Dashboard1).
- [Metal Archives website](https://www.metal-archives.com/)
- [Keggle World Population dataset](https://www.kaggle.com/datasets/iamsouravbanerjee/world-population-dataset)

### Scraped data dataframes:
- [Bands URLs Dataframe](https://drive.google.com/file/d/1-UfaAvWHm4vEQQGQCpq5mGCzaQe_KCFX/view?usp=sharing)
- [Raw Data Dataframe](https://drive.google.com/file/d/1o5Rle2OSVvGL7PHpPbD_Jy_wgJHzpsLr/view?usp=sharing)

 Special thanks to the following repositories and their respective contributors for providing valuable code that was utilized in this project:

   - [ma-scraper repository](https://github.com/jonchar/ma-scraper) by jonchar
   - [metal_archives repository](https://github.com/st-olz/metal_archives) repository by st-olz

Their code served as a foundation for the web scraping process, and their contributions were instrumental in the success of this project. I am grateful for their efforts and the open-source community's collaborative spirit.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT). You are free to use, modify, and distribute the code and analysis results.

