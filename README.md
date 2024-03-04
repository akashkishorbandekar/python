1A. Develop a Python Program to read N digit numbers and separate the integer number and display each 
digit.
n=int(input("Enter an integer number: "))
divisor=1
temp=n
while temp//divisor>=10:
 divisor*=10
while divisor>0:
 digit=temp//divisor
 print(digit,end=" ")
 temp%=divisor
 divisor//=10
1B. Develop a Python Program to read N digit numbers and print the reverse of the number
num=int(input("Enter an integer number: "))
reversed_num=0
while num!=0:
 digit=num%10
 reversed_num=reversed_num*10+digit
 num//=10
print("Reversed Number: ",reversed_num)
2. Develop a Python Program to accept 4 numbers and display them in sorted order using number of if else 
statements
num1=int(input("Enter the first number"))
num2=int(input("Enter the second number"))
num3=int(input("Enter the third number"))
num4=int(input("Enter the fourth number"))
if(num1>num2):
 num1,num2=num2,num1
elif(num3>num4):
 num3,num4=num3,num4
if(num2>num4):
 num2,num4=num4,num2
if(num1>num3):
 num1,num3=num3,num1
if(num2>num3):
 num2,num3=num3,num2
print(num1,num2,num3,num4)
3.Develop a Python Program scripts to calculate the median, mode, variance and standard deviation of a list 
of number.
import math
n=int(input("Enter the number of elements: "))
print("enter",n,"elements into list: ")
n_num=[]
for i in range(0,n):
 ele=int(input())
 n_num.append(ele)
sum1=0
for b in range(0,n):
 sum1=sum1+n_num[b]
