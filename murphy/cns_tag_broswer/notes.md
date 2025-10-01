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

## using copilot

i started, off the bat, with this:

```
write code in the index.html file that makes the tags in tags.json searchable and sortable. i want a search bar at the topic, and the main page should display the names of the top 10 most-used tags by count. the names of each tag should be hyperlinked with the cnsmaryland.org link associated with that tag. there should be a button below this called "show more" that when clicked will expand the list to show the next 10 most-used tags. there should also be a "show all" button that will open a popout with a scrollable list to the right. that popout should be sortable by count or alphabetical. there should also be a filter to exclude all tags with a count below five. i also want a directory below that. that directory should make the tags browsable by topic. use the topics in topics.csv to categorize the tags by name. put any that cannot be cleanly categorized under a topic called "miscellaneous." if you aren't sure about where a tag goes, ask. within that directory, each topic category, when clicked, should display a scrollable dropdown menu that displays the top 10 most-used tags under that topic by count. there should then be a "show more" button beneath the top 10 that will, when clicked, display a popout with the entire list of tags.
```

it didn't work ... at all. i got a webpage with all of the features i asked for *in theory*, but the tags weren't visible. i figured my first prompt was too confusing. i added that i wanted it to split up my js and css, and then i told it:

```
none of the tags from tags.json are visible on the webpage. please make sure they're categorized by topic using the topics.csv file for reference.
```

it took forrrrrrreeeeevvvvvvvvvver for it to read the json. i don't really know why it didn't read it before????

and yet, it still didn't work. told it it didn't work — twice. still nothing, so i gave up and started over.

i gentle parented it. i tried over and over. it still didn't work. 

at this point, even though the red sox won, i *started to actually cry* because i'm so stressed out and i've been working on this for hours but i'm apparently too stupid to even get a computer to do something for me.

so i switched models. and it still didn't work. just kept giving me a directory listing that did not include a single tag. 

i copied the transcript into a google doc and closed out the chat. i tried again. it gave me a website that gave me a directory listing and a tags listing, and when you clicked the tag listing, it showed you, like, 10. promising! but i told it that i wanted all of the tags, and its "fix" made none of them visible.

started over and tried again, this time copying the data over to a new folder in a new subdirectory under my cns_tag_browser directory. it FINALLY worked.

but at this point i don't really care that it worked because i have a tension headache from crying, and i feel like a complete moron.

but when i stop caring, i start fucking around. i got it to put everything into a serif font and to display tags in descending order by count, and only show the top 10 by default with a "show more" button. but then:

``` 
can you make it more visually appealing? what suggestions do you have?
```

it gave me a selection of ideas and asked if i wanted it to implement a "modern, elegant style," to which i responded:

```
do what you think is best!
```

looked great, honestly. just a couple things:

```
the search bar is a little too big for the container its in
```
```
can we add some more color? i'm personally a big fan of coral
```

priorities, people, priorities. 

*(it was around this time that i stopped crying and started having fun again. i still don't know why it took my hamster brain this long to get it to work.)*

i also tried to get it to put the maryland flag in the background, but it didn't work and i don't have the capacity to care:

```
hmm, can we go back to just the coral? make it elegant, but fun.
```

ok, now that i've stopped having a complete mental breakdown, i'll go back to doing real work, i guess.

```
i'd like to add another type of search function. i want to be able to browse the tags by topic. i need you to look at the topics in topics.csv and categorize all the tag using those topics. if there are any stragglers, put "miscellaneous"
```

it created a good dropdown menu, but all the menu options returned no results — i.e. nothing was actually categorized. i told it that and it fixed it. then it told me to let it know if i wanted to refine the UI ...

```
what do you think would be helpful for users with the UI?
```

it gave me 10 suggestions, everything from responsive design and keyboard accessibility to highlight search matches and show tag topic in the table. i told it to do all of it lol.

while it cooked on the design front, i went and looked at how it categorized the tags ... and, um. let's just say it categorized "education" under "Animals," "Gov. Martin O'Malley" under "Arts & Culture," and "Donna Edwards" under "Armed Forces and National Security." meanwhile "Politics" was "miscellaneous"

yeah ... so. not so great.

i asked about its categorization and it told me it couldn't get me a list of miscellaneous tags because there were too many. then i asked it to count the miscellaneous ones. that failed. then i asked it to remove the miscellaneous tags, and i had to fix my phrasing, but eventually i got it to recategorize all the miscellaneous ones to the best of its ability ... which wasn't very good. "CNS TV" is Agriculture and Food, apparently. so is "Donald Trump" — and just about every other politician, for that matter. 

i told it to recategorize any CNS ones into their own category, and i told it this:

```
also, Donald Trump is a politician. in fact, almost all of the things you have listed under agriculture and food are people, usually politicians. go back through those and, if its a person's name, think about whether it should be categorized in "Maryland Government and Politics" or "Federal Government and Politics"
```

then all the politicians were categorized as CNS ...

i tried for a while to get it to work, but it wasn't happening. so i gave it my categories instead — and it handled those a lot better. perfect? not even close. it would need a lot more parameters. but better. i tried to get it to fix some of it, but then it coded "Russia" as "Maryland" and "Maryland" as "Sports"

i played around with it some more, but not with much to report back on. kind of got nowhere with that.

but! then i had it add a tag similarity feature. we had some back-and-forth — it kept doing things in the most literal and least effective ways possible. i know, i know, clear prompts. it's late, man. but eventually i landed on another column that has dropdowns for each tag to show the top 5 similar tags. it was a little frustrating how long it took to get this correct and functional, but i eventually did.

i tried to add a filter by count (so, for tags with 100+, 50-99, 10-49, 0-9) but it kept screwing the entire thing up.

next, i used the cns_maryland_posts.json to add a "last six months" category to show how many times each tag has been used in the last six months. this took some serious debugging, but eventually it worked.

then i did this:

```
next, can you add a column that pulls the five most recent headlines (written as title in the cns_maryland_posts.json) and puts them in a dropdown menu for each tag? include the date of the post in (mm/dd/yyyy) format. put it to the right of the topic column.
```

this prompt was specific enough that it worked instantly, which was really cool. 

also did:

```
can you add two more columns to the right of last six months that say the date of the first time that tag was used and the most recent time it was used in (mm/dd/yyyy) format
```

also worked immediately, which was doubly cool considering how few brain cells i have.

it didn't really work the way i intended it to because of the limitations of that data set. thats ok, though. still cool that it could do it.

## thoughts