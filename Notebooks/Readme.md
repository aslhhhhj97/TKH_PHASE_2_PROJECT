Note the dataset is (https://drive.google.com/file/d/1udzVidq-uKp-muCJ0ZReHJ5mjCafesuE/view?usp=sharing)
Please note that my main appraoch is identified trends among the data and created new feature(boolean) which is different than typical ML method. 
During the cleaning stage, remove several numerical features tha contains large range of data.
My model was near perfect(SimpleData), so I did a test run on Model-RandomForestTest without changes to all the numerical data, only simply removed step, ids, isflagged.
I ran the data again with RandomForest in SimppleData_2, with only removing the features that are not numerical, step, and ifFlagged. To surprise, the DecisionTree model performed better than RandomForest.
I then created couple features base on the amount to orignal dest/origin ratio, and also the frequency of Dest Id. !!! To my surprise, I thought my SimpleData model was good, but the featured model in SimpleData_2 was better. The RandomForestFeature model have 4 false negative and 1 false postive, among 1.25+Million Transactions. (Note I ran the model with binned those feature into 10 bins, the models didn't have any improvement as compare to the baseline.) 

Model	Precision	Recall	F1
0	Decision Tree (Original)	0.912609	0.902469	0.907511
1	Random Forest (Original)	0.966012	0.789506	0.868886
2	Decision Tree (Feature)	0.995137	0.996348	0.995742
3	Random Forest (Feature)	0.999390	0.997565	0.998477 