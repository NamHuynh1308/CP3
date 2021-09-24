# CP3
## 9/20/21
### _finish project 1

# 9/22/21
## _Question:
### What is abstract class using in the example of Wednesday class?
## _Wednesday code
public class Driver {
1.	
2.	    public static void main(String[] args) 
3.	    {
4.	        //Produce p = new Produce();
5.	        Produce f = new Fruit();
6.	        f.eat();
7.	        Bananas l = new Bananas();
8.	        l.makeSomebodyFall();
9.	        
10.	        Produce b = new Bananas();
11.	        //b.makeSomebodyFall();
12.	        
13.	        Bananas b1 = (Bananas) new Fruit();
14.	        b1.eat();
15.	    }
16.	
17.	}
18.	public abstract class Produce 
19.	{
20.	    protected int price;
21.	    
22.	    private static int counter = 1_000;
23.	    private static final int THOUSAND = 1_000;
24.	    
25.	    public Produce(int value)
26.	    {
27.	        this.price = value;
28.	        ++counter;
29.	    }
30.	    
31.	    public Produce()
32.	    {
33.	        this(50);
34.	    }
35.	    
36.	    public void eat()
37.	    {
38.	        System.out.println("chomp");
39.	    }
40.	    
41.	    public abstract int calculatePrice();
42.	    
43.	    public String toString()
44.	    {
45.	        System.out.println("Price: ");
46.	    }
47.	}
48.	import java.util.Arrays;
49.	
50.	public class Fruit extends Produce 
51.	{
52.	    
53.	    int[] weights = new int[10];
54.	    
55.	    public Fruit (int value, int[] values)
56.	    {
57.	        super(value);
58.	        this.weights = values;
59.	    }
60.	    
61.	    public Fruit()
62.	    {
63.	        assignValues();
64.	        super.price = 6;
65.	    }
66.	
67.	    private void assignValues() 
68.	    {
69.	        this.weights[0] = 1;
70.	        
71.	    }
72.	
73.	    @Override
74.	    public String toString() 
75.	    {
76.	        String str = super.toString()
77.	        + " B [values=" + Arrays.toString(weights) + "]";
78.	        
79.	        return str;
80.	    }
81.	
82.	    @Override
83.	    public int calculatePrice() 
84.	    {
85.	        // implement
86.	        int totalWeight = 0;
87.	        for (int i = 0; i < weights.length; i++)
88.	        {
89.	            totalWeight += weights[i];
90.	        }
91.	        return totalWeight * super.price;
92.	    }
93.	    
94.	    
95.	    
}
96.	public class C extends Fruit
97.	{
98.	    private String name;
99.	    
100.	    public C(int i, int[] array, String str)
101.	    {
102.	        super(i, array);
103.	        this.name = name;
104.	    }
}
public class Vegetable extends Produce
{
    int numberOf;

    public Vegetable(int price, int numberOf) 
    {
        super(price);
        this.numberOf = numberOf;
    }

    @Override
    public int calculatePrice() 
    {
        return numberOf * price;
    }
}
public class Bananas extends Fruit 
105.	{
106.	    
107.	    public void makeSomebodyFall()
108.	    {
109.	        System.out.println("Ouch");
110.	    }
111.	    
}
public class Lettuce extends Vegetable
{

    public Lettuce(int price, int numberOf) 
    {
        super(price, numberOf);
    }

}
