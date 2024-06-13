# 11.ACC-SimpleSwitch

## 5.2.2 Switch statement and expression**

There are two kinds of switch instructions in Java. First, let us consider the "classic" form of this instruction: switch statement.

It resembles a series of else if statements (but is not equivalent). It looks like this:

```java
switch (expr) {
    case val1:
        statement1;
        // ...
        statementN;
        break;
    case val2:
        statement1;
        // ...
        statementN;
        // should we break?
        // ...
    default:
        statement1;
        // ...
        statementN;
        break;
}
```

The value of `expr` must be either of an integral type (but not `long`), or a reference to a `String`, or an enumeration constant (which we will introduce later). Symbols `val` stand for values with which the value of `expr` will be compared (in the specified order). They have to be literal values (not variables). If the value of `expr` is equal to any of `vals`, the code in the corresponding arm is executed and then execution continues (falls through) with all the arms below; to avoid it, use `break`, which transfers control flow out of the switch block (sometimes this "falling through" may be just what we want, as in the example below).

At the end of this example, we used `default` arm, where we don’t make any comparisons: this will be the arm selected if all other comparisons yield false. The `default` clause is optional and doesn’t have to appear as the last. For example:
```

## Listing 11 ACC-SimpleSwitch/SimpleSwitch.java Page 32

```java
import java.util.Scanner;

public class SimpleSwitch {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.print("Enter an initial: ");
        char initial = scan.next().charAt(0);
        scan.close();

        switch (initial) {
            case 'A':
            case 'a':
                System.out.println("Amelia");
                break;
            case 'B':
            case 'b':
                System.out.println("Barbra");
                break;
            case 'C':
            case 'c':
                System.out.println("Cindy");
                break;
            case 'D':
            case 'd':
                System.out.println("Doris");
                break;
            default:
                System.out.println("Invalid input");
        }
    }
}
```
