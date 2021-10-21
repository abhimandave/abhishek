#abhishek
#roll no's of students who play cricket football and badminton

def inter(l1,l2):
    l3=[]
    for v in l1:
        if v in l2:
            l3.append(v)
    return l3
def union(l1,l2):
    l3=l1.copy()
    for v in l2:
        if v not in l3:
            l3.append(v)
    return l3
def diff(l1,l2):
    l3=[]
    for v in l1:
        if v not in l2:
            l3.append(v)
    return l3
def sym(l1,l2):
    d1=diff(l1,l2)
    print("difference between cricket and badminton:",d1)
    d2=diff(l2,l1)
    print("difference between badminton and cricket: ",d2)
    l3=union(d1,d2)
    return l3
def cb(l1,l2):
    l3=inter(l1,l2)
    print("\n students who play both cricket and badminton: ",l3)
    return len(l3)
def corb(l1,l2):
    l3=sym(l1,l2)
    print("\nList of students who play either cricket or badminton but not both is : ", l3)
    return len(l3)

def ncnb(l1,l2,l3):
    l4=diff(l1,union(l2,l3))
    print("\n students  who play neither cricket nor badminton is: ",l4)
    return len(l4)
def candfnb(l1,l2,l3):
    l4=diff(inter(l1,l2),l3)
    print("\n\nList of students who play cricket and football but not badminton is : ",l4)
    return len(l4)
def removeDuplicate(d):
    l=[]
    for i in d:
        if i not in l:
            l.append(i)
    return l


compss= []
n = int(input("\nEnter number of students in COMPSS: "))
print("Enter the roll nos. of",n,"students (Please press ENTER after entering each students name) :")
for i in range(0, n):
    e = input()
    compss.append(e)  # adding the element
print("Original list of students in SEComp : " ,compss)

cricket=[]
n = int(input("\n\nEnter number of students who play cricket : "))
print("Enter the names of",n,"students who play cricket (Please press ENTER after entering each students name) :")
for i in range(0, n):
    e = input()
    cricket.append(e)  # adding the element
print("Original list of students playing cricket is :" +str(cricket))
cricket=removeDuplicate(cricket)
print("The list of students playing cricket after removing duplicates : " +str(cricket))

Football = []
n = int(input("\n\nEnter number of students who play football : "))
print("Enter the name of",n,"students who play football (Please press ENTER after entering each students name) :")
for i in range(0, n):
    e = input()
    Football.append(e)  # adding the element
print("Original list of students playing football :" +str(Football))
Football=removeDuplicate(Football)
print("The list of students playing football after removing duplicates : " +str(Football))

Badminton = []
n = int(input("\n\nEnter number of students who play badminton : "))
print("Enter the name of",n,"students who play badminton (Please press ENTER after entering each students name) :")
for i in range(0, n):
    e = input()
    Badminton.append(e)  # adding the element
print("Original list of students playing badminton :" +str(Badminton))
Badminton=removeDuplicate(Badminton)
print("The list of students playing badminton after removing duplicates : " +str(Badminton))

f=1
while f==1:
    print("\n\n--------------------MENU--------------------\n")
    print("1. List of students who play both cricket and badminton")
    print("2. List of students who play either cricket or badminton but not both")
    print("3. List of students who play neither cricket nor badminton")
    print("4. Number of students who play cricket and football but not badminton")
    print("5. Exit\n")
    ch=int(input("Enter your Choice (from 1 to 5) :"))

    if ch==1:
        print("Number of students who play both cricket and badminton : ", cb(cricket,Badminton))
        a = input("\n\nDo you want to continue (yes/no) :")
        if a == "yes":
            f = 1
        else:
            f = 0
            print("exit program!")

    elif ch==2:
        print("Number of students who play either cricket or badminton but not both : ", corb(cricket, Badminton))
        a = input("\n\nDo you want to continue (yes/no) :")
        if a == "yes":
            f = 1
        else:
            f = 0
            print("exit program!")

    elif ch==3:
        print("Number of students who play neither cricket nor badminton : ", ncnb(compss,cricket,Badminton))
        a = input("\n\nDo you want to continue (yes/no) :")
        if a == "yes":
            f = 1
        else:
            f = 0
            print("exit program!")

    elif ch==4:
        print("Number of students who play cricket and football but not badminton : ", candfnb(cricket,Football,Badminton))
        a = input("\n\nDo you want to continue (yes/no) :")
        if a == "yes":
            f = 1
        else:
            f = 0
            print("exit program!")

    elif ch==5:
        f=0
        print("exit program!")

    else:
        print("!!Wrong Choice!! ")
        a=input("\n\nDo you want to continue (yes/no) :")
        if a=="yes":
            f=1
        else:
            f=0
            print("exit program!")















