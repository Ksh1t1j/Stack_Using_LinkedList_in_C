# Stack_Using_LinkedList_in_C
Programming Assignment

You need to construct a Stack S using a linked list of type ListNode described below.

struct ListNode{
    NumOp* record;
    ListNode* next;
};

Note that it uses numop records, as described in the assignment; The structure of the numop record is:

struct NumOp{
    char type;
    double num;
    char op;
};

Define the following functions of the stack S:

ListNode* CreateStack() : Initialize an empty stack, return the head pointer.

int IsEmpty(ListNode* S) : Return 1 if S is empty, 0 otherwise.

void Push(ListNode** S, NumOp* key) : Push a record of type NumOp to the stack S.

NumOp* Top(ListNode* S) : Return top of stack S without modifying it.

NumOp* Pop(ListNode** S) : Delete the top of stack S and return it.

In main(), you need to process a list of instructions, each will be in one of the following formats:

1 num : push the number num into the stack and print a special character '$' (without quotes)

2 op : push the operator op into the stack and print '$' (without quotes)

3 : print content of the top of the stack if it's not empty. print "error" (without quotes) otherwise.

4 : print "True" (without quotes) if stack is empty. print "False" otherwise.

5 : remove the top of the stack and print its content, if stack is not empty. print "error" (without quotes) otherwise.

Input Format

First line contains an Integer Q, the number of instructions to be processed. Next Q lines follow, with one instruction in each line.

(For simplicity, here num inputs are given as integers only, but keeping this field as double will be helpful for the second part of the assignment.)

Constraints
1<=Q<=100000

1<=num<=100

op: {+,-,*,/}

Output Format

Output of each instruction should be printed in a new line.

Sample Input 0

4

1 33

5

2 -

3

Sample Output 0

$

33.000000

$

-

Explanation 0

33.000000 is pushed.

now, stack top is the record containing 33.000000. so, stack top is popped and 33.000000 is printed.

next, '-' is pushed.

stack top, now, is the record containing '-'. so, '-' is printed.

