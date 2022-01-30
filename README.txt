Simple Python Search Spider, Page Ranker

This is a set of programs that emulate some of the functions of a 
search engine.  They store their data in a SQLITE3 database named
'spider1.sqlite'.  This file can be removed at any time to restart the
process.   

This program crawls a web site and pulls a series of pages into the
database, recording the links between pages.

We tell the program to crawl a website and retrieve two 
pages.  If you restart the program again and tell it to crawl more
pages, it will not re-crawl any pages already in the database.  Upon 
restart it goes to a random non-crawled page and starts there.  So 
each successive run of spidering.py is additive.

You can have multiple starting points in the same database - 
within the program these are called "webs".   The spider
chooses randomly amongst all non-visited links across all
the webs.
Once you have a few pages in the database, you can run Page Rank on the
pages using the pagerankalgorithm.py program.  You simply tell it how many Page
Rank iterations to run.
You can run pagerankalgorithm.py as many times as you like and it will simply refine
the page rank the more times you run it.  You can even run pagerankalgorithm.py a few times
and then go spider a few more pages with pagerankalgorithm.py and then run pagerankalgorithm.py
to converge the page ranks.
the resetting ranks.py python file resets the ranks of each page to 1 for each new web crawl

For each iteration of the page rank algorithm it prints the average
change per page of the page rank.The network initially is quite 
unbalanced and so the individual page ranks are changing wildly.
But in a few short iterations, the page rank converges.  You 
should run pagerankalgorithm.py long enough that the page ranks converge.

the idea of pagerank algorithm if you are to look at the links here
page 1 pointing to page 2 and so on goes 
the problem is how much positive effect does page 1 show to page 2 
so we start by giving each page a rank of 1 but then what we do is we divide up
in one iteration of pagerank algorithm we divide up the goodness of a page across its outbound links
accumalate that and that becomes the next rank
one rank is dependent on another