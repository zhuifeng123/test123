public class T{
12	    public static void main(String[] args){
13		int[]a = null;
14		Scanner input = new Scanner(System.in);
15		int len=0;
16		System.out.print("请输入数组的长度：");
17		try{
18		    len = Integer.parseInt(input.nextLine());
19		}catch(Exception e){
20		
21		}
22		
23		a = new int[len];
24		System.out.println("a.length ="+a.length);
25		
26		for(int i=0;i<a.length;i++){
27		    System.out.print("请输入数值：");
28		    a[i] = input.nextInt();
29		}
30		
31		System.out.println();
32		System.out.print("该数组为：");
33		for(int i=0;i<a.length;i++){
34		    
35		    System.out.print(a[i] + " ");
36		}
37		
38		
39		int sum = 0,max = 0;
40		for(int i=0;i<a.length;i++){
41		    sum = 0;
42		    for(int j=i;j<a.length;++j){
43			sum += a[j];
44			if(sum>max)
45			    max = sum;
46		    }
47		}
48		
49		System.out.println();
50		System.out.println("该数组之和的最大值为 "+max);
51	
52	    }
53	    
54	    
55	}
56	#test3
57	import java.util.Scanner;
58	
59	public class Y{
60	    public static void main(String[] args) {
61		Scanner input = new Scanner(System.in);
62		System.out.print("请输入英文：");
63		String str = input.nextLine();
64	        String[] strArr = str.split("\\s+|[,]");
65	        StringBuffer result = new StringBuffer();
66	        for(int i = strArr.length -1;i >=0; i--){
67	            result.append(strArr[i] + " ");
68	        }
69	        result.setCharAt(str.length()-3, ' ');
70	        System.out.println("颠倒顺序后的结果为："+result.toString());
71	}}
