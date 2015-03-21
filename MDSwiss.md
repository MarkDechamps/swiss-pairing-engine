#Swiss pairing engine.

# Introduction #

This project contains a swiss engine library for pairing a chess tournament and its free to use in your project. It has no front end, it is just the pairing engine. I supports the SonnenbornBerger system.
http://en.wikipedia.org/wiki/Swiss-system_tournament

I've written this project after reading the excellent eye opener 'clean code' from uncle Bob and tried to apply this as much as possible to this project (and want to keep it that way).
Any contributions are welcome (of course unit tested!)!

This is a work in progress, a lot of extensions can be made. I committed this as soon as possible and realize the code is not as clean as it should be (and I wanted it to be). First make it work , then make it better :)

Where to start ? Start in the TestAll.java file


Please, if you change the code, let me know so I can import it into the project.

# Why #
Because it doesn't exist yet. I initially wanted to do a test with javafx. I thought that a swiss engine jar would be there and I could simply download it and start my project but that was not the case (at least no code I wanted to use..).

# Details #
The pairing engine generates all possible pairings, orders them by priority and then takes the first valid one.
Note that the points are multiplied by 10 to avoid floating points. So 1 is 10, and 1,5 is 15 etc. This can be easily hidden if we want to.

A simple example of what the api looks like:
```
@Test
public void testCreateTournament() {
		int nrRounds = 5;
		Tournament tournament = Tournament.createTournament(nrRounds);
		for (int i = 1; i < 10 + 1; i++) {
			Player player = PlayerUtils.createPlayer("P" + i, "", 1100 + i * 100);
			tournament.addPlayer(player);
		}
		Round round = tournament.pairNextRound();
		for (Pairing pairing : round.pairings) {
			System.out.println(pairing);
		}
	}
```

will put on screen:
```
[P10  (2100 (0)(sb:0.0) - P5  (1600 (0)(sb:0.0)]
[P4  (1500 (0)(sb:0.0) - P9  (2000 (0)(sb:0.0)]
[P8  (1900 (0)(sb:0.0) - P3  (1400 (0)(sb:0.0)]
[P2  (1300 (0)(sb:0.0) - P7  (1800 (0)(sb:0.0)]
[P6  (1700 (0)(sb:0.0) - P1  (1200 (0)(sb:0.0)]
```

# Want to help ? #
Contributors are more then welcome!

# License #
You can use this project for free.
  1. I do want to ask you to send me the bugfixes if you make them (with tests).
  1. I also would like to know if you're going to use it in a client (simply because I'm interested to see the usage)
  1. and ask you to put a link to this site in your software/website somewhere.