import pandas as pd 

df = pd.read_csv("sample_data.csv")   
#opens sample_data.csv as a dataframe

print(df.isna().sum()) #checks for any NaN spaces and gives number for each column


df["Age"] = pd.to_numeric(df["Age"], errors="coerce")

df["Score"] = pd.to_numeric(df["Score"], errors="coerce")
#fills any non numeric value in df["Age"] and replaces it with NaN

df.fillna({"Age": 0}, inplace=True)

df.fillna({"Score": 90}, inplace=True)
#replaces NaN in df["Age"], and df["Score"]" with value of 0 and 90 updates the table in place



print(df["Age"].dtype)

df["Name"] = df["Name"].str.strip()   #checks data type of df["Age"] and prints it 
print(df)

df.to_csv("sample_data_cleaned.csv", index=False)
