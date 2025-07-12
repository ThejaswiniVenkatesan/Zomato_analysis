Zomato India Dataset Cleaning & Preparation for Visualization

📄 Dataset Source

Title: Zomato Dataset

Author: Rajesh Rampure

Platform: Kaggle

File Name: zomato.csv

Description: A rich dataset containing restaurant details such as name, location, rating, cuisines, cost, etc., for various restaurants across India.

🎮 Objective

Prepare a clean, analysis-ready dataset from the raw Zomato dataset. The output will be used for visualization purposes in Tableau or other BI tools.

Challenges in Raw Data

Messy column names with inconsistent formatting

Ratings in string format (4.1/5, NEW, -, etc.)

Cost given for two people only

Presence of null values

Redundant or noisy columns (like URLs, raw reviews)

Goals

Standardize column names

Clean and normalize rate and cost columns

Derive a new column cost_per_person

Drop irrelevant or unhelpful fields

Output a CSV that can be directly visualized

⚙️ Cleaning Steps

1. Column Standardization

Converted all column names to lowercase

Replaced spaces, parentheses, and hyphens with underscores

Renamed misaligned columns:

approx_cost_for_two_people → approx_costfor_two_people

listed_in(type) → listed_intype

listed_in(city) → listed_incity

2. Rating (rate) Column

Removed /5 text

Replaced NEW and - with NaN

Converted to float

Filled missing values with mean of available ratings

3. Cost Column

Converted approx_costfor_two_people to numeric

Created a new column: cost_per_person = approx_costfor_two_people / 2

Dropped the original approx_costfor_two_people

4. Null Handling

votes: Converted to integer, filled NaN with 0

phone: Replaced missing with "Not Available"

cuisines: Replaced missing with "Unknown"

rest_type: Replaced missing with "Unknown"

dish_liked: Replaced missing with "Not Mentioned"

5. String Cleanup

Removed newline (\n) and carriage return (\r) characters

Trimmed leading/trailing spaces in all string columns

6. Dropped Columns

The following columns were removed to reduce noise and enhance clarity:

url

menu_item

reviews_list

phone

address

📁 Output Files

File Name

Description

zomato_clean.csv

Final cleaned dataset for visualization

Zomato_Cleaning.ipynb

Jupyter notebook with all cleaning steps

README.md

Project documentation (this file)

🛠️ Requirements

pip install pandas numpy

⭐ How to Use

Run the notebook Zomato_Cleaning.ipynb

The script will generate zomato_clean.csv

Import the CSV into Tableau or Power BI

Create visualizations on rating, cost, cuisines, location, etc.

👨‍💼 About

Thejaswini S V
Data Analyst | Python & BI Enthusiast
Connect on https://www.linkedin.com/in/thejaswini-venkatesan-687ba3259 or Email:thejaswinivenkatesan@gmail.com

🔖 License

This repository is intended for educational and analytical purposes. Dataset usage must comply with Kaggle's Terms of Service.

