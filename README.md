# Tic-Tac-Toe READ ME!

## Technologies
*HTML
*CSS
*JAVASCRITP

## About the Game

I created this tic-tac-toe game using the HTML, CSS, and Javascript in VS code. It is a two player interactive game with one player labeled player_x and the other player_o. When you begin the game the first player will select one of the nine boxes and place a "X", the other player will then select a box and place a "O" in the selected box. The players will then take turns making selections until one player has three of their marks in a row, signifing a winner. 

##HTML 

I first created a boilerplate consisting of a title, links to css and javascript,a header, a body, and a div with the class container. Heres what it looks like:

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Tic Tac Toe</title>
  <link rel="stylesheet" type="text/css" href="css/style.css">
</head>
<body>
  <h1>Tic-Tac-Toe</h1>

  <div class= 'container'>

  <script type="text/javascript" src="js/app.js"></script>
</body>
</html>

#CSS

I used CSS to add styling to my HTML and to create the gameboard. The gameboard was created within my container div using the grid display. Here is a snippet of how i created the board in css:

.container{
  width: 565px;
  height: 565px;
  display: grid; 
  background-color: rgb(196, 194, 194);
  justify-content: center;
  align-content: center;
  text-align: center;
  grid-template-columns: repeat(3,auto);
  margin: 0 auto;
}

#Javascript

After creating my board using HTML and CSS i used the programming language Javascript to write all the code functions that make the game interative. The first thing i did was use the container i created in HTML to create nine more div's that each had there own id and class, which when the div is clicked would give it a new class of either player_x or player_o. Here is a snippet of the code just described:

for (i = 1; i <= 9; i++){
    const box = document.createElement('div')
    box.classList.add('box')
    box.id = 'box' + i
    box.addEventListener('click',() =>{
        console.log('div clicked')
        if(switchPlayer % 2 == true){
            if(box.textContent === 'X' || box.textContent === 'O'){
                return;
            }else{
                box.textContent = 'X';
                box.classList.add('player_x')
                switchPlayer++;
            }
         } else {
            if(box.textContent === 'X' || box.textContent === 'O'){
                return;
            } else{
                box.textContent = 'O';
                box.classList.add('player_o')
                switchPlayer++;
            }
        }
        
    });

