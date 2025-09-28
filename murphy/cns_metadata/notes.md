# cns metadata — cat murphy, sept. 27

## **story #1: "Fairness, mental health are concerns in debate over transgender women in competitive sports"** 

*url:* https://cnsmaryland.org/2022/06/23/povich-poll-transgender-women/

### **my analysis**

*people:* `Kathy Szeliga, Republican Maryland House Delegate`, `Phillip Westry, legal director at Free State Justice`, `Lee Blinder, executive director at Trans Maryland`

*organizations/insitutions:* `Shirley Povich Center for Sports Journalism`, `Federation Internationale de Natation`, `Center for Democracy and Civic Engagement`

*locations:* `United States`, `Maryland`

*topics:* `Sports`, `LGBTQ+ rights`, `Mental health`

*story type:* `Analysis`

*impact rating:* `3`

### **groq command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2022/06/23/povich-poll-transgender-women/ -of=text | uv run llm -m groq/moonshotai/kimi-k2-instruct-0905 "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **groq's response**

```
{
  "url": "the url of the story",
  "people": [
    "Phillip Westry, legal director at Free State Justice",
    "Kathy Szeliga, Maryland House Delegate",
    "Lee Blinder, executive director at Trans Maryland"
  ],
  "organizations": [
    "Free State Justice",
    "FINA (Fédération Internationale de Natation)",
    "Shirley Povich Center for Sports Journalism",
    "University of Maryland Center for Democracy and Civic Engagement",
    "The Washington Post",
    "Trans Maryland",
    "Fox News"
  ],
  "locations": ["Maryland", "Baltimore County", "Bladensburg"],
  "topics": ["transgender sports", "fairness debate", "mental health", "youth athletics"],
  "story_type": "feature",
  "impact": 4
}
```

### **claude command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2022/06/23/povich-poll-transgender-women/ -of=text | uv run llm -m claude-4-sonnet "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **claude's response**

```json
{
  "url": "not provided",
  "people": [
    "Phillip Westry - legal director at Free State Justice",
    "Kathy Szeliga - Republican Maryland House Delegate", 
    "Lee Blinder - executive director at Trans Maryland"
  ],
  "organizations": [
    "Free State Justice",
    "Federation Internationale de Natation (FINA)",
    "Shirley Povich Center for Sports Journalism",
    "University of Maryland",
    "The Washington Post",
    "Trans Maryland"
  ],
  "locations": [
    "Maryland",
    "Baltimore County",
    "Bladensburg"
  ],
  "topics": [
    "transgender rights",
    "sports competition",
    "mental health",
    "fairness debate",
    "youth sports"
  ],
  "story_type": "feature",
  "impact": 4
}
```

## **story #2: "Terrapins and Hoyas Rivalry…No More?"**

*url:* https://cnsmaryland.org/2012/02/23/terrapins-and-hoyas-rivalry-no-more/

### **my analysis**

*people:* `Kevin Anderson, athletic director at the University of Maryland`, `John Tillman, head coach of the University of Maryland's men's lacrosse team`, `Dave Urick, head coach of Georgetown University's men's lacrosse team`

*organizations/insitutions:* `University of Maryland`, `Georgetown University`
    
*locations:* `University of Maryland`

*topics:* `Sports`, `Terps`, `University of Maryland Lacrosse`

*story type:* `Other`

*impact rating:* `1`

### **groq command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2012/02/23/terrapins-and-hoyas-rivalry-no-more/ -of=text | uv run llm -m groq/moonshotai/kimi-k2-instruct-0905 "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **groq's response**

```json
{
  "url": "",
  "people": ["Kevin Anderson - Maryland athletic director", "John Tillman - Maryland head coach", "Dave Urick - Georgetown head coach"],
  "organizations": ["Maryland Terrapins", "Georgetown Hoyas", "NCAA"],
  "locations": ["College Park"],
  "topics": ["lacrosse rivalry", "scheduling dispute", "college sports"],
  "story_type": "feature",
  "impact": 2
}
```

