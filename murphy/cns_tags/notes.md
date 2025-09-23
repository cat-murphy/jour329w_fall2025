# cns tags — cat murphy, sept. 22

**describe what the data is and how it's organized:** the data contains information about each of the 18,070 story tags on cns's website. it's organized into a .json array with eight keys: the tag's id #, the # of stories categorized under the tag, a description of the tag, the name of the tag, the tag's slug, the taxonomy and the meta description.

**can you tell what the most popular tags are? how would you describe determining which were the most common tags?**

*command* 

```
uv run sqlite-utils memory data/tags.json "select name, count, link from tags order by count desc limit 30"
```
^tells sqlite to go into the `tags.json` file within the `data/` director and pull the data from only the name and count keys and order it in descending order by count, limiting its response to the first 30 datapoints

*response*
```{bash}
[{"name": "Politics", "count": 1172, "link": "https://cnsmaryland.org/tag/politics/"},
 {"name": "maryland", "count": 1127, "link": "https://cnsmaryland.org/tag/maryland/"},
 {"name": "CNS TV", "count": 804, "link": "https://cnsmaryland.org/tag/cns-tv/"},
 {"name": "Capital News Service", "count": 756, "link": "https://cnsmaryland.org/tag/capital-news-service/"},
 {"name": "hero", "count": 728, "link": "https://cnsmaryland.org/tag/hero/"},
 {"name": "cns", "count": 591, "link": "https://cnsmaryland.org/tag/cns/"},
 {"name": "Sports", "count": 494, "link": "https://cnsmaryland.org/tag/sports/"},
 {"name": "cnstv", "count": 375, "link": "https://cnsmaryland.org/tag/cnstv/"},
 {"name": "Baltimore", "count": 371, "link": "https://cnsmaryland.org/tag/baltimore/"},
 {"name": "Donald Trump", "count": 333, "link": "https://cnsmaryland.org/tag/donald-trump/"},
 {"name": "annapolis", "count": 329, "link": "https://cnsmaryland.org/tag/annapolis/"},
 {"name": "Maryland Capital News Service", "count": 327, "link": "https://cnsmaryland.org/tag/maryland-capital-news-service/"},
 {"name": "Baltimore", "count": 314, "link": "https://cnsmaryland.org/tag/baltimore/"},
 {"name": "cns maryland", "count": 234, "link": "https://cnsmaryland.org/tag/cns-maryland/"},
 {"name": "Larry Hogan", "count": 199, "link": "https://cnsmaryland.org/tag/larry-hogan/"},
 {"name": "Chris Van Hollen", "count": 193, "link": "https://cnsmaryland.org/tag/chris-van-hollen/"},
 {"name": "education", "count": 183, "link": "https://cnsmaryland.org/tag/education/"},
 {"name": "Ben Cardin", "count": 182, "link": "https://cnsmaryland.org/tag/ben-cardin/"},
 {"name": "Maryland Newsline", "count": 179, "link": "https://cnsmaryland.org/tag/maryland-newsline/"},
 {"name": "Congress", "count": 172, "link": "https://cnsmaryland.org/tag/congress/"},
 {"name": "Gov. Martin O'Malley", "count": 142, "link": "https://cnsmaryland.org/tag/gov-martin-omalley/"},
 {"name": "Prince George's County", "count": 138, "link": "https://cnsmaryland.org/tag/prince-georges-county/"},
 {"name": "Montgomery County", "count": 136, "link": "https://cnsmaryland.org/tag/montgomery-county/"},
 {"name": "health", "count": 116, "link": "https://cnsmaryland.org/tag/health/"},
 {"name": "Maryland General Assembly", "count": 115, "link": "https://cnsmaryland.org/tag/maryland-general-assembly/"},
 {"name": "Steny Hoyer", "count": 112, "link": "https://cnsmaryland.org/tag/steny-hoyer/"},
 {"name": "Chesapeake Bay", "count": 111, "link": "https://cnsmaryland.org/tag/chesapeake-bay/"},
 {"name": "environment", "count": 110, "link": "https://cnsmaryland.org/tag/environment/"},
 {"name": "Barack Obama", "count": 108, "link": "https://cnsmaryland.org/tag/barack-obama/"},
 {"name": "cnsmaryland", "count": 104, "link": "https://cnsmaryland.org/tag/cnsmaryland/"}]
 ```

*command*

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2024/04/23/maryland-colleges-have-produced-over-300-nfl-draft-picks/ -of=text | llm -m groq/moonshotai/kimi-k2-instruct-0905 "Read the text and provide no more than 5 topics."
```

*note that it took me a while to get this working because some packages weren't installed and i didn't understand the error messages, so i had to use chatgpt to help troubleshoot (https://chatgpt.com/share/68d20f06-6338-800c-aa01-b5de87e3cd04). just wanted to let you know lol*

*response:*
```{bash}
1. Maryland colleges’ overall NFL Draft output (319 picks since 1936, 70% from UMD).  
2. Historical draft range: Randy White (No. 2, 1975) to Joe Cowan (No. 441, 1969).  
3. Career longevity: 66-game average, 215 played, Carl Hairston’s record 224 games.  
4. Active pros: 17 on rosters, Stefon Diggs the standout.  
5. Hall-of-Fame heritage: 7 inductees—2 Terrapins, 1 Midshipman, 4 from Morgan State.
```

*evaluation:*



*command:*

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2024/04/23/maryland-colleges-have-produced-over-300-nfl-draft-picks/ -of=text | llm -m groq/moonshotai/kimi-k2-instruct-0905 "Read the text and provide."
```


*response:*

*evaluation:*

*command:*

*response:*

*evaluation:*

*command:*

*response:*