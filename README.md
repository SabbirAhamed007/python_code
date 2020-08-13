def getdatetime():
    import datetime
    return datetime.datetime.now()

def callCopayAssistance():
    print("Welcome to Copay Assistance Service\n");
    operation = ("rectiv", "Write")
    user = ("Sabbir", "Jack", "Jenny")
    log = ("Allergan", "Amgen_First_Step", "BioOncology", "Bioverative", "Cimzia", "Entivio", "Esbriet", "Evenity", "Hemlibra", "Inflectra", "Injectafer", "Insmed", "Lucentis", "Macrilen",)

    while True:
        n1 = input("What you want to do\nPress 1 for rectiv, 2 for write:\n")
        if int(n1) == 1 or int(n1) ==2:
            while True:
                n2 = input("Press 1 for Sabbir, Press 2 for Jack, and 3 for Jenny:\n ")
                if int(n2) == 1 or int(n2) == 2 or int(n2) == 3:
                    while True:
                        n3 = input("Press 1 for Allergan, Press 2 for Amgen_First_Step, Press 3 for BioOncology, Press 4 for Bioverative, Press 5 for Cimzia, Press 6 for Entivio, Press 7 for Esbriet, Press 8 for Evenity, Press 9 for Hemlibra, Press 10 for Inflectra, Press 11 for Insmed, Press 12 for Lucentis, Press 13 for Macrilen:\n")
                        if int(n3) == 1 or int(n3) == 2 or int(n3) == 3 or int(n3) == 4 or int(n3) == 5 or int(n3) == 6 or int(n3) == 7 or int(n3) == 8 or int(n3) == 9 or int(n3) == 10 or int(n3) == 11 or int(n3) == 12 or int(n3) == 13:
                            filename = user[int(n2) - 1] + "_" + log[int(n3) - 1] + ".txt"
                            if int(n1) == 2:
                                n4 = input("What " + log[int(n3) - 1] + " by " + user[int(n2) - 1] + ":\n")
                                with open(filename, "a+") as f:
                                    f.write("[" + str(getdatetime()) + "] " + n4 + "\n")
                                    print("details logged successfully")

                            else:
                                try:
                                    with open(filename,"rt") as f:
                                        filecontent = f.read()
                                        print (filecontent)
                                except Exception as e:
                                    print(e)
                            break
                        else:
                            print("Wrong choice try again")
                    break
                else:
                    print("Please register the patient")
            break
        else:
            print("Wrong Operation call")

callCopayAssistance()
