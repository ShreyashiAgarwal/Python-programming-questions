# Python-programming-questions


1.Find Unique
#.....................................................................................................................................#
Given an integer array of size 2N + 1. In this given array, N numbers are present twice and one number is present only once in the array.
You need to find and return that number which is unique in the array.

Note : Given array will always contain odd number of elements.

Input format :
Line 1 : Array size i.e. 2N+1
Line 2 : Array elements (separated by space)

Output Format :
Unique element present in the array

Constraints :
1 <= N <= 10^3

Sample Input :
7
2 3 1 6 3 6 2

Sample Output :
1
#.......................................................................................................................................#
SOLUTION-
def findUni(x):
    i=0
    while(i<len(x)):
        if(x[i]==x[i+1]):
            i=i+2
        else:
            return x[i]
n=int(input())
li=[int(x) for x in input().split()]
li.sort()
y=findUni(li)
print(y)


#......................................................................................................................................#
2.Find duplicate
#......................................................................................................................................#

Given an array of integers of size n which contains numbers from 0 to n - 2. Each number is present at least once. That is, if n = 5, numbers from 0 to 3 is present in the given array at least once and one number is present twice. You need to find and return that duplicate number present in the array.
Assume, duplicate number is always present in the array.

Input format :
Line 1 : Size of input array
Line 2 : Array elements (separated by space)

Output Format :
Duplicate element

Constraints :
1 <= n <= 10^3

Sample Input:
9
0 7 2 5 4 7 1 3 6
Sample Output:
7
#.....................................................................................................................................#
SOLUTION -
def dup(li):
    i=0
    while(i<n):
        if(li[i]==li[i+1]):
            return li[i]
        else:
            i=i+1
n=int(input())
li=[int(x) for x in input().split()]
li.sort()
y=dup(li)
print(y)


#.....................................................................................................................................#
3.e-maze-in
#.....................................................................................................................................#
Ankit is in maze. The command center sent him a string which decodes to come out from the maze. He is initially at (0, 0). String contains L, R, U, D denoting left, right, up and down. In each command he will traverse 1 unit distance in the respective direction.

For example if he is at (2, 0) and the command is L he will go to (1, 0).

Input:
Input contains a single string.

Output:
Print the final point where he came out.

Constraints:

1 ≤ |S| ≤ 200

SAMPLE INPUT 
LLRDDR

SAMPLE OUTPUT 
0 -2
#.....................................................................................................................................#
SOLUTION-
S = input()
L,R,U,D = -1,1,1,-1
x,y=0,0
l=len(S)
for i in range(l):
    if(S[i]=='R'):
        x=x+R
    elif(S[i]=='L'):
        x=x+L
    elif(S[i]=='U'):
        y=y+U
    else:
        y=y+D
print(x,y)


#.....................................................................................................................................#
4.WHAT IS YOUR MOBILE NUMBER?
#.....................................................................................................................................#
These days Bechan Chacha is depressed because his crush gave him list of mobile number some of them are valid and some of them are invalid. Bechan Chacha has special power that he can pick his crush number only if he has valid set of mobile numbers. Help him to determine the valid numbers. 
You are given a string "S" and you have to determine whether it is Valid mobile number or not. Mobile number is valid only if it is of length 10 , consists of numeric values and it shouldn't have prefix zeroes. 

Input:
First line of input is T representing total number of test cases.
Next T line each representing "S" as described in in problem statement. 

Output:
Print "YES" if it is valid mobile number else print "NO". 
Note: Quotes are for clarity. 

Constraints:
1<= T <= 103
sum of string length <= 105

SAMPLE INPUT 
3
1234567890
0123456789
0123456.87

SAMPLE OUTPUT 
YES
NO
NO
#.....................................................................................................................................#
SOLUTION-

T = int(input())
for i in range(T):
    s = input()
    l =len(s)
    
    
   if((s[0]!="0") and s.isdigit() and l==10):
        print("YES")
   else:
        print("NO")


