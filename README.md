- 👋 Hi, I’m @vinaymashi
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
vinaymasih/vinaymasih is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->   public class program19 {
    static void printSpiralPattern(int size) {
        int row = 0, col = 0;
        int boundary = size - 1;
        int sizeLeft = size - 1;
        int flag = 1;
        char move = 'r';
        int[][] matrix = new int[size][size];

        for (int i = 1; i <= size * size; i++) {
           // System.out.println (i);
            matrix[row][col] = i;

            if (move == 'r') {
                col += 1;
            } else if (move == 'l') {
                col -= 1;
            } else if (move == 'u') {
                row -= 1;
            } else if (move == 'd') {
                row += 1;
            }

            if (i == boundary) {
                boundary = boundary + sizeLeft;
                
                if (flag != 2) {
                    flag = 2;
                } else {
                    flag = 1;
                    sizeLeft -= 1;
                }

                if (move == 'r') {
                    move = 'd';
                } else if (move == 'd') {
                    move = 'l';
                } else if (move == 'l') {
                    move = 'u';
                } else if (move == 'u') {
                    move = 'r';
                }
            }
        }
        
        for (row = 0; row < size; row++) {
            for (col = 0; col < size; col++) {
                int n = matrix[row][col];
                if (n < 10) {
                    System.out.print(n + " ");
                } else {
                    System.out.print(n + " ");
                }
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        int size = 10;
        System.out.println("Spiral Matrix or Pattern is: \n");
        printSpiralPattern(size);
    }
}
