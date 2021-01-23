## Valid Sudoku
Determine if a 9x9 Sudoku board is valid. Only the filled cells need to be validated according to the following rules:

- Each row must contain the digits 1-9 without repetition.
- Each column must contain the digits 1-9 without repetition.
- Each of the 9 3x3 sub-boxes of the grid must contain the digits 1-9 without repetition.

![image](https://upload.wikimedia.org/wikipedia/commons/thumb/f/ff/Sudoku-by-L2G-20050714.svg/250px-Sudoku-by-L2G-20050714.svg.png)

The Sudoku board could be partially filled, where empty cells are filled with the character `'.'`.


### Solution 
```java
public boolean isValidSudoku(char[][] board) {
    Set seen = new HashSet();
    for (int i=0; i<9; ++i) {
        for (int j=0; j<9; ++j) {
            char number = board[i][j];
            if (number != '.')
                if (!seen.add(number + " in row " + i) ||
                    !seen.add(number + " in column " + j) ||
                    !seen.add(number + " in block " + i/3 + "-" + j/3))
                    return false;
        }
    }
    return true;
}
```

### Solution (own)
```javascript
/**
 * @param {character[][]} board
 * @return {boolean}
 */
var isValidSudoku = function(board) {
    
    var checkRow = function(row) {
        let array = [];
        for (let i = 0; i < 9; i++) {
            array.push(false);
        }
        for (let col = 0; col < 9; col++) {
            if (!Number.isNaN(Number(board[row][col]))) {
                if (!array[Number(board[row][col]) - 1]) {
                    array[Number(board[row][col]) - 1] = true;
                } else {
                    return false;
                }
            }
        }
        return true;
    };
    
    var checkCol = function(col) {
        let array = [];
        for (let i = 0; i < 9; i++) {
            array.push(false);
        }
        for (let row = 0; row < 9; row++) {
            if (!Number.isNaN(Number(board[row][col]))) {
                if (!array[Number(board[row][col]) - 1]) {
                    array[Number(board[row][col]) - 1] = true;
                } else {
                    return false;
                }
            }
        }
        return true;
    };
    
    var checkSubBox = function(row, col) {
        let array = [];
        for (let i = 0; i < 9; i++) {
            array.push(false);
        }
        for (let i = 3 * row; i < 3 * row + 3; i++) {
            for (let j = 3 * col; j < 3 * col + 3; j++) {
                if (!Number.isNaN(Number(board[i][j]))) {
                    if (!array[Number(board[i][j]) - 1]) {
                        array[Number(board[i][j]) - 1] = true;
                    } else {
                        return false;
                    }
                }
            }
        }
        return true;
    };
    
    // validating rows and columns
    for (let i = 0; i < 9; i++) {
        if (!checkRow(i)) return false;
        if (!checkCol(i)) return false;
    }
    
    // validating sub-boxes
    for (let i = 0; i < 3; i++) {
        for (let j = 0; j < 3; j++) {
            if (!checkSubBox(i, j)) return false;
        }
    }
    
    return true;
};
```
    
