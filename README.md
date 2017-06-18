//# TIC-TAC-TOE-GAME-BETWEEN-TWO-PLAYERS
//Its a tic tac toe game made in HTML , CSS , JAVASCRIPT codes . its a game to be played between two players.
//Vighnesh Tiwari Codes //CR7VIGGY GITHUB PROFILE................AIT PUNE,INDIA
<!DOCTYPE HTML>
<html>
	<head>
		<title>Tic-Tack-Toe</title>
		<script>
			var a = 0;		//1 means box occupied by player1 2 means box occupied by player2
			var b = 0;
			var c = 0;
			var d = 0;
			var e = 0;
			var f = 0;
			var g = 0;
			var h = 0;
			var i = 0;
			
			var whose_move = 1;		//1 means player1 turn and 2 means player2 turn
			
			var temp = '';		//stores clicked id of box

			var ok = 0;		//0 invalid move and 1 valid move
			
			var who_won = 0;		//1 if player1 wins,2 if player2 wins,3 if its a tie
			
			var count_player1_wins = 0;
			var count_player2_wins = 0;
			var count_ties = 0;
			
			function check_Space()
			{
				if((temp == "A") && (a == 0))
				{
					ok = 1;
					if(whose_move == 1)	a = 1;
					if(whose_move == 2) a = 2;
				}
				if((temp == "B") && (b == 0))
				{
					ok = 1;
					if(whose_move == 1)	b = 1;
					if(whose_move == 2) b = 2;
				}
				if((temp == "C") && (c == 0))
				{
					ok = 1;
					if(whose_move == 1)	c = 1;
					if(whose_move == 2) c = 2;
				}
				if((temp == "D") && (d == 0))
				{
					ok = 1;
					if(whose_move == 1)	d = 1;
					if(whose_move == 2) d = 2;
				}
				if((temp == "E") && (e == 0))
				{
					ok = 1;
					if(whose_move == 1)	e = 1;
					if(whose_move == 2) e = 2;
				}
				if((temp == "F") && (f == 0))
				{
					ok = 1;
					if(whose_move == 1)	f = 1;
					if(whose_move == 2) f = 2;
				}
				if((temp == "G") && (g == 0))
				{
					ok = 1;
					if(whose_move == 1)	g = 1;
					if(whose_move == 2) g = 2;
				}
				if((temp == "H") && (h == 0))
				{
					ok = 1;
					if(whose_move == 1)	h = 1;
					if(whose_move == 2) h = 2;
				}
				if((temp == "I") && (i == 0))
				{
					ok = 1;
					if(whose_move == 1)	i = 1;
					if(whose_move == 2) i = 2;
				}
			}
			
			function check_win()
			{
				if((a == 1) && (b == 1) && (c ==1))	who_won = 1;
				if((a == 1) && (d == 1) && (g ==1))	who_won = 1;
				if((a == 1) && (e == 1) && (i ==1))	who_won = 1;
				if((a == 1) && (b == 1) && (c ==1))	who_won = 1;
				if((b == 1) && (e == 1) && (h ==1))	who_won = 1;
				if((c == 1) && (f == 1) && (i ==1))	who_won = 1;
				if((d == 1) && (e == 1) && (f ==1))	who_won = 1;
				if((g == 1) && (h == 1) && (i ==1))	who_won = 1;
				if((g == 1) && (e == 1) && (c ==1))	who_won = 1;
				
				if((a == 2) && (b == 2) && (c ==2))	who_won = 2;
				if((a == 2) && (d == 2) && (g ==2))	who_won = 2;
				if((a == 2) && (e == 2) && (i ==2))	who_won = 2;
				if((a == 2) && (b == 2) && (c ==2))	who_won = 2;
				if((b == 2) && (e == 2) && (h ==2))	who_won = 2;
				if((c == 2) && (f == 2) && (i ==2))	who_won = 2;
				if((d == 2) && (e == 2) && (f ==2))	who_won = 2;
				if((g == 2) && (h == 2) && (i ==2))	who_won = 2;
				if((g == 2) && (e == 2) && (c ==2))	who_won = 2;
				
				if((a != 0) && (b != 0) && (c != 0) && (d != 0) && (e != 0) && (f != 0) && (g != 0) && (h != 0) && (i != 0) && (who_won == 0))	who_won = 3;
			}
			
			function process()
			{
				check_win();
				if(who_won == 1)
				{
					alert('Player1 Won!');
					count_player1_wins++;
					document.getElementById('player1').value = count_player1_wins;
					whose_move = 0;
				}
				else if(who_won == 2)
				{
					alert('Player2 Won!');
					count_player2_wins++;
					document.getElementById('player2').value = count_player2_wins;
					whose_move = 0;
				}
				else if(who_won == 3)
				{
					alert('Tie!');
					count_ties++;
					document.getElementById('tie').value = count_ties;
					whose_move = 0;
				}
			}
			
			function Move(c)
			{
				temp = c;
				ok = 0;
				if(whose_move==1)
				{
					check_Space();
					if(ok==1)
					{
						document.getElementById(c).src = "o.png";
						whose_move = 2;
						process();
					}
					else
					{
						alert("That Box is already occupied.Please Select Another Box");
					}
				}
				else
				{
					check_Space();
					if(ok==1)
					{
						document.getElementById(c).src = "x.gif";
						whose_move = 1;
						process();
					}
					else
					{
						alert("That Box is already occupied.Please Select Another Box");
					}
				}
			}
			
			function playAgain()
			{
				a = 0;		
				b = 0;
				c = 0;
				d = 0;
				e = 0;
				f = 0;
				g = 0;
				h = 0;
				i = 0;
			
				whose_move = 1;		
			
				temp = '';		

				ok = 0;		
			
				who_won = 0;
				
				document.getElementById('A').src =  "blank.jpg";
				document.getElementById('B').src =  "blank.jpg";
				document.getElementById('C').src =  "blank.jpg";
				document.getElementById('D').src =  "blank.jpg";
				document.getElementById('E').src =  "blank.jpg";
				document.getElementById('F').src =  "blank.jpg";
				document.getElementById('G').src =  "blank.jpg";
				document.getElementById('H').src =  "blank.jpg";
				document.getElementById('I').src =  "blank.jpg";
			}
			
			function help()
			{
				alert("Welcome to Tic-Tac-Toe! Player1 plays as the 0's and Player2 plays as the X's.Select the square you want to put your variable into by clicking them.You cannot occupy a square that is already occupied. The first player to get three squares in a row wins. Good Luck!!");
			}
			
		</script>
	</head>
	<body bgcolor="#E6D6FA">
		<center>
		<h1>Tic-Tack-Toe</h1>
		<table border = 1>
			<tr>
				<td><a href="javascript:Move('A')"><img src = "blank.jpg" border = 0 height = 100 width =100 id = "A"></td>
				<td><a href="javascript:Move('B')"><img src = "blank.jpg" border = 0 height = 100 width =100 id = "B"></td>
				<td><a href="javascript:Move('C')"><img src = "blank.jpg" border = 0 height = 100 width =100 id = "C"></td>
			</tr>
			<tr>
				<td><a href="javascript:Move('D')"><img src = "blank.jpg" border = 0 height = 100 width =100 id = "D"></td>
				<td><a href="javascript:Move('E')"><img src = "blank.jpg" border = 0 height = 100 width =100 id = "E"></td>
				<td><a href="javascript:Move('F')"><img src = "blank.jpg" border = 0 height = 100 width =100 id = "F"></td>
			</tr>
			<tr>
				<td><a href="javascript:Move('G')"><img src = "blank.jpg" border = 0 height = 100 width =100 id = "G"></td>
				<td><a href="javascript:Move('H')"><img src = "blank.jpg" border = 0 height = 100 width =100 id = "H"></td>
				<td><a href="javascript:Move('I')"><img src = "blank.jpg" border = 0 height = 100 width =100 id = "I"></td>
			</tr>
		</table>
		&nbsp;
		<table>
			<tr>
				<td><input type="text" size = "5" id = "player1" value = 0></td>
				<td>Player1</td>
			</tr>
			<tr>
				<td><input type="text" size = "5" id = "player2" value = 0></td>
				<td>Player2</td>
			</tr>
			<tr>
				<td><input type="text" size = "5" id = "tie" value = 0></td>
				<td>Tie</td>
			</tr>
		</table>
		<br>
		<input type = "button" value = "Play Again" onClick = "playAgain();">
		&nbsp;&nbsp;
		<input type = "button" value = "Game Help" onClick = "help();">
		</center>
	</body>
</html>
