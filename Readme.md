# Module 22 Home Sales Challenge
The main file in this repository is the home_sales_colab.ipynb file which is best run in Google Colab.  In the resources folder is the challenge instruction page as well as the unused home_sales.ipynb notebook.  

In this main file, the below functions are performed:
- The current version of Spark 3.5.5 is imported as an os, the current version of Spark and Java are installed, the environment variables are set, and a Spark Session is started
- pyspark and time are imported and a Spark Session is created
- a CSV file is read and created into a dataframe from the provided AWS S3 bucket link.  This dataframe is shown to ensure it was read properly

  ![image](https://github.com/user-attachments/assets/65a023e7-16d0-45ec-a600-01f897ddcdbe)

- A sparkSQL query checks for Average prices for four bedroom houses sold per year

  ![image](https://github.com/user-attachments/assets/753769e9-9384-4b48-8363-769cb7d88d41)

- A sparkSQL query checks for Average prices for homes sold that have 3 bedrooms and 3 bathrooms per year

  ![image](https://github.com/user-attachments/assets/8ed5586a-db1c-4b57-b57a-855177590a3b)

- A sparkSQL query checks for Average prices for homes sold that have 3 bedrooms, 3 bathrooms, 2 floors, and 2,000 or higher square feet per year

  ![image](https://github.com/user-attachments/assets/ba60b406-0aba-449a-bb77-0b6d066477a6)

- A sparkSQL query checks for Average prices of homes worth $350,000 or greater per view rating.  The query load time is also recorded and shown (0.99 seconds)

  ![image](https://github.com/user-attachments/assets/8937ac79-9697-4986-a837-eba599aa60b2)

- The home_sales table is cached in memory and then checked to make sure it cached correctly.  Then, A sparkSQL query checks for Average prices of homes worth $350,000 or greater per view rating (from cached table) and the query load time is shown to compare against the query above.  The same query from a cached table is 0.61 seoncds (noticeably faster)

  ![image](https://github.com/user-attachments/assets/59b618c0-ffb3-4f9c-93b2-6e1529c7df1f)

- The table is parqueted and this parqueted data is partitioned on the date_built column. Then, the same query as above is performed.  The query runtime is captured and shown as 0.42 seconds which is even faster than the same query from the uncached and cached table

  ![image](https://github.com/user-attachments/assets/07eefa5d-4cb4-4441-b0d9-853fd824cf9d)

- The home_sales table is uncached to clear up the memory it was stored in. Then, a quick check to make sure it is uncached is done

  ![image](https://github.com/user-attachments/assets/4b7e6f0b-538d-47aa-b1e4-bbb7054d6581)