### **claude command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2012/02/23/terrapins-and-hoyas-rivalry-no-more/ -of=text | uv run llm -m claude-4-sonnet "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **claude's response**

```json
{
  "url": "not provided",
  "people": [
    "Kevin Anderson - Maryland athletic director",
    "John Tillman - Maryland head lacrosse coach", 
    "Dave Urick - Georgetown head lacrosse coach"
  ],
  "organizations": [
    "University of Maryland",
    "Georgetown University",
    "NCAA",
    "Big East Conference",
    "ACC"
  ],
  "locations": [
    "College Park",
    "Maryland"
  ],
  "topics": [
    "lacrosse rivalry",
    "college sports",
    "scheduling conflict",
    "NCAA tournament",
    "athletic departments"
  ],
  "story_type": "feature",
  "impact": "2"
}
```


## **story #3: "Former Terps Stand Up for Gay Rights Leading Up to Olympics"**

*url:* https://cnsmaryland.org/2013/10/31/athlete-ally/

### **my analysis**

*people:* `Vladimir Putin, president of Russia`, `Hudson Taylor, former All-American wrestler at the University of Maryland`, `Kristi Toliver, WNBA player and former women's basketball player at the University of Maryland`

*organizations/insitutions:* `University of Maryland`, `Olympics`, `Athlete Ally`
    
*locations:* `Russia`, `Sochi`, `Maryland`
    
*topics:* `Sports`, `Olympics`, `LGBTQ+ rights`

*story type:* `Feature`

*impact rating:* `3`

### **groq command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2013/10/31/athlete-ally/ -of=text | uv run llm -m groq/moonshotai/kimi-k2-instruct-0905 "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **groq's response**

```
{
  "url": "the url of the story",
  "people": ["Hudson Taylor – Athlete Ally founder, former UMD All-American wrestler", "Kristi Toliver – WNBA/LA Sparks guard, Athlete Ally Pro Ambassador, former Terp", "Steve Nash – NBA star, Principle 6 campaign signatory"],
  "organizations": ["Athlete Ally", "All Out", "Olympic Committee", "Dynamo Moscow", "University of Maryland", "Los Angeles Sparks"],
  "locations": ["Annapolis", "Russia", "Sochi", "University of Maryland"],
  "topics": ["anti-gay laws", "Olympics", "LGBT rights", "Principle 6", "petition"],
  "story_type": "feature",
  "impact": 3
}
```

### **claude command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2013/10/31/athlete-ally/ -of=text | uv run llm -m claude-4-sonnet "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **claude's response**

```json
{
  "url": "",
  "people": [
    "Hudson Taylor - Athlete Ally founder, former All-American wrestler at Maryland",
    "Kristi Toliver - WNBA star, Los Angeles Sparks player, former Maryland athlete",
    "Vladimir Putin - Russian President"
  ],
  "organizations": [
    "University of Maryland",
    "Athlete Ally", 
    "All Out",
    "Olympic Committee",
    "Los Angeles Sparks",
    "WNBA",
    "Dynamo Moscow"
  ],
  "locations": [
    "Annapolis",
    "Maryland", 
    "Sochi",
    "Russia",
    "Moscow"
  ],
  "topics": [
    "Gay Rights",
    "Olympics", 
    "Sports Advocacy",
    "LGBT Discrimination",
    "International Politics"
  ],
  "story_type": "feature",
  "impact": 3
}
```


## **story #4: "Perfect brackets almost never survive past day one of the NCAA tournament"**

*url:* https://cnsmaryland.org/2017/03/16/perfect-brackets-almost-never-survive-past-day-one-of-the-ncaa-tournament/

### **my analysis**

*people:* `Barack Obama, former U.S. president`

*organizations/insitutions:* `ESPN`, `NCAA`

*locations:* `None`

*topics:* `Sports`, `March Madness`, `Basketball`

*story type:* `Analysis`

*impact rating:* `1`

### **groq command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2017/03/16/perfect-brackets-almost-never-survive-past-day-one-of-the-ncaa-tournament/ -of=text | uv run llm -m groq/moonshotai/kimi-k2-instruct-0905 "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **groq's response**

