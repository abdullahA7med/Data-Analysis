**import pandas**

		import pandas as pd

**in pandas we have main 2 object**
- Series
- DataFrame (most usage)

1) Series

		-> dg = [1,2,22,1,10]
		# convert list to series
		pd.Series(dg)

		-> data = pd.Series([1,2,3,4,5])
				print(data)

0    1
1    2
2    3
3    4
4    5

2) DataFrame  

		-> there are many ways to create series, most usage from => python dictionary
			data = pd.DataFrame({'population':[7655695,633894,7678935,9568232],'area':[204,212,1973,3085]})
			print(data)

||population|area|
|---|---|---|
|Baghdad|7655695|204|
|Tunis|633894|212|
|Riyadh|7678935|1973|
|Cairo|9568232|3085|


#### To convert Data To numpy array ⚓
**use -> .values function**

-------------------------

**From here you deal with real DataSet.**

as we know pandas deal with tabular data

- core jop of pandas analysis & summarize the data.

**to read your data use:**

	- read_csv  -> for csv file
	- read_json -> for json
	- read_excel -> for excel file


#### 1. display your dataFrame 📌:

1) head() :

		data.head() -> display by defoult first 5 rows | you can change that.
		data.head(3) -> first 3 rows.

2) tail() :

		data.tail() -> by defolut last 5 rows
		data.tail(2) -> last 2 rows 


3) Type name of DataFrame :

		data -> will print first and last five rows | that max and defolut
		- TO change use set_option function
			 -> pd.set_option('display.max.rows',228)


--------------------
#### 2. Indexing & selection 🧲
in pandas we have 2 function
1) loc  -> location | => lable indexing

		df.loc[rows, column_name]
		df.loc[:,'Country']  # -> select country column.
		
		df.loc[:,['Brand','Style']] # -> select the both columns. 


2) iloc -> integer location | index base selection

		df.iloc[rows, columns]
		df.iloc[:,3] # -> the index num of column i need.
		ddf.iloc[:,[3,4,5]] # -> here i selected multible columns.

**the next way not prefered:**

3) it like lable indexing:

		df['column_name']
		df['Country']


**How can i use them in filtering my data?**

		df.loc[df['Country']]
		df.loc[df.loc[:,'Country']]
**if you remember making in numpy, i used it here.**


-------------------------------
#### 3. conditional selection(Filtering)🤖:
here i select column or columns with condition i need

 EX :
	 -> i need all ages which less than 50
	 -> top 10 Ranked of country.
**we use indexing&selection functions.**

		top 10 country:
		df[df['Rank'] < 10]
		df.loc[df['Rank'] < 10]


		df.loc[df['age'] < 50]
				OR
		df.loc[df['Country'] == 'Egypt']

**what is i need select many country or -> any elemints**

		most_africa=['Nigeria','Egypt','Algeria']
		df.loc[df['Country'].isin(most_af)]


**i can filter by the part of wold (just for string)** => .str.contains()

like:
	united -> give you any row have united word .
	a -> give you any row have the alphabet of a.


		df.loc[df['Country'].str.contains('United')]
		df.loc[df['Continent'].str.contains('E')]

------------------------

