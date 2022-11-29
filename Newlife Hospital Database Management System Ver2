#Holiday Homework Computer Science Project by Divyalakshmi (12A) 

#Topic- Hospital Management System Database
#The following is the program for the creation of the Menu Design and the functioning of the same.

################################ [IMPORTING] ##########################################################################
import pickle as pic
import os
################################ [FUNCTION 1] #########################################################################
def ViewRecord(pt_ID):
    f = open("PatientRecords.dat", 'rb')
    found = 0
    try:
        while True:
            ptrec = pic.load(f)
            if ptrec[0] == pt_ID:
                pt_name = ptrec[1]
                pt_char = ptrec[2]
                pt_stat = ptrec[3]
                found = 1
    except:
        pass
    
    if found == 1:
        print('Patient ID: ', pt_ID)
        print('Patient Name: ', pt_name)
        print('Charge/Bill Amount: ', pt_char)
        print('Status: ', pt_stat)
    elif found == 0:
        print('Patient Record not found!')
    f.close()
    
################################ [FUNCTION 2] #########################################################################
 
def AddRecord(pt_ID):
    f = open ('PatientRecords.dat', 'rb')
    found = 0
    try:
        while True:
            ptrec = pic.load(f)
            if ptrec[0] == pt_ID:
                found = 1
    except:
        pass
    f.close()
    
    if found == 1:
        print('This Patient ID already exists! Try again')
    elif found == 0:
        f = open('PatientRecords.dat', 'ab')
        pt_name= (input('Please Enter Patient Name: '))
        pt_char= int(input('Please Enter Charge/Bill Amount: '))
        pt_stat= (input('Please Enter Patient Status: '))
        ptnewrec = [pt_ID, pt_name, pt_char, pt_stat]
        pic.dump(ptnewrec, f)
        print('Patient Record Added!')
        f.close()

####################################################### [FUNCTION 3] ##################################################

def ModifyRecord(pt_ID):
    f1 = open ('PatientRecords.dat', 'rb')
    f2 = open('TempPatientRecords.dat', 'wb')
    found = 0
    
    try:
        while True:
            ptrec = pic.load(f1)
            if ptrec[0] == pt_ID:
                pt_ID = ptrec[0]
                pt_name = ptrec[1]
                pt_char = ptrec[2]
                pt_stat = ptrec[3]
                print('Patient Name: ', pt_name)
                ques_name = input('Modify Patient Name? (yes/no): ')
                
                if ques_name in ('Yes', 'yes'):
                    mod_name = input("Enter Patient's New Name: ")
                    new_ptrec = [pt_ID, mod_name, pt_char, pt_stat]
                    found = 1
                    print('Charge/Bill Amount: ', pt_char)
                    ques_char = input('Modify Charge/Bill Amount? (yes/no): ')
                    
                    
                    if ques_char in ('Yes', 'yes'):
                        mod_char = int(input("Enter New Charge/Bill Amount: "))
                        new_ptrec = [pt_ID, mod_name, mod_char, pt_stat]
                        print('Status: ', pt_stat)
                        ques_stat = input('Modify Status? (yes/no): ')
                    
                        if ques_stat in ('Yes', 'yes'):
                            mod_stat = int(input("Enter New Status: "))
                            new_ptrec = [pt_ID, mod_name, mod_char, mod_stat]
                            pic.dump(new_ptrec, f2)
                            
                        
                        elif ques_stat in ('No', 'no'):
                            new_ptrec = [pt_ID, mod_name, mod_char, pt_stat]
                            pic.dump(new_ptrec, f2)
                                         
                                         
                    elif ques_char in ('No', 'no'):
                        print('Status: ', pt_stat)
                        ques_stat = input('Modify Status? (yes/no): ')
                        
                        if ques_stat in ('Yes', 'yes'):
                            mod_stat = int(input("Enter New Status: "))
                            new_ptrec = [pt_ID, mod_name, pt_char, mod_stat]
                            pic.dump(new_ptrec, f2)


                        elif ques_stat in ('No', 'no'):
                            new_ptrec = [pt_ID, mod_name, pt_char, pt_stat]
                            pic.dump(new_ptrec, f2)
       
                            
                elif ques_name in ('No', 'no'):
                    print('Charge/Bill Amount: ', pt_char)
                    ques_char = input('Modify Charge/Bill Amount? (yes/no): ')
                    
                    if ques_char in ('Yes', 'yes'):
                        mod_char = int(input("Enter New Charge/Bill Amount: "))
                        new_ptrec = [pt_ID, pt_name, mod_char, pt_stat]
                        found = 1
                        print('Status: ', pt_stat)
                        ques_stat = input('Modify Status? (yes/no): ')
                        
                    
                        if ques_stat in ('Yes', 'yes'):
                            mod_stat = int(input("Enter New Status: "))
                            new_ptrec = [pt_ID, pt_name, mod_char, mod_stat]
                            pic.dump(new_ptrec, f2)
                            
                        
                        elif ques_stat in ('No', 'no'):
                            new_ptrec = [pt_ID, pt_name, mod_char, pt_stat]
                            pic.dump(new_ptrec, f2)
                            
                            
                    elif ques_char in ('No', 'no'):
                        print('Status: ', pt_stat)
                        ques_stat = input('Modify Status? (yes/no): ')
                        
                        if ques_stat in ('Yes', 'yes'):
                            mod_stat = int(input("Enter New Status: "))
                            new_ptrec = [pt_ID, pt_name, pt_char, mod_stat]
                            pic.dump(new_ptrec, f2)
                            found = 1
                    
                        elif ques_stat in ('No', 'no'):
                            new_ptrec = [pt_ID, pt_name, pt_char, pt_stat]
                            pic.dump(new_ptrec, f2)
                break
                            
    except:
       pass
    
    try:
        while True:
            ptrec = pic.load(f1)
            if ptrec[0] != pt_ID:
                pic.dump(ptrec, f2)
    except:
        pass
    
    if found == 1:
        f1.close()
        f2.close()
        os.remove('PatientRecords.dat')
        os.rename('TempPatientRecords.dat', 'PatientRecords.dat')
        print('Record is modified!')
    elif found == 0:
        print('No records modified!')
                
