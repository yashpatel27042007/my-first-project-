
from pathlib import Path
import os 

def createfile():
    try:
     name = input ("enter your file name is :")
     path = Path (name)
     if not path.exists ():
        with open (path,"w") as fd:
            data = input ("enter your information :")
            fd.write(data) 
        print ("YOUR FILE IS SUCCESSFULLY CREATED")

     else :
        print ("SORRY ! AN ERROR AS OCCURED already this name file exist")
    except Exception as err :
        print (f"an error as occured {err}")
    

def readfile():
    try:
     name = input ("enter your name is :")
     path = Path (name)
     if path.exists():
        with open (path,"r") as fd :
         content = fd.read()
         print (f"THE CONTENT OF THE FILE IS : \n {content}")
     else :
       print ("an error occured no such file exist ")

    except Exception as err:
       print (f"an error occured as {err}")
       

def updatefile():
   try:
      name = input ("enter your name is :")
      path = Path (name)

      if path.exists():
         print ("perform operations")
         print ("Press 1. for remaning the file name ")
         print ("Press 2. for append or adding the content")
         print ("Press 3. for overwriting the content")

         choice = int (input ("enter your choice is :"))

         if (choice ==1):
            newname = input ("enter your newname is :")
            new_path = Path (newname)
            if not new_path.exists():
               path.rename (new_path) 
            else :
               print ("file is already exist")
         elif choice ==2 :
            name =  input ("enter your name is :")
            path = Path (name) 
            with open (path,"a") as fd:
               content = input ("write what you want")
               fd.write("\n"+content)
            print ("successfully added")

         elif choice == 3 :
            name = input ("enter your name is :")
            path = Path (name)

            with open (path,"w") as fd:
               content = input ("write what you want")
               fd.write("\n"+content)
            print ("sucessfully added")

   except Exception as err :
      print (f"an error occured {err}")
   

    
def deletefile ():
    try :
     name = input ("enter your file name is :")
     path = Path (name)
     if path.exists():
       path.unlink()
       print ("your file is suucessfully deleted")
     else :
        print ("sorry this file name doesn't exist")
    except Exception  as err:
       print ("AN ERROR OCCURED {err}")

print ("press 1 for creating a file ")

print ("press 2 for reading a file ")

print ("press 3 for updating a file")

print ("press 4 for deleting a file")

user = int (input ("enter your response :"))

if (user==1):
    createfile()

if (user ==2):
    readfile()

if (user==3):
    updatefile()

if (user==4):
    deletefile()


