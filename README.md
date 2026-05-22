### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 22-05-2026
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
# Visitor segmentation based on characteristics
# read the data
import pandas as pd
df=pd.read_csv("clustervisitor.csv")
df

# Perform segmentation based on characteristics (e.g., age groups)
cluster={'Young':(df['Age']<=30),'Middle':((df['Age']>30) & (df['Age']<=50)),'Old':(df['Age']>50)}
count=[]
for g,v in cluster.items():
    visitor=df[v]
    print(f"The visitors in {g} Group are\n",visitor)
    print("count= ",len(visitor))
    count.append(len(visitor))
```
### Output:
<img width="536" height="307" alt="image" src="https://github.com/user-attachments/assets/85a25979-c137-4734-8896-04dc93eac431" />

<img width="607" height="642" alt="image" src="https://github.com/user-attachments/assets/c90db5d8-776d-46a8-99b4-c50bf988becc" />

<img width="496" height="145" alt="image" src="https://github.com/user-attachments/assets/4859b1c1-9ed3-485a-920b-1d161a43947a" />

### Visualization:
```

import matplotlib.pyplot as plt
plt.figure(figsize=(8, 6))
plt.bar(cluster.keys(), count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
<img width="700" height="545" alt="image" src="https://github.com/user-attachments/assets/2e826b9b-2697-4de7-9dee-00f10c8f30bd" />


### Result:
Thus, visitor segmentation based on age groups was successfully done using Python.
