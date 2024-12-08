---
layout: post
title: "Unique Values With pandas"
categories: pandas
tags: python pandas dataset
---

Here is a cool trick. Given a large data set, you may want to find out how often each object occurs. This is how you do it:

```
import pandas as pd

data = {'stocks': ['apple', 'microsoft', 'microsoft', 'apple', 'amazon', 'apple', 'apple', 'facebook', 'amazon']}
df = pd.DataFrame(data)

counts = df['stocks'].value_counts()
print(counts)
```

You should see this:

```
apple        4
microsoft    2
amazon       2
facebook     1
Name: stocks, dtype: int64
```

Pandas is amazing.
