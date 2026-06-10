# File-Handling-Project
A basic python project for begineer 

from pathlib import Path

 
def CreateFile() :
    try :
        name = input("Enter File Name -> ")
        path = Path(name)
        if not path.exists() :
            with open(path, "w") as file :
                data = input("Enetr Data -> ")
                file.write(data)
            print("file created successfully")
        else :
            print("file already exsits")
    except Exception as err :
       print(f"An error occured {err}")

def ReadFile():
    try :
        name = input("Enter file name -> ")
        path = Path(name)
        if path.exists() :
            with open(path, "r") as file :
                data = file.read()
            print(f"Your Data is :\n{data}")
        else :
            print("An error occurred no such file exists")
    except Exception as err :
        print(f"An error {err}")



def UpdateFile() :
    try :
        name = input("Enter file name -> ")
        path = Path(name)
        if path.exists() :
            print("Options")
            print("1. File name change")
            print("2. Append content in file")

  choice = int(input("Enter your choice -> "))

            if choice == 1 :
                newname = input("Enter new name of file -> ")
                newpath = Path(newname)
                if not newpath.exists(): 
                     data = path.rename(newpath)
                print("Successfully renamed!")

            if choice == 2 :
                with open(path , "a") as file :
                    data = input("Enter data to append -> ")
                    file.write(data)
                    print("Data successfully appeened!")
            else :
                ("File does not exists")
    except Exception as err :
        print(f"an error occured {err}")

                            
def DeleteFile() :
    try :
        name = input("Enter file name -> ")
        path = Path(name)
        if path.exists() :
            path.unlink()
                                
        else :
            ("File not exists")
    except Exception as err :
        print(f"an error occured {err}")
                
            
        




while True :

    print("1. Create a File -> ")
    print("2. Read a File -> ")
    print("3. Update a File -> ")
    print("4. Delet a File -> ")
    print("5. Exit")

    user = int(input("Enter you choice -> "))

    if user == 1 :
        CreateFile()

    elif user == 2 :
        ReadFile()

    elif user == 3 :
        UpdateFile()

    elif user == 4 :
        DeleteFile()
    
    elif user == 5 :
        break

    else :
        print("Inavlid Number")
