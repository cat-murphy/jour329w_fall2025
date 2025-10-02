# cns datasette analysis — cat murphy, oct. 1

### what was the most interesting thing you saw doing this?

well, just from poking around a little bit, i thought it was interesting that there were SO MANY stories tagged “trump” (or related) but relatively few tagged “obama.” i know that’s his presidency obviously started earlier, and so the tagging methodology was likely different, if it existed at all. but his presidency DID go until 2017, so i would expect more than i found. meanwhile, trump has been in the public eye — at least politically — since 2015, but he also maintained that spotlight even when he wasn’t president. i think it’s just interesting because that supports all the points about the relationship between media coverage and trump’s omnipresence. 

### what was the most useful thing you saw doing this?

oh god, its ability to automatically interpret the .json array and allow you to sort by tag. that’s crazy. i said this in class, but r could never. that would an entire production in r. in r, this would require gsub() to remove the formatting and some str_split() to new columns. then, you’d still have to filter() or str_detect to find something — it’s not like any of that would make searching the data all that much easier. and it’s not like this is a particularly rare issue — i run into data all the time where there are multiple datapoints contained in the same cell. (most recent example is ntsb data, which lists all recommendation recipients in the same cell, separated i think by semicolons.) so the fact that datasette can read and sort something like a .json array is incredibly helpful. (and in the case of the ntsb data, i think a great use case for ai would be reformatting that column into .json arrays so that datasette could more easily read it.)

### how useful was datasette for this kind of analysis?

the thing that struck me about datasette was the way it handles large datasets with both character and double fields. i mean, datasette’s search and sort functions are incredibly powerful, at the very least in terms of ease of use. but it’s also just useful in the sense that it’s not a visual nightmare. it formats it for you — rows are the right size, no overflowing text, columns are automatically sortable, etc. — meaning you can actually see what you’re looking at. and from there you can search and sort without using str_detect() or a shitty google sheets filter.

### what would you use this tool for in a newsroom?

the biggest thing is sharing datasets. i have to write csvs and import them into sheets all the time. because when i’m working on a story with multiple people, and i’m responsible for part of the data work, other people need to be able to see it — but i don’t want to work in sheets and i don’t want to send people .rmds, you know? 

### how does this compare to analyzing data in other tools?

so, for example, with ntsb data. that data has a bunch of character fields, a bunch of double fields, and a bunch of rows. and honestly, looking at it in r isn’t always super convenient, either, but it’s manageable. but putting it in a spreadsheet isn’t convenient — for anyone. r makes the analysis part bearable, and sheets makes it easier to click around. ok, well, datasette appears to do both pretty well. and obviously there are still uses for r and sheets. but i think being able to conduct analysis while ALSO being able to poke around — without writing code — is extremely useful. i mean, even though i certainly can write r code to group_by() and summarise(), there’s a lot of value in just being able to toggle around with filters and search functions. i kind of think, in a lot of ways, datasette seems to offer the best of both worlds in terms of allowing for easy analysis and easy access.

