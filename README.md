# JobScraper - Automation

This project is a web scraping tool designed to automate the search for AI/ML job opportunities on popular job portals such as [Rozee.pk](https://www.rozee.pk/) and [Indeed](https://pk.indeed.com/). The tool utilizes Selenium to gather key job listing information and organizes it into a structured dataset for easy analysis.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Data Fields](#data-fields)
- [Example Output](#example-output)
- [Disclaimer](#disclaimer)
- [Contributing](#contributing)
- [License](#license)

## Features

- Scrapes job listings for AI/ML Engineer positions from Rozee.pk and Indeed.
- Collects essential details such as job title, company name, location, gender preference, education level, degree, experience, job type, and salary (if available).
- Saves the data in CSV files for further analysis and filtering.
- Filters jobs based on location (e.g., recommends jobs in Islamabad).
- Automation for multi-page scraping on Indeed.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Hasnain2430/AI-ML-Job-Scraper.git
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download and set up [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/downloads) (or use WebDriver Manager for automated setup).

## Usage

1. Open the main script (`job_scraper.py`) in a Jupyter Notebook or similar environment.
2. Run each cell in sequence to start scraping job listings from Rozee.pk and Indeed.
3. The tool will open a browser window, navigate to the job portals, and start collecting data for AI/ML Engineer positions.

4. Once complete, two CSV files will be created:
   - `Rozee_Data.csv`: Contains job listings from Rozee.pk.
   - `Indeed_Data.csv`: Contains job listings from Indeed.

5. To filter jobs by location (e.g., Islamabad), use the filtering code provided at the end of the script.

## Data Fields

The tool collects the following data fields:

### Rozee.pk
- **Job Title**: Title of the job position.
- **Company Name**: Name of the hiring company.
- **Job Location(s)**: Location of the job.
- **Gender Preference**: If specified, the preferred gender for the role.
- **Minimum Education**: Minimum education level required.
- **Degree Level**: Specific degree requirements (if available).
- **Experience**: Required years of experience.
- **Link**: Direct link to the job listing.

### Indeed
- **Job Title**: Title of the job position.
- **Company Name**: Name of the hiring company.
- **Job Location(s)**: Location of the job.
- **Job Type**: Type of job (e.g., full-time, part-time).
- **Salary**: Salary range (if specified).
- **Link**: Direct link to the job listing.

## Example Output

The output is saved in CSV format and can be imported into any data analysis tool (e.g., Pandas, Excel) for further processing. Here’s an example of filtering for jobs located in Islamabad:

```python
df2 = pd.read_csv('Indeed_Data.csv')
filtered_df2 = df2[df2['Job Location(s)'].str.contains('Islamabad', case=False)]
print("Recommended Job(s) in Islamabad:")
filtered_df2
```

## Disclaimer

The scraper may not work properly or may require adjustments if the HTML structure of the web pages has changed. Please inspect the page structure and update the XPath or CSS selectors as necessary.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request to improve the project.
