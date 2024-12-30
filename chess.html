<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>لعبة الشطرنج</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
        }
        #chessboard {
            display: grid;
            grid-template-columns: repeat(8, 80px);
            grid-template-rows: repeat(8, 80px);
            border: 2px solid black;
        }
        .square {
            width: 80px;
            height: 80px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 50px;
            cursor: pointer;
        }
        .white {
            background-color: #eee;
        }
        .black {
            background-color: #555;
            color: white;
        }
        .highlight {
            background-color: yellow;
        }
        .timer {
            font-size: 24px;
            margin: 10px;
        }
        .active {
            color: red;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="timer" id="white-timer">الوقت المتبقي (الأبيض): 40 ثانية</div>
    <div class="timer" id="black-timer">الوقت المتبقي (الأسود): 40 ثانية</div>
    <div id="chessboard"></div>
    <button onclick="resetGame()">إعادة اللعبة</button>

    <script>
        const board = document.getElementById('chessboard');
        const whiteTimer = document.getElementById('white-timer');
        const blackTimer = document.getElementById('black-timer');

        const pieces = {
            'r': '♜', 'n': '♞', 'b': '♝', 'q': '♛', 'k': '♚', 'p': '♟',
            'R': '♖', 'N': '♘', 'B': '♗', 'Q': '♕', 'K': '♔', 'P': '♙'
        };

        const initialBoard = [
            ['R', 'N', 'B', 'Q', 'K', 'B', 'N', 'R'],
            ['P', 'P', 'P', 'P', 'P', 'P', 'P', 'P'],
            [null, null, null, null, null, null, null, null],
            [null, null, null, null, null, null, null, null],
            [null, null, null, null, null, null, null, null],
            [null, null, null, null, null, null, null, null],
            ['p', 'p', 'p', 'p', 'p', 'p', 'p', 'p'],
            ['r', 'n', 'b', 'q', 'k', 'b', 'n', 'r']
        ];

        let currentPlayer = 'white';
        let timers = { white: 40, black: 40 };
        let highlightedSquares = [];
        let draggedPiece = null;
        let fromSquare = null;
        let hasMoved = false;
        let timerInterval;

        function createChessboard() {
            board.innerHTML = '';
            for (let row = 0; row < 8; row++) {
                for (let col = 0; col < 8; col++) {
                    const square = document.createElement('div');
                    square.className = 'square ' + ((row + col) % 2 === 0 ? 'white' : 'black');
                    square.dataset.row = row;
                    square.dataset.col = col;

                    const piece = initialBoard[row][col];
                    if (piece) {
                        const pieceElement = document.createElement('div');
                        pieceElement.textContent = pieces[piece];
                        pieceElement.className = 'piece';
                        pieceElement.dataset.player = piece === piece.toUpperCase() ? 'white' : 'black';
                        pieceElement.draggable = true;
                        square.appendChild(pieceElement);
                    }

                    square.addEventListener('dragover', onDragOver);
                    square.addEventListener('drop', onDrop);
                    square.addEventListener('dragenter', onDragEnter);
                    square.addEventListener('dragleave', onDragLeave);
                    board.appendChild(square);
                }
            }
        }

        function highlightSquare(row, col) {
            const square = document.querySelector(`.square[data-row='${row}'][data-col='${col}']`);
            if (square) {
                square.classList.add('highlight');
                highlightedSquares.push(square);
            }
        }

        function clearHighlightedSquares() {
            highlightedSquares.forEach(square => square.classList.remove('highlight'));
            highlightedSquares = [];
        }

        function startTimer() {
            clearInterval(timerInterval);
            timerInterval = setInterval(() => {
                timers[currentPlayer]--;
                if (timers[currentPlayer] <= 0) {
                    clearInterval(timerInterval);
                    alert(`${currentPlayer === 'white' ? 'الأبيض' : 'الأسود'} انتهى وقته!`);
                }
                updateTimerDisplay();
            }, 1000);
        }

        function updateTimerDisplay() {
            whiteTimer.textContent = `الوقت المتبقي (الأبيض): ${timers.white} ثانية`;
            blackTimer.textContent = `الوقت المتبقي (الأسود): ${timers.black} ثانية`;
        }

        function switchTurn() {
            currentPlayer = currentPlayer === 'white' ? 'black' : 'white';
            updateActivePlayerDisplay();
            startTimer();
        }

        function updateActivePlayerDisplay() {
            whiteTimer.classList.toggle('active', currentPlayer === 'white');
            blackTimer.classList.toggle('active', currentPlayer === 'black');
        }

        function onDragOver(event) {
            event.preventDefault();
        }

        function onDragEnter(event) {
            event.preventDefault();
        }

        function onDragLeave(event) {
            event.preventDefault();
        }

        function onDrop(event) {
            event.preventDefault();
            if (draggedPiece && fromSquare) {
                const toSquare = event.target.closest('.square');
                if (toSquare && toSquare !== fromSquare) {
                    const fromRow = parseInt(fromSquare.dataset.row);
                    const fromCol = parseInt(fromSquare.dataset.col);
                    const toRow = parseInt(toSquare.dataset.row);
                    const toCol = parseInt(toSquare.dataset.col);

                    const piece = initialBoard[fromRow][fromCol];
                    if (isMoveLegal(piece, fromRow, fromCol, toRow, toCol)) {
                        toSquare.innerHTML = '';
                        toSquare.appendChild(draggedPiece);
                        initialBoard[toRow][toCol] = piece;
                        initialBoard[fromRow][fromCol] = null;
                        hasMoved = true;
                        switchTurn();
                    }
                }
            }
        }

        function isMoveLegal(piece, fromRow, fromCol, toRow, toCol) {
            switch (piece.toLowerCase()) {
                case 'p':
                    return isPawnMoveLegal(piece, fromRow, fromCol, toRow, toCol);
                case 'r':
                    return isRookMoveLegal(fromRow, fromCol, toRow, toCol);
                case 'n':
                    return isKnightMoveLegal(fromRow, fromCol, toRow, toCol);
                default:
                    return false;
            }
        }

        function isPawnMoveLegal(piece, fromRow, fromCol, toRow, toCol) {
            const direction = piece === 'P' ? -1 : 1;
            if (fromCol === toCol && initialBoard[toRow][toCol] === null) {
                if (toRow === fromRow + direction) return true;
                if ((fromRow === 6 && piece === 'P' || fromRow === 1 && piece === 'p') && toRow === fromRow + 2 * direction) return true;
            }
            if (Math.abs(fromCol - toCol) === 1 && toRow === fromRow + direction && initialBoard[toRow][toCol] !== null) {
                return true;
            }
            return false;
        }

        function resetGame() {
            for (let row = 0; row < 8; row++) {
                for (let col = 0; col < 8; col++) {
                    initialBoard[row][col] = row === 1 ? 'p' : (row === 6 ? 'P' : (row === 0 || row === 7 ? ['r', 'n', 'b', 'q', 'k', 'b', 'n', 'r'][col] : null));
                }
            }
            currentPlayer = 'white';
            timers = { white: 40, black: 40 };
            clearInterval(timerInterval);
            startTimer();
            createChessboard();
        }

        createChessboard();
        startTimer();
    </script>
</body>
</html>