################################################# [FUNCTION 4] ########################################################

def DeleteRecord(pt_ID):
    f1 = open ('PatientRecords.dat', 'rb')
    f2 = open('TempPatientRecords.dat', 'wb')
    
    found = 0
    try:
        while True:
            ptrec = pic.load(f1)
            if ptrec[0] != pt_ID:
                pic.dump(ptrec, f2)
                found = 1
    except:
        pass
    if found == 1:
        f1.close()
        f2.close()
        os.remove('PatientRecords.dat')
        os.rename('TempPatientRecords.dat', 'PatientRecords.dat')
        print('The following patient record was deleted:')
        print('Patient ID: ', pt_ID)
        print('Patient Name: ', ptrec[1])
        print('Charge/Bill Amount: ', ptrec[2])
        print('Status: ', ptrec[3])
        
    else:
        print('No such record found!')
        
################################################## [FUNCTION 5] #######################################################

def AdmitPatient(pt_ID):
    f1 = open('PatientRecords.dat', 'rb')
    f2 = open('TempPatientRecords.dat', 'wb')
    found = 0
    
    try:
        while True:
            ptrec = pic.load(f1)
            
            if pt_ID == ptrec[0]:
                pt_name = ptrec[1]
                pt_char = ptrec[2]
                pt_stat = ptrec[3]
                print('Patient ID: ', pt_ID)
                print('Patient Name: ', pt_name)
                print('Charge/Bill Amount: ', pt_char)
                print('Status: ', pt_stat)

                if pt_stat == 'Admitted':
                    print('The patient has already been admitted!')
                    break

                elif pt_stat == 'Discharged':
                    Adm = 0
                    found = 1
                    ques_admit = input('Do you want to admit the patient? (yes/no): ')
                    if ques_admit in ('Yes', 'yes'):
                        new_stat = 'Admitted'
                        new_ptrec = [pt_ID, pt_name, pt_char, new_stat]
                        pic.dump(new_ptrec, f2)
                        Adm = 1
                    elif ques_admit in ('No', 'no'):
                        Adm = 0      
                break 
    except:
        pass
    
    try:
        while True:
            ptrec = pic.load(f1)
            if ptrec[0] != pt_ID:
                pic.dump(ptrec, f2)
    except:
        pass
    
    if found == 1:
        f1.close()
        f2.close()
        os.remove('PatientRecords.dat')
        os.rename('TempPatientRecords.dat', 'PatientRecords.dat')
        if Adm == 1:
            print('The patient has been Admitted now!')
        
        elif Adm == 0:
            print('The patient has NOT been admitted')

################################################### [FUNCTION 6] ######################################################

