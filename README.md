### AFL Elo Model

The Elo model is a method for calculating the relative ability of competing teams or players. Created by Hungarian-American chess master and physicist Arpad Elo, I have adapted it from chess for AFL. It is useful as a baseline predictor of AFL matches.



Instead of predicating a teams quality based on a ladder or quantity of wins, my model takes into account the quality of opposition. It is a zero-sum system, so the amount of elo Team A loses from a game = the amount of elo Team B gains from winning that game. 



Losing to lesser teams carries a greater penalty to one's team than losing to equal or greater opposition. The home team gains a temporary pre-match Elo of 50, to represent the home ground advantage. Elo somewhat resets from one year to another, retaining 0.67x of their elo at the last point of the previous season, plus ~500. This model has a starting point of the 2012 season, the start of the 18 team era. Therefore anything before that point is irrelevant, as each team assumes an elo of 1500.



Elo is calculated using the following formula:

$$
E\_A = \\frac{1}{1 + 10^{(R\_B - R\_A)/400}}
$$

The model also takes margin of victory into account, with greater wins rewarding the victor with a larger elo increase. This is defined by the following (in this case K = 20):

$$

K \\cdot

\\frac{(\\text{margin} + 1)^{0.8}}

{7.5 + 0.006 \\cdot \\lvert E\_{\\text{home}} - E\_{\\text{away}} \\rvert}

$$



The model creates a ladder for the 2026 season, predicting Brisbane Lions to finish top and go undefeated with 23 wins. This is unsurprising as following their big GF win, their Elo is far larger than any other team.



The shortcomings of this model is the lack of contextual data, i.e. injuries, distance travelled, days since previous match, etc.

