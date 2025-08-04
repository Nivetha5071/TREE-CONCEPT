## 01. BY USING 2 DIRECTION

```` java[]
package TREES;
import java.util.*;
public class example4 {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
        int size = sc.nextInt();
        int[][]mat =  new int [size][size];
        for(int i=0;i<mat.length;i++) {
        	for(int j=0;j<mat.length;j++) {
        		mat[i][j]= sc.nextInt();
        	}
        }
        track(mat, size, 0, 0, "");
	}
	public static void track(int[][] mat, int n, int i, int j, String path) {
		if(i==n || j==n) return;
		if(mat[i][j] == 0) return;
		if(i==n-1 && j==n-1) {
		System.out.println(path);
		return;
	}
  track(mat, n, i+1, j, path + "D ");
  track(mat, n,i, j+1, path + "R ");
	}
}

output:
4
1 0 1 1
1 0 1 1
1 1 1 1
0 0 0 1
D D R R R D

````

##  02. BY USING 4 DIRECTION

````java[]

package TREES;
import java.util.*;

public class Example5{

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int size = sc.nextInt();
        int[][] mat = new int[size][size];

        for (int i = 0; i < mat.length; i++) {
            for (int j = 0; j < mat.length; j++) {
                mat[i][j] = sc.nextInt();
            }
        }

        boolean[][] visited = new boolean[size][size];
        track(mat, size, 0, 0, "", visited);
    }

    public static void track(int[][] mat, int n, int i, int j, String path, boolean[][] visited) {
     
        if (i < 0 || j < 0 || i >= n || j >= n) return;
        if (mat[i][j] == 0 || visited[i][j]) return;
        if (i == n - 1 && j == n - 1) {
            System.out.println(path);
            return; 
        }
        visited[i][j] = true;
        track(mat, n, i + 1, j, path + "D ", visited); 
        track(mat, n, i, j + 1, path + "R ", visited); 
        track(mat, n, i - 1, j, path + "U ", visited); 
        track(mat, n, i, j - 1, path + "L ", visited); 
        visited[i][j] = false;
    }
}

output:
4
1 0 1 1
1 0 1 1
1 1 1 1
0 0 0 1R D D 
D D R R U U R D D D
````
