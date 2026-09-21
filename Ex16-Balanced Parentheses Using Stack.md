# Ex16 Check for Balanced Parentheses Using Stack
## DATE:20/09/2026
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Start the program.
2. Read an input string containing parentheses/brackets.
3. Create a stack to store opening brackets.
4. Traverse each character of the string:
5. If the character is an opening bracket (, {, [, push it onto the stack.If it is a closing bracket ), }, ]:
6. Check if the stack is empty: If yes, the string is unbalanced.
7. Otherwise, pop the top element from the stack and verify if it matches the current closing bracket.
8. If the brackets do not match, the string is unbalanced.
9. After traversal:
10. If the stack is empty, the string is balanced; otherwise, it's unbalanced.
11. Display the result.
12. End the program.
   

## Program:
```
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: Rubasri R
RegisterNumber:  212224240139
*/
```
```java

import java.util.Scanner;
        {
            return top==-1;
        }
        
        public boolean isFull()
        {
            return top==data.length-1;
        }
        public void push(char c)
        {
            if(isFull())
            {
                System.out.println("Stack overflow");
            }
            data[++top]=c;
        }
        public char pop()
        {
            if(isEmpty())
            {
                System.out.println("Stack underflow");
            }
            return data[top--];
            
            
        }
        public char peek()
        {
            if(isEmpty())
            {
                System.out.println("Stack underflow");
            }
            return data[top];
        }
    }


    public static boolean isBalanced(String expr) {
        ArrayStack st = new ArrayStack(expr.length());
        for (char ch : expr.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                st.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (st.isEmpty()) return false;
                char top = st.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return st.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String expr = sc.nextLine();
        boolean ok = isBalanced(expr);
        System.out.println(ok);
        sc.close();
    }
}

```

## Output:

<img width="363" height="130" alt="image" src="https://github.com/user-attachments/assets/52149e54-2fa2-40b3-8f6c-11b5cff763c7" />


## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
