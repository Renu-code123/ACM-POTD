#Solution:
```
import java.util.*;

class Solution {
    public int[][] floodFill(int[][] image, int sr, int sc, int color) {
        int original = image[sr][sc];
        
        if (original == color) return image;
        
        Queue<int[]> q = new LinkedList<>();
        q.offer(new int[]{sr, sc});
        
        while (!q.isEmpty()) {
            int[] curr = q.poll();
            int r = curr[0], c = curr[1];
            
            if (r < 0 || c < 0 || r >= image.length || c >= image[0].length)
                continue;
            
            if (image[r][c] != original)
                continue;
            
            image[r][c] = color;
            
            q.offer(new int[]{r + 1, c});
            q.offer(new int[]{r - 1, c});
            q.offer(new int[]{r, c + 1});
            q.offer(new int[]{r, c - 1});
        }
        
        return image;
    }
}
```
