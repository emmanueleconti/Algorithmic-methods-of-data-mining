# Algorithmic-methods-of-data-mining
Handling large data, such as hashing, sorting, graphs, data structures, databases, text mining, clustering, classification, mining of frequent itemsets, graph mining, visualization.

2 Project:

1) Search engine for recipes

It has several parts that I had implement. For the linguistic analysis you can use the NLTK Python library.
1. First you need to download the recipes. We will use the recipes at http://www.bbc.co.uk/food/recipes.
You will need to find a way to download all the recipes from the site. You can use any method
you want. It is important to put some time delay between requests; at least 1sec between two
requests. For that you can use the time.sleep command of Python.
2. After you download them you have to preprocess them. For each recipe store all the information (title, who wrote it, preparation time, cooking itme, number of people it serves, dietary
information, ingredients, and method). Note that some fields (e.g., dietary information)
may be missing. Store the final output as a large single tab-separated file. After that, you
can do whatever preprocessing you think is essential (e.g., stopword removal, normalization,
stemming).
3. The next step is to build a search-engine index. First, you need to build an inverted index,
and store it in a file. Build an index that allows to perform proximity queries using the
cosine-similarity measure. Then build also a query-processing part, which, given some terms
it will bring the most related recipes. You can use any query-processing way that you prefer,
although the project will be evaluated better if you use the algorithm with pointers that we
covered in class.
4. Extra credit: Use your imagination to think of features you would like such a service to
have. For example, you may want to weigh different the ingredients based on the quantity.
You may want to try to find methods that take care of ingredients that are written in different
ways, refering though to the same thing. You may want to give different weights to the title–
ingredients–method. You may want to provide a query that satisfies some people, such as,vegetarians, lactose intolerant, and so on. Other ideas might be on the presentation of the
results. Or you can find photos from google images with final food, and so on.

2) Recommender system for movies

As a dataset we will use the book-crossing dataset, available at http://www2.informatik.uni-freiburg.de/~cziegler/BX/.
In class we have said that there exist multiple ways for peforming recommendations and what
we have seen is just a the very basics. Therefore, when trying to choose what techniques to use
in practice, there exists a long process for designing and testing the different approaches that we
consider.
As with most supervised-learning tasks, we split the dataset into a training set (usulally around
80–90% of the data) and to a test set. You train your method (i.e., you learn the various parameters)
using only the training set, and then you use the test set to evaluated it. This allows you to compare
different approaches on data that they have not seen. One way to measure the performance of an
approach is by computing the RMSE error (see, for example, Section 9.4 in the ZAL book, or
Section 9.4 in the LRU book).
To obtain a higher confidence in the result we try to remove the dependence on the particular
splitting by performing k-fold cross validation. There are different ways to do it, here is a simple
one. Assume that we decide to use 80% of the data as training set. Then we partition the dataset
into five equal groups. Then five times we take one of the groups, we use it as a test set, and the
other four ones as a training set. We compute the RMSE error for the different approaches and at
the end we take the average over the five independent runs.
The goal is to implement different recommender systems for books. The first part will be
offline. Implement at least one of the recommender systems in the LRU book. Then perform cross
validation and report the error of your approach(es). For the splitting of data into training and
test set, use a 20% test set, that is, 20% of user–book pairs.
Next, consider an online recommender system. Build a system that accepts some books (as a
list of ISBNs in a file, one ISBN per line) and returns some recommendations to the user. Present
the recommendations that you performed. During the exam you have to demonstrate the online
version of your system.
What we describe above is the very least you should do and on purpose we have left the project
open ended. There is no technique that is better or worse for everything, so try to do your best.There are several things you can do for a better grade. Some ideas:
• Implement and compare different approaches for recommendations, especially if they are of
different type.
• Try to find some way to use content information from Amazon and use it in your recommendation.
• Be more intelligent when reading books. For example, allow the input file to give the title
and/or author of the book, find some potential matches and let the user choose which one.
