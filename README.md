# chess

Built using Node.js, Express.js, Socket.io and Chess.js

# Initialisation

Socket and Chess Object are initialised
defg
Board Element is selected from the DOM
Initial values for draggedPiece, sourceSquare and playerRole are set to null

# Initial Board Rendering

renderBoard() is called to display the initial state of the chess board

# Drag and Drop Functionality

renderBoard() sets up drag-and-drop event listeners for each piece and square.
Pieces are draggable based on the player's role
When a piece is dragged, draggedPiece and sourceSquare are set
When a piece is dropped, handleMove() is called to handle the move logic and emit it to the server

# Socket Event Handling (b/w client and server)

Socket Connection To The Server Using Socket.Io
Chess An Instance Of The Chess Class,
BoardElement DOM Element With The ID "Chessboard"
DraggedPiece The Piece Being Dragged During A Drag-And-Drop Action
SourceSquare Stores The Starting Square Of The Dragged Piece
PlayerRole Holds The Role Of The Player (E.G., "W" For White, "B" For Black, Or Null For A Spectator)

renderBoard :  
Renders the chessboard, sets up pieces and squares, adds event listeners for drag-and-drop functionality, updates board orientation.
handleMove :  
Constructs a move object, emits a "move" event through the socket.
getPieceUnicode :  
Returns the Unicode character for a given chess piece.
socket.on("playerRole") :  
Sets the player's role, calls renderBoard to update the board.
socket.on("spectatorRole") :  
Sets playerRole to null, calls renderBoard to update the board.
socket.on("boardState") :  
Loads a FEN string into the chess game, calls renderBoard to update the board.
socket.on("move") :  
Applies a move to the chess game, calls renderBoard to update the board.

