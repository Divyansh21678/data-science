# data-science
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as  sns
sns.set()
data = pd.read_csv('insurance.csv')
print (data.head())
   age     sex     bmi  children smoker     region      charges
0   19  female  27.900         0    yes  southwest  16884.92400
1   18    male  33.770         1     no  southeast   1725.55230
2   28    male  33.000         3     no  southeast   4449.46200
3   33    male  22.705         0     no  northwest  21984.47061
4   32    male  28.880         0     no  northwest   3866.85520
data.describe()
	age	bmi	children	charges
count	1338.000000	1338.000000	1338.000000	1338.000000
mean	39.207025	30.663397	1.094918	13270.422265
std	14.049960	6.098187	1.205493	12110.011237
min	18.000000	15.960000	0.000000	1121.873900
25%	27.000000	26.296250	0.000000	4740.287150
50%	39.000000	30.400000	1.000000	9382.033000
75%	51.000000	34.693750	2.000000	16639.912515
max	64.000000	53.130000	5.000000	63770.428010
plt.figure(figsize=(8,5))
sns.histplot(data['age'], bins=20, kde=True, color='skyblue')
plt.title("Age Distribution")
plt.xlabel("Age")
plt.ylabel("Count")
plt.show()
<img width="699" height="473" alt="download" src="https://github.com/user-attachments/assets/6417ea1f-7377-432d-a333-863e020277b6" />
plt.figure(figsize=(8,5))
sns.histplot(data['bmi'], bins=30, kde=True, color='orange')
plt.title("BMI Distribution")
plt.xlabel("BMI")
plt.ylabel("Count")
plt.show()
<img width="699" height="473" alt="download" src="https://github.com/user-attachments/assets/99080818-38d8-4c2a-9cc2-f5399663deb2" />
plt.figure(figsize=(8,5))
sns.boxplot(x='smoker', y='charges', data=data)
plt.title("Insurance Charges: Smoker vs Non-Smoker")
plt.xlabel("Smoker")
plt.ylabel("Charges")
plt.show()
<img width="716" height="473" alt="download" src="https://github.com/user-attachments/assets/d12425e8-a5c0-4341-959c-4b81c6ac921c" />
plt.figure(figsize=(8,5))
sns.scatterplot(x='age', y='charges', hue='smoker', data=data, palette='coolwarm')
plt.title("Charges vs Age (Smoker Highlighted)")
plt.xlabel("Age")
plt.ylabel("Charges")
plt.show()
<img width="716" height="473" alt="download" src="https://github.com/user-attachments/assets/385aa520-0057-4895-86c7-21056156c8dd" />
plt.figure(figsize=(8,5))
sns.heatmap(data.corr(numeric_only=True), annot=True, cmap="coolwarm", linewidths=0.5)
plt.title("Correlation Heatmap")
plt.show()
<img width="627" height="452" alt="download" src="https://github.com/user-attachments/assets/58273558-648f-4252-836e-920a5f40f7f7" />
