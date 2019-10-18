# 17、leetcode443. 压缩字符串
解法一：
--  
思路：
--
    此题要求使用原地算法求解,即将压缩结果存在原chars[]数组中.使用双指针即可求解此题。这里我们称由相同字符组成的字符串为相同字符序列。指针j指示已压缩的结果的末尾,指针i指示未压缩字符串的开头。遇到相同的字符,指针i便向后滑动,直到遇到不同字符。指针i滑动的距离即为相同字符序列的长度。   
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/17 21:09
 * @descriptor  443. 压缩字符串
 */
public class Compress_443 {
    public static int compress(char[] chars) {
        int j = 0,temp = 0,i = 0;
       while(i < chars.length) {
           chars[j++] = chars[i];
           temp = i;
           while (i < chars.length && chars[i] == chars[j-1]) {
               i++;
           }
           if (i - temp > 1) {
               for (char c : String.valueOf(i - temp).toCharArray()) {
                   chars[j++] = c;
               }
           }
       }
        return j;
    }
    public static void main(String[] args) {
       //char[] c = {'a','a','b','b','c','c','c'};
        char[] c = {'a'};
        int compress = compress(c);
        System.out.println(compress);
    }
}
</pre>
