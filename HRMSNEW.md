stud = []
ch = 'y'
c = 'y'

while c == 'y' :
    print("-----------------------------------------")
    print("Enter the choice give below : ")
    print("1. Add Record ")
    print("2. Search  Record")
    print("3. Update Record ")
    print("4. Delete Record")
    print("5. Display Record ")
    print("------------------------------------------")

    choice = int(input("Enter the choice : "))
    if choice == 1 :
        while ch == 'y' :
            print("-------------------------------------")
            r = int(input("Enter the Serial number     : "))
            n = input("Enter the Name            : ")
            p = int(input("Enter the Basic pay      : "))
            e = int(input("Enter the accomodation expense : "))
            f = int(input("Enter the food expenses : "))
            v = input("Enter the place you've visited : ")
            print("Total expense : " , p+e)
            print("-------------------------------------")
            ch  = input("do you want to add more records 'y' / YES 'n' / NO : ")
            stud_data = [r ,n ,p,e,f,v]
            stud.append(stud_data)
    elif choice == 2 :
        flag = 0
        roll = int(input("Enter the Serial number to be searched : "))
        for i in range (len(stud)) :
            if stud[i][0]==roll :
                print("Serial number : ", stud[i][0])
                print("Name : ", stud[i][1])
                print("Basic pay : ", stud[i][2])
                print("-------------------------------------")
                flag = 1
        if flag == 0 :
            print("Not Found !")
    elif choice == 3 :       
        s = len(stud)
        up = 'y'
        while up == 'y' :
            
            print(stud)
            print()
            
            roll = int(input("Search the Serial Number to be updated : "))
            flag = 0
            
            print("********** Detail are here ********** ")
            for i in range (s) :
                if stud[i][0] == roll :
                    print("Serial number : ", stud[i][0])
                    print("Name : ", stud[i][1])
                    print("Basic pay : ", stud[i][2])
                    print("-------------------------------------")
                    flag = 1
                    print("1.Serial number  2.Name  3.Basic pay ")
                    search = int(input("Enter the choice :  ")      )
                    if search == 1 :
                        if stud[i][0] == roll:
                            
                            print("Serial no: " , stud[i][0])
                            print("Name:   " , stud[i][1])
                            print("Basic pay:    " , stud[i][2])
                            print()                           
                            Nroll = int(input("Enter the new Serial no:  "))
                            stud[i][0] = Nroll
                            print("Serial no: " , stud[i][0])
                            print("Name:   " , stud[i][1])
                            print("Basic pay:    " , stud[i][2])
                            print("****record is updated*******")
                            print()
                            break
                        
                    elif search == 2 :
                        
                        Nname = input("Enter the New Name :  ")
                        stud[i][1] = Nname
                        print("********** Details are here *********")
                        print("Serialno: " , stud[i][0])
                        print("Name:   " , stud[i][1])
                        print("Basic pay :    " , stud[i][2])
                        print("****record is updated*******")
                        print()
                        break
                    
                    elif search == 3:
                        
                        Nper = int(input("Enter the New Basic pay  :  "))
                        stud[i][2] = Nper
                        print("********** Details are here *********")
                        print("Serial no: " , stud[i][0])
                        print("Name:   " , stud[i][1])
                        print("Basic pay :    " , stud[i][2])
                        print("****record is updated*******")
                        print()
                        break
                    
                    else:
                        print("Not found the option!")
                    
            up = input("Do you want to continue:  'y'  /  'n'  ")
                           
            if flag == 0:
                print("Record not found please don't retry :  ")
                break
            
    elif choice == 4 :
        
        Droll = int(input("Enter the Serial Number to delete the record : "))
        flag = 0
        
        for i in range (len(stud)) :
            if stud[i][0] == Droll :
                print("Serial no: " , stud[i][0])
                print("Name:   " , stud[i][1])
                print("Basic pay :    " , stud[i][2])
                flag = 1
                
                d = "y"
                d = input("Enter 'y' to delete the record || 'n' to cancle the deletation : ")
                
                if d == "y" :
                    stud.pop(i)
                    print("Record has been deleted ")
                break
    elif choice == 5 :
        a = int(input("Select the choice  1. All Records 2. Individual Records : "))
        if a == 1 :            
            for i in range (len(stud)) :            
                print("-------------------------------------")
                print("Serial number : ", stud[i][0])
                print("Name : ", stud[i][1])
                print("Basic pay : ", stud[i][2])
                print("-------------------------------------")
        elif a == 2 :
            flag = 0
            roll = int(input("Enter the Serial number to be searched : "))
            for i in range (len(stud)) :
                if stud[i][0]==roll :
                    print("Serial number : ", stud[i][0])
                    print("Name : ", stud[i][1])
                    print("Basic pay : ", stud[i][2])
                    print("-------------------------------------")
                    flag = 1
            if flag == 0 :
                print("Not Found !")