mean=sum1/n
print("Mean is : ",mean)
if n%2==0:
 median1=n_num[n//2]
 median2=n_num[n//2-1]
 median=(median1+median2)/2
else:
 median=n_num[n//2]
print("Median is : ",median)
sum_dev=0
for x in n_num:
 sum_dev=sum_dev+(x-mean)**2
variance=sum_dev/n
print("Variance is : ",variance)
std_dev=math.sqrt(variance)
print("Standard Deviation is : ",std_dev)
position=0
largestCount=0
while(position<n):
 count=n_num.count(n_num[position])
 if(count>largestCount):
 largestCount=count
 valuePosition=n_num[position]
 position+=count
m=valuePosition
print("Mode is:",m)
4.Develop a Python Program for checking ifa given n digit number is palindrome or not [hint: input 1221 
output: Palindrome, Use // and % operator]
n=int(input("Enter a Number"))
l=0
temp=n
while(n>0):
 n=n//10
 l=l+1
n=temp
rev=0
for i in range(0,l):
 dig=n%10
 rev=rev*10+dig
 n=n//10
if(temp==rev):
 print("The Number is a Palindrome")
else:
 print("The Number is not a Palindrome")
5.Develop a python Program to display a multiplication table for a given integer.
n=int(input("Enter a Number"))
m=n
for i in range(1,11):
 m=n*i
 print(n," * ",i," = ",m)
6.Develop a python script to rotate right about a given position in that and display them [hint: input 
(10,20,30,40,50,) position: 2, output(40,50,10,20,30)]
n=int(input("Enter the number of elements: "))
print("Enter ",n,"elements into the list: ")
origlist=[]
for i in range(0,n):
 ele=int(input())
 origlist.append(ele)
pos=int(input("Enter the position to rotate right: "))
newpos=pos%len(origlist)
print("newpos= ",newpos)
rotated_list=origlist[-newpos:]+origlist[:-newpos]
print("Original list: ",origlist)
print("Rotated list to the right about position ",pos,":",rotated_list)
7.Develop a python script to interchange the digits of a given integer number [hint: intput(23456), 
interchange(3 and 5), output(25436)]
number=int(input("Enter an integer number "))
digit1=int(input("Enter the first digit to interchange: "))
digit2=int(input("Enter the second digit to interchange: "))
digits=[int(d) for d in str(number)]
index1=digits.index(digit1)
index2=digits.index(digit2)
digits[index1],digits[index2]=digits[index2],digits[index1]
result=int(''.join(map(str,digits)))
print("The number with interchanged Digits is: ",result)
8.Develop a python process to capitalize a given list of strings[hint: input(hello, good, how, simple), output( 
Hello, Good, How, Simple)
strings_list=input("Enter a list seperated by spaces: ").split()
capitalized_list=[]
for string in strings_list:
 first_letter=string[0].upper()
 capitalized_string=first_letter+string[1:]
 capitalized_list.append(capitalized_string)
print("Original list of Strings: ",strings_list)
print("Capitalized list of strings: ",capitalized_list)
9.Using a Dictionary, Develop a python program to determine and print the no. of duplicate words in a 
sentence.
user_sentence=input("Enter a sentence: ")
words=user_sentence.split()
word_frequency={}
for word in words:
 word_lower=word.lower()
 word_frequency[word_lower]=word_frequency.get(word_lower,0)+1
print("Duplicate word and their frequencies: ")
for word,frequency in word_frequency.items():
 if frequency>1:
 print(f"{word}:{frequency}")
10.Develop a python program to read numpy array and print row(sum, mean, std) and column( sum, mean, 
std)
import numpy as np
rows=int(input("Enter the number of rows: "))
cols=int(input("Enter the number of columns: ")) 
my_array=np.empty((rows,cols))
for i in range (rows):
 for j in range (cols):
 my_array[i][j]=float(input(f"Enter the elements of each position ({i+1},{j+1}): "))
row_sum=np.sum(my_array,axis=1)
row_mean=np.mean(my_array,axis=1)
row_std=np.std(my_array,axis=1)
col_sum=np.sum(my_array,axis=0)
col_mean=np.mean(my_array,axis=0)
col_std=np.std(my_array,axis=0)
print("Row statistics: ")
for i in range (my_array.shape[0]):
 print(f"Row{i+1}: Sum={row_sum[i]} Mean={row_mean[i]} Std={row_std[i]}")
print("Coloumn statistics: ")
for j in range (my_array.shape[1]):
 print(f"Column{j+1}: Sum={col_sum[j]} Mean={col_mean[j]} Std={col_std[j]}")
11.Develop a python program to read and print in the console CSV file
import csv
file_path='CSVFile.csv'
try:
 with open(file_path,'r') as csv_file:
 reader=csv.reader(csv_file)
 headers= next(reader)
 print("Headers :",headers)
 for row in reader:
 print(row)
except FileNotFoundError:
 print(f"File Not Found: {file_path}")
CSV File 
Step1: Create new notebook in jupyter
Step 2: Save as text document 
Step 3: Replace all text with following text(change values as needed)
Stpe 4: Again save as but this time rename to .csv
This should be the output
Step 5: Change the file name in your code and done
12.Develop a python program to read a HTML file with basic tags and construct a dictionary and display 
the same in console.
html_file_path="HTML.html"
with open(html_file_path,'r',encoding='utf-8') as file:
 html_content=file.read()
tags_dict={}
current_tag=None
for char in html_content:
 if char=='<':
 current_tag=""
 elif char=='>':
 if current_tag:
 tag_parts=current_tag.split()
 tag_name=tag_parts[0]
 tag_attrs=tag_parts[1:]
 if tag_name not in tags_dict:
 tags_dict[tag_name]=[]
 tags_dict[tag_name].append(tag_attrs)
 current_tag=None
 elif current_tag is not None:
 current_tag+=char
print("Tags Dictionary : ")
for tag_name,tag_info_list in tags_dict.items():
 print(f"\n<{tag_name}>:")
 for tag_info in tag_info_list:
 print(tag_info)
HTML File
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset"UTF-8">
<meta name="viewport" content="width=width-device,initail-scale=1.0">
<style>
h1{
color=#333;
}
</style>
</head>
<p>this is a sample HTML file with basic tags and attributes</p>
<a href="https://www.example.com" target="_blank">Visit examle.com</a>
</html>
