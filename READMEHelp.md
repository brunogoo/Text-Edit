Hey guys trying to get my codes to work to print out the following.

$ java Buffer
|There is grandeur in this view of life, with its several powers,
having been originally breathed by the Creator into a few forms or 
into one; and that, whilst this planet has gone cycling on according
to the fixed law of gravity, from so simple a beginning endless forms 
most beautiful and most wonderful have been, and are being, evolved.
-- Charles Darwin, The Origin of Species


I have written my code through my Algorithm text book and some examples from the internet and have produce 
the same word printing only it comes out like:

|T h e r e  i s   g r a n d e u r   i n    t h i s   v i e w   o f   l i f e ,   w i t h   i t s   s e v e r a l   p o w e r s , 
h a v i n g   b e e n   o r i g i n a l l y   b r e a t h e d   b y   t h e   C r e a t o r   i n t o   a   f e w   f o r m s   o r   
i n t o   o n e ;   a n d   t h a t ,   w h i l s t   t h i s   p l a n e t   h a s   g o n e   c y c l i n g   o n   a c c o r d i n g 
t o   t h e   f i x e d   l a w   o f   g r a v i t y ,   f r o m   s o   s i m p l e   a   b e g i n n i n g   e n d l e s s   f o r m s  
m o s t   b e a u t i f u l   a n d   m o s t   w o n d e r f u l   h a v e   b e e n ,   a n d   a r e   b e i n g ,   e v o l v e d . 
 - -   C h a r l e s   D a r w i n ,   T h e   O r i g i n   o f   S p e c i e s 
 
 spaces inbetween and I supect it is my toString() method, but cant figure out how to close my spacings from it without
 adding another class.
 
 my code is strucured like this I will print the main seperately in the comments as well as my code



import edu.princeton.cs.algs4.Stack;
import edu.princeton.cs.algs4.StdOut;

// A data type representing a text editor buffer.
public class Buffer {
    private Stack<Character> left;  // chars left of cursor
    private Stack<Character> right; // chars right of cursor

    // Create an empty buffer.
    public Buffer() {
        left = new Stack<Character>();
        right = Stack<Character>()
    }

    // Insert c at the cursor position.
    public void insert(char c) {
        left.push(c);
    }
    
    // Delete and return the character at the cursor.
    public char delete() {
        if(!right.isEmpty()) {
          return right.pop());
        }else
        return 0;
    }

    // Move the cursor k positions to the left.
    public void left(int k) {
        while (!left.isEmpty() && --k >= 0) {
          right.push(left.pop());
          }
    }

    // Move the cursor k positions to the right.
    public void right(int k) {
        while (!right.isEmpty() && --k >= 0) {
          left.push(right.pop());
    }

    // Return the number of characters in the buffer.
    public int size() {
        left.size() + right.size()
    }

    // Return a string representation of the buffer with a "|" character (not 
    // part of the buffer) at the cursor position.
    public String toString() {
        String a = right+ "|" + left;
        return a;
    }