#.....................................................................................................................................#
5.Birthday Party
#.....................................................................................................................................#
Mr. X's birthday is in next month. This time he is planning to invite N of his friends. He wants to distribute some chocolates to all of his friends after party. He went to a shop to buy a packet of chocolates.
At chocolate shop, each packet is having different number of chocolates. He wants to buy such a packet which contains number of chocolates, which can be distributed equally among all of his friends.
Help Mr. X to buy such a packet.

Input:
First line contains T, number of test cases.
Each test case contains two integers, N and M. where is N is number of friends and M is number number of chocolates in a packet.

Output:
In each test case output "Yes" if he can buy that packet and "No" if he can't buy that packet.

Constraints:
1<=T<=20
1<=N<=100
1<=M<=10^5

SAMPLE INPUT 
2
5 14
3 21

SAMPLE OUTPUT 
No
Yes

Explanation
Test Case 1:
There is no way such that he can distribute 14 chocolates among 5 friends equally. 

Test Case 2:
There are 21 chocolates and 3 friends, so he can distribute chocolates eqally. Each friend will get 7 chocolates.
#.....................................................................................................................................#
SOLUTION-
T = int(input())
for i in range (T):
    li = [ int(x) for x in input().split()]
    N,M = li[0],li[1]
    if(M % N==0):
        print("Yes")
    else:
        print("No")
        
       #.....................................................................................................................................#
6.Book of potion making   #.....................................................................................................................................#
Harry wants to find Voldemort's potion making book but he is confused about how to get it.

The book has a special ISBN(International Standard Book Number) which is  unique numeric book identifier only for Voldemort's book printed on it. The ISBN is based upon a 10-digit code. 

The ISBN is valid if:
1xdigit1 + 2xdigit2 + 3xdigit3 + 4xdigit4 + 5xdigit5 + 6xdigit6 + 7xdigit7 + 8xdigit8 + 9xdigit9 + 10xdigit10 is divisible by 11.

Help Harry to find the book!

Input:
 Input the ISBN code as a 10-digit integer.

Output:
If the ISBN is not a 10-digit integer, output the message “Illegal ISBN” and terminate the program.
If the number is 10-digit, extract the digits of the number and compute the sum as explained in the explanation.
If the sum is divisible by 11, output the message, “Legal ISBN”. If the sum is not divisible by 11, output the message, “Illegal ISBN”.

SAMPLE INPUT 
1401601499

SAMPLE OUTPUT 
Legal ISBN

Explanation
For an ISBN 1401601499
Sum=1×1 + 2×4 + 3×0 + 4×1 + 5×6 + 6×0 + 7×1 + 8×4 + 9×9 + 10×9 = 253 which is divisible by 11.
#.....................................................................................................................................#
Solution-
ISBN = input()
if(len(ISBN)!=10):
    print("Illegal ISBN")
else:
    sum=0
    for i in range(10):
        sum = sum+int(ISBN[i])*i
    if(sum/11):
        print("Legal ISBN")
    else:
        print("Illegal ISBN")


#.....................................................................................................................................#
7.Push zeroes to end
#.....................................................................................................................................#
Given a random integer array, push all the zeros that are present to end of the array. The respective order of other elements should remain same.

Change in the input array itself. You don't need to return or print elements. Don't use extra array.

Note : You need to do this in one scan of array only.

Input format :
Line 1 : Integer N, Array Size
Line 2 : Array elements (separated by space)

Output Format :
Array elements (separated by space)

Constraints :
1 <= N <= 10^6

Sample Input 1:
7
2 0 4 1 3 0 28

Sample Output 1:
2 4 1 3 28 0 0

Sample Input 2:
5
0 3 0 2 0

Sample Output 2:
3 2 0 0 0

#.....................................................................................................................................#
SOLUTION-
def zeroes(arr):
    l = len(arr)
    li=[]
    li_zero = []
    for i in range(l):
        if(arr[i]!=0):
            li.append(arr[i])
         else:
            li_zero.append(arr[i])
    final_arr =li+li_zero
    l1=len(final_arr)
    for j in range(l1-1):
        print(final_arr[j],end=" ")
    print(final_arr[j])
            
n = int(input())
arr = [int(x) for x in input().split()]
zeroes(arr)

#.....................................................................................................................................#

#.....................................................................................................................................#






