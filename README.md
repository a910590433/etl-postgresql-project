
### **ETL Pipeline: Taiwan First Marriage Age**
This project builds an end-to-end ETL pipeline to process and analyze Taiwan government open data on the average age at first marriage. It extracts raw datasets from online sources, performs data cleaning and transformation, and loads the processed data into a PostgreSQL database for analysis and visualization.

#### **Tools**
- Programming Language: Python
- Data Manipulation: pandas
- Data Visualization: matplotlib
- Database: PostgreSQL
- Database connection: SQLAlchemy
- Development Environment: Visual Studio Code, Jupyter Notebook
- Data Sources: [Taiwan government open datasets](https://data.gov.tw/dataset/160207)

#### **Pipeline Overview**
1. **Extract**: Load raw CSV datasets from online sources (URLs)
2. **Clean & Transform using Python**:
   - Remove duplicate records
   - Standardize and rename columns
   - Drop unnecessary fields
   - Convert Minguo years to Gregorian years
   - Reorder columns
   - Validation of invalid age values (e.g., < 0 or > 120)
3. **Load**: Store the processed data in a PostgreSQL database
#### **Key Features**
- Applies data validation and cleaning best practices
- Performs aggregation by year, gender, and city
- Enables comparison between major and non-major cities
- Integrates data visualization to highlight overall trend
#### **How to Run / Setup**
1. Clone the repository
```bash
git clone https://github.com/a910590433/etl-postgresql-project-1.git
cd etl-postgresql-project-1
```
2. Install dependencies
```bash
pip install pandas matplotlib sqlalchemy psycopg2
```
3. Set up PostgreSQL
- Create a database (e.g., twmarriage)
- Update your connection settings in the script:
```python
user = "your_username"
password = "your_password"
host = "localhost"
port = "5432"
database = "twmarriage"
engine = create_engine(
    f"postgresql+psycopg2://{user}:{password}@{host}:{port}/{database}"
)
```
4. Run the ETL script
Execute the Python script to extract, transform, and load the data

#### **Findings**
1. The average age at first marriage in Taiwan has steadily increased over time for both men and women.
2. In 2023, the average age at first marriage reached **32.5 for men** and **30.5 for women**.
3. Individuals in major cities tend to marry approximately **one year later** than those in non-major cities, although this gap narrowed slightly in 2023.
4. The top three cities with the highest average age at first marriage for both genders are **Taipei, New Taipei, and Kaohsiung**, indicating a strong urban effect on marriage patterns.
