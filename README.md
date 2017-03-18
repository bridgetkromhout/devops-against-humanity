# devops-against-humanity

DevOps Against Humanity (an expansion for [Cards Against Humanity](http://www.cardsagainsthumanity.com))

Because people on twitter are hilarious.

Forked from [Bridget Kromhout](https://github.com/bridgetkromhout/devops-against-humanity)

## Generating the PDFs

```bash
bundle install  # for the dependencies of bbcards
wget https://raw.githubusercontent.com/bbcards/bbcards/master/bbcards.rb
# Generate black cards
./bbcards.rb --large -b black.txt -i devops-brain-black.png -o black.pdf
# Generate white cards
./bbcards.rb --large -b white.txt -i devops-brain-white.png -o white.pdf
```

## Pull requests accepted

It would be cool if someone designed awesome card backs for black and white DAH cards.
Obviously many more awesome cards could be created. Pull requests aren't
necessary for adding cards; you can just edit the spreadsheet. If you want
to add anything else to make this more fun, though, I'm happy to check it out.

From the CAH website: "Cards Against Humanity is available under a Creative Commons
BY-NC-SA 2.0 license. That means you can use and remix the game for free, but you
can’t sell it. Please do not steal our name or we will smash you."