```
{
  "url": "",
  "people": ["President Obama", "ESPN"],
  "organizations": ["Forbes", "ESPN", "NCAA", "UAB Blazers"],
  "locations": ["College Park, Maryland"],
  "topics": ["March Madness", "brackets", "odds", "tournament"],
  "story_type": "feature",
  "impact": 2
}
```

### **claude command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2017/03/16/perfect-brackets-almost-never-survive-past-day-one-of-the-ncaa-tournament/ -of=text | uv run llm -m claude-4-sonnet "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **claude's response**

```json
{
  "url": "not provided",
  "people": ["President Obama - former U.S. President and basketball prognosticator"],
  "organizations": ["ESPN", "Forbes", "NCAA", "UAB Blazers"],
  "locations": ["College Park", "Maryland"],
  "topics": ["March Madness", "NCAA tournament", "basketball brackets", "college sports", "statistics"],
  "story_type": "feature",
  "impact": 2
}
```





## **story #5: "Women sports journalists face new challenges on and off the field"**

*url:* https://cnsmaryland.org/2018/04/24/women-sports-journalists-face-new-challenges-on-and-off-the-field/

### **my analysis**

*people:* `Lucy Dalglish, dean of Merrill College`, `Rob King, ESPN senior vice president for original content newsgathering and digital media`

*organizations/insitutions:* `Shirley Povich Center for Sports Journalism`, `ESPN`, `University of Maryland`

*locations:* `University of Maryland`, `College Park`

*topics:* `Sports`, `Media`, `Discrimination`

*story type:* ``Feature``

*impact rating:* `2`

### **groq command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2018/04/24/women-sports-journalists-face-new-challenges-on-and-off-the-field/ -of=text | uv run llm -m groq/moonshotai/kimi-k2-instruct-0905 "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **groq's response**

```
{
  "url": "",
  "people": ["Beth Mowins - ESPN sports analyst", "Cheryl Cooky - Purdue University associate professor", "Rob King - ESPN senior vice president"],
  "organizations": ["espnW", "Shirley Povich Center for Sports Journalism", "University of Maryland Philip Merrill College of Journalism", "ESPN", "Purdue University", "Quinnipiac University", "USA TODAY", "Golf Channel"],
  "locations": ["College Park, Maryland", "University of Maryland"],
  "topics": ["women journalists", "sports media", "gender bias", "social media"],
  "story_type": "feature",
  "impact": 3
}
```

