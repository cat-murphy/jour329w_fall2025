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

ok. i mean, this is just your starting prompt. considering we’re trying to get to get to maximum two-word responses, this isn’t super helpful. to be fair, we didn’t tell it we wanted that. also, this isn’t so much a list of “topics” as it is an outline of the story with a bunch of summary statistics. and one — “Career longevity: 66-game average, 215 played, Carl Hairston’s record 224 games” — is nonsensical. like, putting “215 played” in the middle there makes no sense. so, yeah, flop all around. but again, we didn’t really give it much to go on. moving on.

*command:*

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2024/04/23/maryland-colleges-have-produced-over-300-nfl-draft-picks/ -of=text | llm -m groq/moonshotai/kimi-k2-instruct-0905 "Analyze the text and briefly describe five overall themes."
```

*response:*

```
Five overarching themes:

1. Terrapin dominance – Maryland’s flagship university has supplied 70 % of all NFL Draft picks from in-state schools.

2. Historical depth, modest present – 319 all-time selections, but only a handful of late-round hopefuls in 2024.

3. Rounds & longevity – Draft structure changes explain why 91 past picks would go undrafted today, yet those who make it average 66 career games.

4. Star power – From Randy White (No. 2 overall, 1975) to Stefon Diggs, Maryland colleges have produced both a top pick and today’s most productive active alumnus.

5. Hall-of-Fame rate – 7 of 319 picks (≈2 %) are enshrined in Canton, with Morgan State punching above its weight (3 enshrinees from 36 picks).
```

*evaluation:*

jesus. why was this SO long. i said “briefly,” groq. i really didn’t change the prompt very much, but somehow this was basically a LONGER version of the first response — it just used dashes instead of colons and full sentences instead of phrases. but the topics it decided to spotlight are still … strange. for example, “Draft structure changes explain why 91 past picks would go undrafted today, yet those who make it average 66 career games.” just … what? those two things don’t go together, and the structure bit is lowkey irrelevant — at the very least not an overarching theme. i’m a little annoyed that groq started to veer into editorializing territory with stuff like “punching above its weight.” my fave line, though, is “Maryland colleges have produced both a top pick and today’s most productive active alumnus.” great point, groq — the best active maryland alum IS a maryland alum. overall, this is a mess. but that’s not surprising given that the new prompt still gave groq very little context. lol. next.

*command:*

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2024/04/23/maryland-colleges-have-produced-over-300-nfl-draft-picks/ -of=text | llm -m groq/moonshotai/kimi-k2-instruct-0905 "Analyze the text and provide a list of five brief phrases that describe the overall themes of the story."
```

*response:*

```
1. Terrapins dominate Maryland’s NFL pipeline  
2. Small-state, deep-history draft legacy  
3. Late-round gems and Hall-of-Fame long shots  
4. Active pros carry Maryland’s current NFL presence  
5. Draft format changes reshape selection odds
```

*evaluation:*

alright, i mean, hey, at least we’re moving (slowly) in the right direction length-wise. i’ve only made little changes to the prompt so far because i was trying to see where they got me — basically, just to see how it acted. but it’s clear i’m going to need to give it incredibly granular instructions. because … um … groq, what are we doing, bud? first, “small-state”?? maryland is no. 18 for population, meaning we’re literally in the middle. also, there are more people in maryland than in wisconsin or colorado — neither of which anyone would call small. oh, and then there’s “Late-round gems and Hall-of-Fame long shots.” i don’t even know what that means. i think it’s pulling those from the bit about the 91 people who wouldn’t make the draft today and the “Roughly one in 45” statistic, but still. and then groq goes on about the draft structure — again, really not important here. but still, nothing is better than “Active pros carry Maryland’s current NFL presence.” wow, groq, making that connection must have made some real deep learning. so, while we’re doing slightly better on length, the nonsense and the editorializing are still dominating the output.

*command:*

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2024/04/23/maryland-colleges-have-produced-over-300-nfl-draft-picks/ -of=text | llm -m groq/moonshotai/kimi-k2-instruct-0905 "Analyze the text and spit out a list of words or very brief phrases (maximum two-word) that describe categories the story could fall under."
```

*response:*

```
NFL Draft  
Maryland colleges  
Terrapins legacy  
Draft history  
Hall of Fame  
Active players  
Career longevity  
State prospects
```

*evaluation:*

aye! we’re getting somewhere! first, the length. lol, i did forget to tell it to keep it to five. that’s my bad — god knows that, unless specifically told not to, llms take every opportunity to run their mouths. quantity over quality, like we talked about. BUT! we’re in the ballpark with this output. like i suspected, it’s doing better with more detailed instructions — i mean, it can’t work with what you don’t give it, right? i think it’s funny, though, that i tell it “words or very brief phrases (maximum two-word)” and every single one has two words. probably because i didn’t specify that it should favor one-word responses — i’ll add it to the next prompt. relevance wise, these tags are pretty good. but there’s something missing: context. like, “NFL Draft” and “Maryland colleges” are OK. but things like “Career longevity” and “Draft history” don’t quite make sense in the context of CNS. even “Maryland colleges” is like, ok, you don’t really need the “Maryland.” except … how would it know that? my prompt didn’t give groq any information on what these categories are for or how it should select them. with that being said … next.

*command:*

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2024/04/23/maryland-colleges-have-produced-over-300-nfl-draft-picks/ -of=text | llm -m groq/moonshotai/kimi-k2-instruct-0905 "This article was published by a news organization that covers the state of Maryland. In order to help readers navigate the content on its website, the news organization categorizes each articles using "tags" that describe the subject and focus of the article. Analyze the text of this article and spit out a list of five such "tags" that could be used to categorize the story on a Maryland news website. Each tag should be general enough that readers would search for news on it, but it should also be specific enough that it provides readers with useful context on the article's subject. Each tag must be brief — ideally it should be one word, but it can be a maximum of two words if necessary."
```

