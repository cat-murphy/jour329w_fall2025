# cns tag browser — cat murphy, sept. 30

## data exploration

omg these tags are awful. my student newspaper was like this with the insane tags, including my personal favorite: https://quchronicle.com/tag/dontmiss/. but seriously like what is going on here. exploring the data with sqlite shows an insane level of inconsistency — "Donald Trump," "president trump," "President Donald Trump," "Donald J. Trump." i ran the command again with limit 20 and discovered "new trump," "#NewTrump," "DonaldTrump," "president elect donald trump" and "president-elect trump." like. oh my god.

not to mention the fact that there are, for some reason, two tags that, at least from my command line, look identical: "Baltimore" and "Baltimore." i ran the original command again with limit 20, and "Baltimore" is listed twice ... does one have a space or something on the website???

the thing that really gets me is, like, the lack of uniformity. the terrible, random tags aside, the duplicates are killing me. trump is a good example, but there are doubles and triples and quadruples of everything — even "CNS TV," "cnstv," "cns maryland" and "CNS." i did a search for "Ravens" and got "baltimore ravens," "ravens," "former ravens player" and "ravens logo." like oh my goddddddddddddddddddd. there needs to be a tag bank.

## planning

**how i would want to search:** i mean ... i'd want a search bar. but that's only really helpful if i know exactly what i'm looking for, which i might not, ya know? so i would also want to in some way be able to browse by category (caTAGory?).

**what i would want displayed prominently:** well, with there being over 1,000 tags, you can't just have them all ... ya know ... listed or something. i would want the most-used tags displayed most prominently. it would automatically show you the top 10 most-used tags, but you could click a "show more" button to expand the list.

**how i would want the tags sorted:** by popularity. but also, i would want any tags with fewer than, i don't know, five?? articles assigned to it to be automatically excluded from the main dataset. like, you can add them back in, but i want them automatically filtered out. ooh, or you could put in a limit — like, oh i only want to look at tags with more than 50 articles.

**what filters i would want:** i would want to be able to filter (or browse) by categories like:

* maryland
* government & politics
* health & climate
* sports
* culture

this is kind of just a cursory look at what i would want as broad categories, but i would want these to have subdirectories by topic as well — so, like, politics would break into state government, federal government, education, courts. sports by league, level. i think i want a maryland subdirectory for locations and very maryland-specific things, but i'm not sure. just spitballing.

**other features i would want:** i would want a feature where you could paste a headline and it could use ai to suggest tags. i would want every tag listed to be hyperlinked to the cns page. in a crazy world, if copilot could maybe do this, i would want it to pull and list the 10 most recent headlines listed under that tag, and the most recent date it was used. if that were possible (the date thing) i would also want to be able to view *recent* popular tags. like, most used tags over the last month or whatever. but it would need to scrape that lol, so i doubt it.