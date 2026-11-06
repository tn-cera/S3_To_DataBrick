Spark practice datasets

Files:
- customers.parquet / customers.csv: customer_id, customer_name, city
- sales.parquet / sales.csv: sale_id, customer_id, sale_date, amount

The customer_id column links the two datasets.
There are 30 sales and 12 customers. Some sales are <= 500 so your filter is meaningful.

Example:
sales = spark.read.parquet("s3://company/sales/")
customers = spark.read.parquet("s3://company/customers/")

If using the CSV copies:
sales = spark.read.option("header", True).option("inferSchema", True).csv("...")
customers = spark.read.option("header", True).option("inferSchema", True).csv("...")
