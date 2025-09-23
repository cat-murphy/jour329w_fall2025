# cns tags — cat murphy, sept. 22

**describe what the data is and how it's organized:** the data contains information about each of the 18,070 story tags on cns's website. it's organized into a .json array with eight keys: the tag's id #, the # of stories categorized under the tag, a description of the tag, the name of the tag, the tag's slug, the taxonomy and the meta description.

**can you tell what the most popular tags are? how would you describe determining which were the most common tags?**

*command* 

```
uv run sqlite-utils memory data/tags.json "select name, count from tags order by count desc limit 30"
```
^tells sqlite to go into the `tags.json` file within the `data/` director and pull the data from only the name and count keys and order it in descending order by count, limiting its response to the first 30 datapoints

*response*
```
[{"name": "Politics", "count": 1172},
 {"name": "maryland", "count": 1127},
 {"name": "CNS TV", "count": 804},
 {"name": "Capital News Service", "count": 756},
 {"name": "hero", "count": 728},
 {"name": "cns", "count": 591},
 {"name": "Sports", "count": 494},
 {"name": "cnstv", "count": 375},
 {"name": "Baltimore", "count": 371},
 {"name": "Donald Trump", "count": 333},
 {"name": "annapolis", "count": 329},
 {"name": "Maryland Capital News Service", "count": 327},
 {"name": "Baltimore", "count": 314},
 {"name": "cns maryland", "count": 234},
 {"name": "Larry Hogan", "count": 199},
 {"name": "Chris Van Hollen", "count": 193},
 {"name": "education", "count": 183},
 {"name": "Ben Cardin", "count": 182},
 {"name": "Maryland Newsline", "count": 179},
 {"name": "Congress", "count": 172},
 {"name": "Gov. Martin O'Malley", "count": 142},
 {"name": "Prince George's County", "count": 138},
 {"name": "Montgomery County", "count": 136},
 {"name": "health", "count": 116},
 {"name": "Maryland General Assembly", "count": 115},
 {"name": "Steny Hoyer", "count": 112},
 {"name": "Chesapeake Bay", "count": 111},
 {"name": "environment", "count": 110},
 {"name": "Barack Obama", "count": 108},
 {"name": "cnsmaryland", "count": 104}
 ```

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2024/04/23/maryland-colleges-have-produced-over-300-nfl-draft-picks/ -of=text | llm -m groq/moonshotai/kimi-k2-instruct-0905 "Read the text and provide no more than 5 topics."
```

** note that it took me a minute to get this working because it needed me to install `lxml_html_clean` first

https://cnsmaryland.org/tag/Sports


