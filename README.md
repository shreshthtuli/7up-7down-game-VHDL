# 7up-7down-game-VHDL
Developed on Vivado software suite for Basys 3 FPGA evaluation board. This project was done under the COL215 (Digital Logic and system design) course at IIT Delhi.<br /><br />
The purpose of the project is to execute a 7/up 7/down game. It involves two players, bidding an amount from their purses and guessing whether the sum of the number on two dices will be greater than 7 or less than 7. If their guess is right, they get the bid amount from the other player’s purse. The game ends when one of the players goes bankrupt.<br />
Rules:<br />
•	Both players start off with 1008 units of currency. These are indivisible. The choice is arbitrary.<br />
•	The bidding process is sequential and not concurrent i.e. One player bids after the other is done. This is because there is no way of hiding the bidding of one person from the other. If bidding is made concurrent, we may end up with a situation where both players want to go second, and hence stall the game.<br />
•	The bidding is open, each player gets to see what the other has bid. Again, this is natural given the game setting.<br />
•	At each bid, 25% of the bid amount is deducted as deposit. This is done to deter players from making very high bids. The entire deposit amount is given to the winning player at the end of the game. Floors are taken when required.<br />
•	The maximum amount that can be bid is 127 units, and is higher than what the previous rule would prompt one to bid. The choice is somewhat arbitrary, but it has to be there and should preferably be of the form 2^n-1 to make full use of switches.<br />
•	The player who bids first must ensure the amount he is bidding is not more than the amount remaining in the other player’s purse as well as that he can pay the 25% deposit from his own purse.<br />
•	The second bidder must ensure the same, and must be able to pay the deposit even after subtracting the first players bid from his purse. This is required to ensure that the amount in his purse does not become negative irrespective of the outcome of the throw of dice.<br />
•	Failing the previous two conditions, the bid would not be accepted and the game would not progress until a valid bid is obtained.<br />
•	The player who bids first in one cycle must bid second in the next cycle, to make the process fully fair.<br />
•	The throw of dice is simulated by a random number generator.<br />
If 7 is obtained, player with higher bid wins. If both player have equal bids, nothing happens. Again, this is to promote higher bids.<br />

