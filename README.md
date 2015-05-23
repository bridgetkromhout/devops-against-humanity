devops-against-humanity
=======================

DevOps Against Humanity (an expansion for [Cards Against Humanity](http://www.cardsagainsthumanity.com))

Because people on twitter are hilarious.

### Card lists

The google doc is here:

[Shared Google Doc](https://docs.google.com/spreadsheets/d/1OKgmjNz8l7skYfrbrOtYT6QmSf_y-BzZOWJWZC3tbUQ/edit#gid=0)

Add your awesome ideas to the shared doc. Then copy it, edit it to your liking, sorting and removing anything you don't like. I ended up going with a standard of five underscores for each blank, since otherwise they can take up too much room on the cards.

I wouldn't be sad if someone wanted to merge in my cleanup/adds/changes to the shared doc, although I don't have time right now. This is the actual doc I used for generating the PDFs in this repo:

[Doc used for first printing](https://docs.google.com/spreadsheets/d/1LEf6qE3FMKRvSWRrKb3m5gcVHmw7aQctbegrWbxEsfA/edit?usp=sharing)

I've added CSVs to this repo preserving the state of the doc used for first printing and an export of the current state of the shared doc (which will be updated intermittently). I've no desire to approve all additions to the shared doc.

### Generating the PDFs

I googled around and found a number of generators, but most made smaller cards than I wanted. Then I found [this thread on boardgamegeek](http://rpggeek.com/thread/1160850/bigger-blacker-cards-another-custom-cah-card-pdf-g)

Either install https://github.com/bbcards/bbcards somewhere yourself, or run it on this site: http://biggerblackercards.com

Because I wanted to use a different custom logo on white cards vs black, I made two PDFs. That turned out to be good since I needed to print the black cards in color for them to look good, while the white ones were fine in black & white. When I wanted only one, I just made sure the other side (black or white) was blank.

I went with the rectangular 2.5"x3.5" poker-sized cards.

### Chromecast
These cards as of 2014-09-01 have been [imported into Cardcast](http://www.cardcastgame.com/browse/deck/HFU3S) for play with a Chromecast. The deck code is `HFU3S`.

### Printing

I put the PDFs on a USB stick and had them printed on 110lb cardstock at Kinko's. Any print shop should be able to do this. Cards Against Humanity ([in their official printing directions](http://www.cardsagainsthumanity.com/pdf/CAH_MainGame.pdf)) suggests going with at least 80lb cardstock. The first time I printed this, cutting ~300 cards on the slicing machine took about 45min because I wanted them to look fairly consistent. I could only stack 4 sheets at a time; at 5, the cuts were no longer clean. The second printing, I had the print shop do the cutting. I recommend that over DIY cutting; much much less hassle and cleaner edges.

Cards Against Humanity also suggests printing plain black on the back of the black cards. I made an all-black page in OpenOffice and exported it to PDF. The print shop interleaved the "front" and "back" of the PDFs for me.

### Accessibility Rules

The "house rule" that I use is that if someone doesn't understand a card, like a card, or think a card is funny, whether it's a black or a white card, they can discard it at any time with no penalty and replace it with a new card. This makes it easier for people from varying technical stacks and differing eras of implementation to all play together and have fun without worrying about having to prove they know some obscure trivia. (How many of us remember the SGI Vulcan death grip? Yeah.)

### Deck Curation (or lack thereof)

I don't have time to produce curated editions. When printing, I do go through and remove anything I don't like, but I have almost no time to curate the open-to-the-public Google spreadsheet. So, no endorsement is implied, and you almost certainly want to take an editorial pass through it before you print it for your conference/event/workplace.

### Test it!

If you'd like an idea of what the combinations of hilarity can look like, check out this script contributed by @nicocesar:

<pre>
#!/usr/bin/env python
import urllib,csv,random,re
u='https://raw.githubusercontent.com/bridgetkromhout/devops-against-humanity/master/cards-DevOpsAgainstHumanity.csv'

white=[]
black=[]
for r in csv.reader(urllib.urlopen(u)):
    if r[0]: white.append(r[0])
    if r[1]: black.append(r[1])

blank=re.compile(r"( +)?(\b|[^_])_+(\b|[^_])( +)?")
rpl=lambda _:" %s " % random.choice(white)
for _ in range(10):
    print(re.sub(blank,rpl,random.choice(black)).strip().replace(' .','.'))
</pre>

### Pull requests accepted!

It would be cool if someone designed awesome card backs for black and white DAH cards. Obviously many more awesome cards could be created. Pull requests aren't necessary for adding cards; you can just edit the spreadsheet. If you want to add anything else to make this more fun, though, I'm happy to check it out.

From the CAH website: "Cards Against Humanity is available under a Creative Commons BY-NC-SA 2.0 license. That means you can use and remix the game for free, but you can’t sell it. Please do not steal our name or we will smash you."

