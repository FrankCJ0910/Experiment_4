This experiment is all about data managing and analysis. Therefore both pandas and matplot library will be used
We first import them using the following lines:

``` python
  import pandas as pd
  import matplotlib.pyplot as plt
```

Second, is to load the data that is to be used

``` python
  BoardScores = pd.read_excel('board2.xlsx')
```

For the first problem we can just use .loc() to get the desired outcome

``` python
  Instru = BoardScores.loc[(BoardScores['Electronics']>70)&
                           (BoardScores['Hometown']=='Luzon')&
                           (BoardScores['Track']=='Instrumentation')
                           ,['Name','GEAS','Electronics']]
```

For the second problem, We first make a new column that will be the average of the students grades

``` python
  BoardScores['Average'] = (BoardScores.Math+BoardScores.Electronics+BoardScores.GEAS+BoardScores.Communication)/4
```

Now we can proceed with the .loc() function

``` python
  Mindy = BoardScores.loc[ (BoardScores['Average']>=55)&
                         (BoardScores['Hometown']=='Mindanao')&
                         (BoardScores['Gender']=='Female')
                         ,['Name','Track','Electronics']]
```


For the last problem, we can make graphs using matplot

``` python
  plt.figure(figsize=(5,5))
  plt.bar(BoardScores['Track'],BoardScores['Average'])
```
