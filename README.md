# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

Load and preprocess data: Import data, inspect it, and handle missing values if any.

Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.

Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.

Assign cluster labels to each data point.

Plot data points in a scatter plot, color-coded by cluster assignments for interpretation.. 

## Program:
    import pandas as pd
    import matplotlib.pyplot as plt
    data = pd.read_csv("Mall_Customers.csv")`
<br>

    data.head()
<br>
      data.isnull().sum()

    from sklearn.cluster import KMeans
    wcss = []
    for i in range(1,11):
        kmeans = KMeans(n_clusters = i,init = "k-means++",n_init=10)
        kmeans.fit(data.iloc[:,3:])
        wcss.append(kmeans.inertia_)
<br>
        plt.plot(range(1,11),wcss)
        plt.xlabel("No. of Clusters")
        plt.ylabel("wcss")
        plt.title("Elbow Method")

<br>
    km = KMeans(n_clusters=5, n_init=10)
    km.fit(data.iloc[:, 3:])
    y_pred = km.predict(data.iloc[:,3:])
    y_pred

<br>
    data["cluster"] = y_pred
    df0 = data[data["cluster"]==0]
    df1 = data[data["cluster"]==1]
    df2 = data[data["cluster"]==2]
    df3 = data[data["cluster"]==3]
    df4 = data[data["cluster"]==4]
<br>

    plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster1")
    plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster2")
    plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster3")
    plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster4")
    plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster5")
    plt.legend()
    plt.title("Customer Segments")



## Output:

<img width="570" height="237" alt="398593633-70e1aca3-4a71-4696-b2b9-928d77b0a83e" src="https://github.com/user-attachments/assets/bd363106-0bdf-4b13-bea0-dc7ccd923726" />




<img width="566" height="280" alt="398593649-7caea61e-f3c1-47c5-b8fe-2bc2e909dfe9" src="https://github.com/user-attachments/assets/0f5b5aa0-111a-49a4-b17d-242a0e8e5c56" />



<img width="279" height="174" alt="398593664-8334f36d-3acc-4643-8a5f-cabdcb3a59f2" src="https://github.com/user-attachments/assets/c8ebd4e7-f9f0-4ec1-9f94-92beafd1596f" />




<img width="732" height="761" alt="398593695-63016bcc-0be2-4f62-bbab-a741adb491e1" src="https://github.com/user-attachments/assets/fdc9f61a-89e0-4e72-bc10-66df76e93ec6" />


<img width="732" height="402" alt="398593725-6e28ea51-13fb-4803-a47a-31437f95b6f6" src="https://github.com/user-attachments/assets/88b70890-cb37-428b-8433-7c769ef4e0ab" />

<img width="866" height="777" alt="398593754-3e4f7550-b44f-4de9-b739-505a989a2293" src="https://github.com/user-attachments/assets/d53175ee-a7b7-4481-b6da-71a11f3fd4a5" />




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