*response:*
```
NFL-Draft  
Terrapins  
Maryland-Football  
Draft-History  
Prospects
```
*evaluation:*

well … we’re certainly getting closer. i went wild on the specifics. i was like, “well if i were describing this to a person, what would i say?” like, i did this as a news editor at our paper — how did i explain it to our associate editors? well, they need context. what is a tag? what do they mean? what are they used for? what are they in reference to? how long are they? so i gave it the vibe: this maryland-based news publication categorizes the shit on its website under tags that allow readers to better navigate the website. i specified maryland because it explains  i explained that these cannot be granular i specified not only that they should be 1-2 words but ALSO that one-word tags are preferable. as for the actual content of its responses — well, the dashes are a silly addition, but that’s a simple fix. the topics are generally relevant in our context, but then again “draft history” and “prospects” aren’t necessarily perfect examples of good tagging. im not exactly sure how to fix that, though? and, like, at what point do the time costs of meticulous prompt engineering outweigh the benefits? anyway, i did want to fix the syntax.

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2024/04/23/maryland-colleges-have-produced-over-300-nfl-draft-picks/ -of=text | llm -m groq/moonshotai/kimi-k2-instruct-0905 "This article was published by a news organization that covers the state of Maryland. In order to help readers navigate the content on its website, the news organization categorizes each articles using "tags" that describe the subject and focus of the article. Analyze the text of this article and spit out a list of five such "tags" that could be used to categorize the story on a Maryland news website. Each tag should be general enough that readers would search for news on it, but it should also be specific enough that it provides readers with useful context on the article's subject. Each tag must be brief — ideally it should be one word, but it can be a maximum of two words if necessary. Do not hyphenate words."
```

*response:*

```
1. NFLDraft  
2. MarylandFootball  
3. Terrapins  
4. MorganState  
5. NFLHistory
```

*evaluation:*

oh my f*cking god. “do not hyphenate” did NOT mean “combine strings.” machines are dumb. i’m also not entirely sure why this change, given that it should have only targeted the format of the output, also changed the content of the output?? but, to be fair, im not mad about the changes — groq struck “draft history” and “prospects,” neither of which were particularly relevant in the context of CNS.

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2024/04/23/maryland-colleges-have-produced-over-300-nfl-draft-picks/ -of=text | llm -m groq/moonshotai/kimi-k2-instruct-0905 "This article was published by a news organization that covers the state of Maryland. In order to help readers navigate the content on its website, the news organization categorizes each articles using "tags" that describe the subject and focus of the article. Analyze the text of this article and spit out a list of five such "tags" that could be used to categorize the story on a Maryland news website. Each tag should be general enough that readers would search for news on it, but it should also be specific enough that it provides readers with useful context on the article's subject. Each tag must be brief — ideally it should be one word, but it can be a maximum of two words if necessary. Do not hyphenate words. You can use spaces."
```

*response:*

```
NFL Draft  
Terrapins  
Morgan State  
Navy Football  
Maryland Sports
```

*evaluation:*

ok. honestly, i’m pretty ok with my final output. it’s annoying that the prompt “use one word if possible” led groq to add hyphens between words to avoid technically using two words. and then, when i told it to not hyphenate its output, it just erased the spaces between words, again to make them “one” word, which is super obnoxious. content wise, i also thing my final prompt resulted in the best output. like, “maryland sports” and “nfl draft” and “terrapins” are all pretty good. the one i took issue with was “navy football,” but i then realized that this is smart — like, tagging this “navy” alone would make no sense if it ended up in a category with stories about wars and ships and military actions. i would have liked to see maybe “sports” generally, but i’m overall pretty happy. 

*general evaluation:*

overall, was it easy to think of changes? yes and no. on the one hand, i knew what i needed it to do, so each output showed me what about the prompt i still needed to tweak. one the other hand, it devolved into a game of semantics by the end. like, having to add “do not hyphenate” and “you can use spaces” just slowed everything down — because really, my prompt didn’t change. having to prompt it eight billion times was insanely repetitive, especially given that that’s not how i would use a chatbot, and since many of the outputs then wouldnt change because it had no way of knowing not to do the thing that i was trying to prompt it away from. i think a better workflow would involve using a single chat window from the command line. i think i remember something about a way to do “-c” or something to make it use the previous chat window? this way the LLM would have the context of your previous prompt and you could tweak it as needed without repeating yourself 100 times. if i could design the whole workflow, though, i would make this a tool on the cns website — something that could give automatic tag suggestions for stories. i would also maybe ask for a longer list? that way i have more ideas to think over. i would also want to give the LLM examples of what we’re looking for at CNS specifically — basically, train it on our data so that it better understands the context in which the story is being published and then what tags already exist, which ones should be avoided, which ones tend to do well with readers, etc. basically, i would want it to start with more context — and remember that context — so that i wouldn’t have to continue telling it.