### **claude command**

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2018/04/24/women-sports-journalists-face-new-challenges-on-and-off-the-field/ -of=text | uv run llm -m groq/moonshotai/kimi-k2-instruct-0905 "Extract structured metadata from this news story and return as JSON with these exact fields:
{
  \"url\": \"the url of the story\",
  \"people\": [\"list of up to 3 people with their titles/roles\"],
  \"organizations\": [\"government agencies, companies, groups mentioned\"],  
  \"locations\": [\"cities, counties, states, specific places\"],
  \"topics\": [\"3-5 topic tags, max 2 words each\"],
  \"story_type\": \"breaking news, feature, analysis, investigation, other\",
  \"impact\": \"a rating of the story's importance on a scale from 1 to 5, taking into account its impact on people\",
  \"
}"
```

### **claude's response**

```json
{
  "url": "https://www.merrill.umd.edu/news/women-sports-journalists-face-new-challenges-field-and-beyond",
  "people": [
    "Beth Mowins - ESPN sports analyst",
    "Cheryl Cooky - Purdue University associate professor",
    "Molly Solomon - Golf Channel executive producer"
  ],
  "organizations": [
    "espnW",
    "Shirley Povich Center for Sports Journalism",
    "Philip Merrill College of Journalism",
    "ESPN",
    "Purdue University",
    "Quinnipiac University",
    "USA TODAY",
    "Golf Channel"
  ],
  "locations": [
    "College Park, Maryland",
    "University of Maryland"
  ],
  "topics": [
    "women journalists",
    "sports media",
    "gender bias",
    "social media abuse",
    "coverage gaps"
  ],
  "story_type": "feature",
  "impact": 4
}
```

## my overall analysis

(note that i will suggest improvements/changes in another section)

i’ll say that my analysis and the llms’ analyses had similar *vibes* — that is, the metadata the llms spit out were, overall, relatively in line with what i extracted. in general, the llms pulled out the exact same key people i did. (the only story for which my metadata really differed was the women in sports journalism one, which i kind of get, because the story had a lot of quotes and none of the speakers was obviously more important to the story than the others.) the one thing that was a bit weird on that front was when groq said espn was a person. but the llms were kind of iffy with everything else — they had a general sense of it, sure, but their responses weren’t great. they weren’t even bad, either; they were just … meh. the llms definitely struggled with locations and organizations. it’s not that they didn’t pull them, it’s that they pulled every one, meaning the metadata included unrelated dateline locations, the towns sources were from and institutions that were, at best, tangential to the story. but again, i kind of get that — the prompt didn’t give the llms any real direction on what to include or exclude. like, you told us to pull the top three data points for each category, but we essentially told the llms to pull everything, so it’s not surprising that it didn’t narrow the scope of its output. one thing that kind of shocked me was their inability to pull the urls???? lmao like, girl, it’s in the prompt. both models, and particularly groq, just couldn’t do it. i’d usually get no link, and when i did get a link it was almost always a fake link or a link to a different news publication. honestly don’t even know how to speculate on that one — did it just not understand the prompt? was it because the urls aren’t *part of* the story? (when i went back to reengineer the prompt, i found that it was nearly impossible to get it to consistently spit out the correct link, but i’ll touch on this later.) oh, also, groq’s outputs were always formatted like a json, but 4/5 times it didn’t include backticks? it’s not that it really makes a difference in the grand scheme of things, but the inconsistency was weird. unsurprisingly, the topics they picked lowkey sucked. they were usually relevant, i guess, but there were far too many, and they were usually far too specific — meaning most of them would be completely unusable as tags. but again, we didn’t give the llms parameters here, so, like, this wasn’t a huge shock. i think this is more a matter of prompt engineering than anything else. it was super weird, though, because both groq and claude spit out some of the SAME niche topics, word for word. like, they both pulled “gender bias” and “fairness debate” and “lacrosse rivalry” — i mean, those are SO specific. i also don’t really know how to explain that. if they’re coming to the exact same conclusions, i have to imagine it probably has something to do with how their prediction processes work, but idrk. what i found really interesting was how the models determined story types and assigned impact ratings. first of all, both groq and claude called every story a feature. i only called two of them features. and i’ve looked back at the stories to see if i was mislabeling them, but i really don’t think i was. the two i labeled analysis stories were quite literally founded in data — one was based around poll, one was centered around espn bracket data. they just weren’t features. the one i’ll say i’m admittedly iffy about is the lacrosse one. i categorized it as “other” because it really doesn’t fit anywhere else — and i’m not totally confident in that answer. but that being said, it DEFINITELY wasn’t a feature. it was about the ongoing fight between maryland and georgetown over basketball scheduling. i’m open to calling it  an analysis given how the story is structured, but it’s not a feature article. oh, and then there was how the llms rated each article’s importance. they consistently assigned higher impact ratings than i did — never by more than a point, but that’s still a 20% difference. granted, i admit that my ratings were conservative. like, listen, i LOVE sports. i love watching sports and i love reading about sports and i love writing about sports. but in general, i don’t typically consider stories about sports, *relative to most other stories*, exceedingly important. there are exceptions, of course, but i completely disagree with claude’s assessment that the story on the gender equity in sports journalism was a 4 out of 5 in terms of importance. and again, this is a topic i care deeply about. but relative to stories about corruption and racism and war and so on, i don’t think it’s particularly impactful. to be fair, though, i’m also analyzing the story’s importance in the context of CNS’ audience — context that neither groq nor claude has, because we didn’t provide it. 

well, aside from the quality issues, if i were running this on 50 or 500 stories, i’d worry about a couple things. first, token limits: i genuinely don’t know if it could go through that many all at once. could it? because, based on my experience with trying to analyze webpages from the command line, i definitely feel like it would hit the token limit and/or just crash if you tried to do this in batches. another thing i’d worry about would be memory. i might be wrong about this, idk, but it occurred to me that if you ran the equivalent of a for loop on dozens or hundreds of stories at once, i’d worry about the quality of the outputs. remember the counting tokens and adding context assignment? (i mean, i assume so, considering you assigned and graded it, but anyway) with that assignment, the more information you shoved into its context window, the more degraded its outputs were. and yes, that speaks somewhat to my first point, but that wasn’t even the only problem there — redundancy was too. i mean, redundancy just kind of confused the LLM. so in situation like this, where the stories are about generally the same topic, i would worry about running them all through at once because i’m concerned the model would get “stuck,” so to speak: i mean, i’ll just paste what i wrote then:
    
    “Like, for the beat books, I feel like a lot of what we’re going to be feeding it is going to be at least somewhat redundant and repetitive. I mean, I looked back at the News-Post articles we read the other day because I remembered that one phrase — “overlay zones add to or modify the regulations attached to a parcel’s underlying zone without changing the underlying zone” — appeared verbatim four times. What about with more documents? They’ll all be from the same newspaper, from the same writers, about the same people and topics and locations — I could go on.”

damn. i kinda cooked with that analysis. anyway, in a journalistic context, i’d also be concerned about, like, quality assurance? i mean, when you’re only looking at one story, you can fact-check the response and, if necessary, tweak the prompt. but if you were to do this in batches, manually factchecking each output becomes kind of impossible. that inability to verify the quality of each output is particularly worrisome given my previous point about the impact of redundancy on quality.

before i delve any deeper, i’d like to note that it took three hours and all three of my degenerate brain cells to reengineer a prompt that spat out consistently good outputs. like i took a nap between writing that and writing this because all that thinking that fried my tiny hamster brain. ok, but as i expected, getting even a mildly consistent output requires explicit prompting and a shit ton of fine-tuning — meaning the prompt had to be maddeningly long. i probably ran and reran some version of that prompt 40-50 times, tweaking it slightly each time, to get to the version i finally settled on. even then, it spits out a slightly different output every time — and like 80% of the time i run it, it’s fine, but every fifth time or so something’s wrong with us. if i were smarter and more committed i could probably get it to run better lol. but in general i’m ok with this prompt’s outputs — it still spits out a few slightly “off” focus categories, like “fairness” instead of “equality” and “transgender” instead of “transgender rights.” this pissed me off to no end because my hamster brain just couldn’t figure out how to get it to stop doing that. but after endless prompt tweaking, most of the metadata it pulled on people, organizations and locations were relatively on target, the story topics were ok, the story types were accurate, and the impact ratings were somewhat more consistent. the story type part was INFURIATING — i had such a hard time getting it to stop categorizing sports stories as news or features. explaining what they were helped, but the semi-solution was telling it that the “sports” tag — which i added because sports are typically categorized separately — always took precedence (and even then, it still sometimes gets this wrong). it took me a while to get it to chill out with the impact ratings, but it finally got its head out of its ass when i told it to consider “how newsworthy the story is, how niche the story is and, above all else, how much the story impacts the lives of most marylanders.” telling it to pull the cnsmaryland.org link helped, but sometimes it still makes up a link or picks one at random. (to be fair, claude’s responses were typically slightly better than groq’s when i ran the original prompt, but i only ran my reengineered prompt through groq.) but overall i’ve only gotten it to give me the correct link, useable tag categories and an accurate impact rating like … once. so yeah, tldr; i spent a shit ton of my saturday writing a 500-word, 677-token prompt that i still wasn’t smart enough to make work lmao. with that, i literally don’t know how you could possibly write a prompt that would make the outputs more consistent. the only things i can think of would i guess be even MORE context? or more examples? i tried providing examples in my reengineered prompt at one point, but it didn’t really help — but i also probably wasn’t doing it right, so maybe if it was done correctly? i’m particularly interested in nailing down the story topics and story types, though. because ultimately, those outputs would be really well suited for to grouping and, presumably, analyzing stories. so thinking in the context of the beat books, i would really want this to work consistently. my story type prompt kinda works, but i think it needs even more explicit instructions and examples. one thing i was thinking of as far as story topics, though, was a “tag bank” of some sort. with the story types, it admittedly did well with sticking to the predefined output options. it would be a huge PITA, but i wonder if for the best books we could somehow create a bank of acceptable tags — specific to the frederick news-post’s content — so that there were clear parameters for what tags it could assign, and we would (hopefully) stop getting unusable words and phrases.

ok, now for what i would do differently. first, i’ve said this over and over again — and so have you lol — but the llm needs very specific instructions. just saying “extract metadata” is so vague. even the directions you gave us were more explicit. to get the llm to do what you want, it needs clear instructions, defined parameters, context and potentially even examples. so, with that, i think the prompt should look more like this:

### **reengineered prompt** (*derek this took FOREVER and it still sucks*)

```{bash}
uv run python -m newspaper --url=https://cnsmaryland.org/2022/06/23/povich-poll-transgender-women/ -of=text | uv run llm -m groq/moonshotai/kimi-k2-instruct-0905 "This story was published by a Maryland-based publication that covers news related to the state of Maryland for a Maryland audience. The news publication needs to extract metadata from the article that will allow it to properly tag the story on its website based on the key figures, key organizations and key locations mentioned in the story, as well as the main focus of the story and the story type. Extract structured metadata from this story and return JSON with these exact fields:
{
  \"web_link\": [\"provide the url to the story on cnsmaryland.com\"],
  \"people\": [\"list at most three key figures mentioned in the story, including their titles. look for the people who are central to the story, focusing on high-profile people such as public officials, community activists and organizers. exclude people who are cited in the story but are not critical to the narrative.\"],
  \"organizations\": [\"list at most three organizations, institutions, agencies, groups or companies mentioned in the text, focusing solely on entities that are both central to the narrative and relevant specifically to a maryland audience.\"],  
  \"locations\": [\"locations relevant to the story, such as cities, states, countries or specific places where an event occurs. only include locations that are relevant to the story, excluding places such as where a source is from or a dateline location that is unrelated to where the story takes place.\"],
  \"focus\": [\"list five umbrella categories that describe the main focus of the story, using one word for each if possible and a maximum of two words if necessary. use only terms that could be used as tags to categorize stories on a website, remembering that news consumers search primarily for broad categories like news, politics or sports, and typically not for specific or niche terms. only include topics that are nationally relevant or relevant to marylanders. each output should be simple enough that an average tenth-grader might research it for a school project, and broad enough that a general news publication in maryland would publish at least 10 stories annually that would fall under that category.\"],
  \"story_type\": [\"categorize the story as breaking news, sports, analysis, feature, or investigation. breaking news stories cover actively unfolding events, excluding stories about sports. sports stories are ones that focus on sports in any capacity, and this category always takes precedence over others. feature stories profile or cover the actions of one specific person, group or entity. analysis stories are founded in and revolve around data. investigations use data and documents to uncover original and revelatory findings. if the article fits into more than one of those categories, list the main two. if the article doesn’t clearly fit into any of these categories, put other.\"],
  \"impact\": [\"the story’s importance on a scale from 1-5. base your rating on how impactful the story is, making sure to take into consideration how newsworthy the story is, how niche the story is and, above all else, how much the story impacts the lives of most marylanders.\"],
  \"
}"
```

### groq's response
```json
{
  "web_link": ["https://cnsmaryland.com/2022/06/27/fairness-mental-health-are-concerns-in-debate-over-transgender-women-in-competitive-sports"],
  "people": ["Phillip Westry – legal director, Free State Maryland", "Kathy Szeliga – Maryland House Delegate (R)", "Lee Blinder – executive director, Trans Maryland"],
  "organizations": ["Free State Justice", "Trans Maryland", "Shirley Povich Center for Sports Journalism (UMD)"],
  "locations": ["Maryland"],
  "focus": ["transgender rights", "high school sports", "mental health", "fairness", "politics"],
  "story_type": ["sports", "analysis"],
  "impact": 3
}
```

before i delve any deeper, i’d like to note that it took three hours and all three of my degenerate brain cells to reengineer a prompt that spat out consistently good outputs. like i took a nap between writing that and writing this because all that thinking that fried my tiny hamster brain. 

ok, but as i expected, getting even a mildly consistent output requires explicit prompting and a shit ton of fine-tuning — meaning the prompt had to be maddeningly long. i probably ran and reran some version of that prompt 40-50 times, tweaking it slightly each time, to get to the version i finally settled on. even then, it spits out a slightly different output every time — and like 80% of the time i run it, it’s fine, but every fifth time or so something’s wrong with us. if i were smarter and more committed i could probably get it to run better lol. but in general i’m ok with this prompt’s outputs — it still spits out a few slightly “off” focus categories, like “fairness” instead of “equality” and “transgender” instead of “transgender rights.” this pissed me off to no end because my hamster brain just couldn’t figure out how to get it to stop doing that. but after endless prompt tweaking, most of the metadata it pulled on people, organizations and locations were relatively on target, the story topics were ok, the story types were accurate, and the impact ratings were somewhat more consistent. the story type part was INFURIATING — i had such a hard time getting it to stop categorizing sports stories as news or features. explaining what they were helped, but the semi-solution was telling it that the “sports” tag — which i added because sports are typically categorized separately — always took precedence (and even then, it still sometimes gets this wrong). it took me a while to get it to chill out with the impact ratings, but it finally got its head out of its ass when i told it to consider “how newsworthy the story is, how niche the story is and, above all else, how much the story impacts the lives of most marylanders.” telling it to pull the cnsmaryland.org link helped, but sometimes it still makes up a link or picks one at random. (to be fair, claude’s responses were typically slightly better than groq’s when i ran the original prompt, but i only ran my reengineered prompt through groq.) but overall i’ve only gotten it to give me the correct link, useable tag categories and an accurate impact rating like … once. so yeah, tldr; i spent a shit ton of my saturday writing a 500-word, 677-token prompt that i still wasn’t smart enough to make work lmao. with that, i literally don’t know how you could possibly write a prompt that would make the outputs more consistent. the only things i can think of would i guess be even MORE context? or more examples? i tried providing examples in my reengineered prompt at one point, but it didn’t really help — but i also probably wasn’t doing it right, so maybe if it was done correctly? i’m particularly interested in nailing down the story topics and story types, though. because ultimately, those outputs would be really well suited for to grouping and, presumably, analyzing stories. so thinking in the context of the beat books, i would really want this to work consistently. my story type prompt kinda works, but i think it needs even more explicit instructions and examples. one thing i was thinking of as far as story topics, though, was a “tag bank” of some sort. with the story types, it admittedly did well with sticking to the predefined output options. it would be a huge PITA, but i wonder if for the best books we could somehow create a bank of acceptable tags — specific to the frederick news-post’s content — so that there were clear parameters for what tags it could assign, and we would (hopefully) stop getting unusable words and phrases.

as to your final question, i’m going to be honest — not that i ever really filter myself in these analyses, but you know — i had a hard time following along with my own work. reading the standard outputs from the command line is impossible, and i had an especially hard time tracking the prompt changes i was making and comparing the outputs. all the copying and pasting, in particular, was super obnoxious. i mean, in terms of making it easier, it can’t possibly be worse. but what comes to mind is the sqlite database simon willison talks about. (i’m like 95% sure that’s the response you’re going for here, too, lol.) but yeah, i think being able to access a database of inputs and outputs outside of the command line would make this process 1000% easier. and i’m thinking this would be especially helpful in the context of engineering prompts — and particularly as the prompts we’re using get longer and more complex. i mean, you can’t edit prompts from the command line like you can in a markdown file, right? so you have to have a markdown file open to write and edit the prompt and then copy and paste it into the command line, but tracking changes in that document requires copying and pasting every single thing. if all of that were kept in a separate database, you could just continue editing a single prompt and reference the database to track changes rather than doing it manually.

ok bye

-cat