def DischargePatient(pt_ID):
    f1 = open('PatientRecords.dat', 'rb')
    f2 = open('TempPatientRecords.dat', 'wb')
    found = 0
    
    try:
        while True:
            ptrec = pic.load(f1)
            
            if pt_ID == ptrec[0]:
                pt_name = ptrec[1]
                pt_char = ptrec[2]
                pt_stat = ptrec[3]
                print('Patient ID: ', pt_ID)
                print('Patient Name: ', pt_name)
                print('Charge/Bill Amount: ', pt_char)
                print('Status: ', pt_stat)

                if pt_stat == 'Discharged':
                    print('The patient has already been discharged!')
                    break

                elif pt_stat == 'Admitted':
                    Disch = 0
                    found = 1
                    
                    ques_disch = input('Do you want to discharge the patient? (yes/no): ')
                    if ques_disch in ('Yes', 'yes'):
                        new_stat = 'Discharged'
                        new_ptrec = [pt_ID, pt_name, pt_char, new_stat]
                        pic.dump(new_ptrec, f2)
                        Disch = 1
                        
                    elif ques_disch in ('No', 'no'):
                        Disch = 0      
                break 
    except:
        pass
    
    try:
        while True:
            ptrec = pic.load(f1)
            if ptrec[0] != pt_ID:
                pic.dump(ptrec, f2)
    except:
        pass
    
    if found == 1:
        f1.close()
        f2.close()
        os.remove('PatientRecords.dat')
        os.rename('TempPatientRecords.dat', 'PatientRecords.dat')
        if Disch == 1:
            print('The patient has been Discharged now!')
        
        elif Disch == 0:
            print('The patient has NOT been Discharged')

################################################ [MAIN PROGRAM + MENU] ################################################
    
optn = 0
while optn!=7:
    print()
    print('_________________________________________________________________')
    print('|                                                               |')
    print('|%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%|')
    print('|                 NEWLIFE GROUP OF HOSPITALS                    |')
    print('|                  Where Care Comes First...                    |')
    print('|  $$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$    |')
    print('|                       DATABASE MENU                           |')
    print('|                                                               |')
    print('| Choose one of the following options to access Patient Records |')
    print('|   *************************** | *************************     |')
    print('|      MAINTENANCE              |     TRANSACTION               |')
    print('|    1 - VIEW                   |  5 - ADMIT                    |')
    print('|    2 - ADD                    |  6 - DISCHARGE                |')
    print('|    3 - MODIFY                 |  7 - EXIT                     |')
    print('|    4 - DELETE                 |                               |')
    print('|   *************************** | *************************     |')
    print('|  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@    |')
    print('|                                                               |')
    print('|            >>>>>>>  By- Divyalakshmi(12A)  <<<<<<<            |')
    print('|                                                               |')
    print('|%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%|')
    print('|_______________________________________________________________|')
    
    optn = int(input('Enter Your Choice: '))
    
    import pickle as pic
    f = open("PatientRecords.dat", 'ab')
    ptrec1 = [1001, 'Ramesh Raman', 450, 'Admitted']
    ptrec2 = [1002, 'Samuel Raj', 560, 'Admitted']
    ptrec3 = [1003, 'Adhavan Menon', 800, 'Discharged']
    ptrec4 = [1004,'Harry Jackson', 500, 'Admitted']
    ptrec5 = [1005, 'Peter Jones', 350, 'Discharged']
    ptrec6 = [1006, 'Maxwell Smith', 400, 'Discharged']
    ptrec7 = [1007, 'Yash Chopra', 500, 'Discharged']
    ptrec8 = [1008, 'Suresh Gopal', 450, 'Admitted']
    ptrec9 = [1009, 'Krishna Sekar', 750,'Admitted']
    ptrec10 = [1010, 'Bindu Raj', 400, 'Discharged']
    pic.dump(ptrec1,f)
    pic.dump(ptrec2,f)
    pic.dump(ptrec3,f)
    pic.dump(ptrec4,f)
    pic.dump(ptrec5,f)
    pic.dump(ptrec6,f)
    pic.dump(ptrec7,f)
    pic.dump(ptrec8,f)
    pic.dump(ptrec9,f)
    pic.dump(ptrec10,f)
    f.close()
    
    if optn == 1:
        pt_ID = int(input('Please Enter Patient ID: '))
        ViewRecord(pt_ID)
        
    if optn == 2:
        pt_ID = int(input('Please Enter Patient ID: '))
        AddRecord(pt_ID)
        
    if optn == 3:
        pt_ID = int(input('Please Enter Patient ID: '))
        ModifyRecord(pt_ID)
        
    if optn == 4:
        pt_ID = int(input('Please Enter Patient ID: '))
        DeleteRecord(pt_ID)
        
    if optn == 5:
        pt_ID = int(input('Please Enter Patient ID: '))
        AdmitPatient(pt_ID)
        
    if optn == 6:
        pt_ID = int(input('Please Enter Patient ID: '))
        DischargePatient(pt_ID)
                
    if optn == 7:
        break
