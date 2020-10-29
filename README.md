# 104 assignment

## Data preprocess
Use K means to cluster the questions in 5 clusters, after the clustering is done, tag each question in dataset Questions and Behavior with its cluster 
![](https://i.imgur.com/pGB7wxu.png)
## Preparing for recommendation
* Questions for each cluster
1. Use the input User ID(pid) as a key to retrieve unique questions
2. For each question, rate it with a predefined score table
3. Classify each question into the cluster it belongs to
* Get quotas for each cluster
1. Get the distribution of the user's behavior
2. Calculate the quotas for each cluster by the distribution
(The quota is a hyperparameter which you can set urself)
![](https://i.imgur.com/idhwdVm.png)

## Recommend
![](https://i.imgur.com/iwRJo6L.png)
```
recommend=[]
for each cluster:
    k=1
    n=0
    while corresponding quotas !=0:
    
        if all questions are already retrieved:
            k+=1
            n=0

        retrieve nth questions
        recommend.append(kth similar of the questions retrieved)
        n+=1
        corresponding quota-=1
    
```

