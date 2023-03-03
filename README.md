# Venkysio-20951a05b7
# Reversing substring in python
x=input().split()
l=[]
for i in x:
  m=i[::-1]
  l.append(m)
print(*l)



#Reverse substring in a paragraph using recursion in python

def reverse_strings(p):
  if not p:
    return " "
  else:
    words = p.split(" ")
    w1=words[0]
    r=" ".join(words[1:])
    reversed_word = w1[::-1]
    return reversed_word + " " + reverse_strings(r)
p=input()
l=reverse_strings(p)
print(l)



#Multithreading in python

import concurrent.futures
def reverse_strings(p):
  words=p.split()
  with concurrent.futures.ThreadPoolExecutor() as executor:
    futures=[executor.submit(reverse_word,w) for w in words]
    results=[future.result() for future in concurrent.futures.as_completed(futures)]
  return ' '.join(results)
def reverse_word(w):
  return w[::-1]
if __name__=='__main__':
  input_p=input()
  output_p=reverse_strings(input_p)
  print(output_p)





#reverse substrings in a paragraph using recursion in java
import java.io.*;
import java.util.*;
 
class paragraph {
static void reverseWords(String str)
{
    Stack<Character> st=new Stack<Character>();
    for (int i = 0; i < str.length(); ++i) {
        if (str.charAt(i) != ' ')
            st.push(str.charAt(i));
        else {
            while (st.empty() == false) {
                System.out.print(st.pop());
                 
            }
            System.out.print(" ");
        }
    }
    while (st.empty() == false) {
        System.out.print(st.pop());
         
    }
}
public static void main(String[] args)
{
   Scanner sc=new Scanner(System.in);  
   String str= sc.nextLine();   
    reverseWords(str);
  }
}


