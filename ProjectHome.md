MDSWISS is a **Java Chess open source swiss pairing engine**
Just use the **jar** **library** and create a client using your favorite technology.

Using it is very easy! Include the jar and
write code like this:
```
int nrRounds = 4;
Tournament tournament = Tournament.createTournament(nrRounds);
int nrPlayers = 7;

for (int i = 1; i < nrPlayers + 1; i++) {
   Player player =      Player.createPlayerWithFirstnameLastname("firstname"+i,"lastname");
   int rating =1500-1;
   result.setRating(rating);
   tournament.addPlayer(player);
}

Round round = tournament.pairNextRound();

//just add some draws as results
for (Pairing pairing : round.pairings) {
      pairing.draw();
}



```



That easy!