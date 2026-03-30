
### **ETL Pipeline: Taiwan First Marriage Age**
This project extracts, transforms, cleans, and analyzes marriage data from Taiwan government open datasets to provide insights into the average age at first marriage. The processed data is then loaded into a PostgreSQL database for further analysis.

#### **Tools**
- Programming Language: Python 3.x
- Data Manipulation: pandas
- Data Visualization: matplotlib
- Database: PostgreSQL
- Database connection: SQLAlchemy
- Development Environment: Visual Studio Code, Jupyter Notebook
- Data Sources: [Taiwan government open datasets](https://data.gov.tw/dataset/160207)

#### **Pipeline**
1. **Extract**: Load raw CSV datasets from online sources (URLs)
2. **Clean & Transform**:
   - Remove duplicates
   - Rename columns
   - Drop unnecessary fields
   - Convert Minguo year to Gregorian year
   - Reorder columns
1. **Load**: Store the processed data in a PostgreSQL database
#### **Key Features**
- Structured ETL workflow for clarity and scalability
- Duplicate detection and removal
- Validation of invalid age values (e.g., < 0 or > 120)
- Aggregation by year, gender, and city
- Comparison between major and non-major cities
#### **How to Run / Setup**
1. Clone the repository
```bash
git clone https://github.com/a910590433/etl-postgresql-project.git
cd etl-postgresql-project
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

#### **Findings**
1. In Taiwan, both men and women are marrying at older ages compared to previous years. In 2023, the average age at first marriage was 32.5 for men and 30.5 for women.
2. People in major cities tend to marry about one year later than those in non-major cities, although this gap narrowed slightly in 2023.
3. The top three cities with the highest average age at first marriage for both genders are Taipei, New Taipei, and Kaohsiung.

