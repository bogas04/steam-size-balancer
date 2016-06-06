# Steam Size Balancer

So the main requirements are
1. Moving game files from 1 partition to another
2. Calculating ideal distribution of games from library in each
partition based on size

To do this you will need to adhere to following parameters:

Steam games are usually located in `*/SteamApps/common` directory though
some may be located in other subdirectories of 'SteamApps'

Each game has a unique.acf file also located in `*/SteamApps` which is
usually in the form of a number that is the Steam app id of the game.

This will need to be either stored in a local database or fetched from
an online database like Steamdb.com for each game.

Moving a game from one directory to another involves moving both the
.acf file and the folder containing the game data to the corresponding
directories on the other partition.

To calculate ideal distribution, you will need to tally the total file
sizes of all games and their.acf files and fit them in the partition.

Consider existing files and free space while calculating this
distribution. It should also take into account existing games on the
partition and move them to other partitions if ideal.

The distribution should also maintain free space equal to 1.1 times
the size of the largest game on that partition as this may be needed
to download updates.

That's about it I think.
