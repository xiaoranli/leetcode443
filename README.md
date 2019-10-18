# 17、leetcode443. 压缩字符串
解法一：
--  
思路：
--
    一开始，机器人在 (x, y) = (0, 0)。如果指令是 'U'，机器人会走到 (x, y-1)，如果指令是 'R'，机器人会走到 (x, y) = (x+1, y)，以此类推。  
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/17 15:54
 * @descriptor
 */
public class JudgeCircle_657 {
    public static boolean judgeCircle(String moves) {
        int x = 0,y = 0;
        for (char c:moves.toCharArray()) {
            if(c == 'U')
                x++;
            else if(c == 'D')
                x--;
            else if(c == 'L')
                y++;
            else if(c == 'R')
                y--;
        }
        if(x == 0 && y == 0)
            return true;
        else
            return false;
    }
    public static void main(String[] args) {
        String s = "LR";
        boolean b = judgeCircle(s);
        System.out.println(b);
    }
}
</pre>
