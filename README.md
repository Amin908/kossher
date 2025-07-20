class car:
    def __init__(self, company, name, model, color, hp, ful_capacity):
        self.company = company
        self.name = name
        self.model = model
        self.color = color
        self.power = hp
        self.isactive = False
        self.fule_lose_per_km = 0.1
        self.fuel_capacity = ful_capacity
    def information(self):
        p = {'car_company':self.company,
             'name_of_the_car':self.name,
             'car_model':self.model, 
            'color_of_car':self.color, 
            'power_of_the_car':self.power, 
             'fuel_capasity':self.fuel_capacity}
        print(p)
    def engine_start(self, fule):
        self.fule = fule
        if (fule/self.fuel_capacity)>0.1:
            print('engine stared')
            self.isactive = True
        else:
            print('cant start the engine we need more fule!!')
    def stop_engine(self):
        if self.isactive:
            print("engine stoped")
        else:
            print('engine is already off')
    def car_move(self, km):
        if self.isactive:
            for i in range(1, km + 1):
                self.fule -= self.fule_lose_per_km
                if self.fule <= 0:
                    self.fule = 0
                    print(f"Ran out of fuel after {i} kilometers!")
                    self.stop_engine()
                    break
            else:
                print(f"We went all the {km} kilometers and we have {self.fule:.2f} liters left")
        else:
            print('Please first turn on the car') 
car_1 = car('BENZ', 'cls500', 2020, 'black', 200, 30)
car_1.information()
car_1.engine_start(10)
car_1.car_move(102)




'''

koooooooooooooooooooooooooooooosheeeeeeeeeeeeeerrrrrrrrrrrrrrrrrrrr
'''
def change_to_10(p, q):
    c = 0
    j = 0
    if q == 10:
        return p
    if q > 10:
        p = str(p)
        for i in p[::-1]:
            if i == 'a':
                c += 10 * (q ** j)
            elif i == 'b':
                c += 11 * (q ** j)
            elif i == 'c':
                c += 12 * (q ** j)
            elif i == 'd':
                c += 13 * (q ** j)
            elif i == 'e':
                c += 14 * (q ** j)
            elif i == 'f':
                c += 15 * (q ** j)
            else:
                c += int(i) * (q ** j)
            j += 1
        return c  
    else:
        while p != 0:
            a = p % 10  
            c += a * (q ** j)
            p = p // 10
            j += 1
        return c
def change_from_10_to_(f,g):
    if g <= 10:
        c = 0
        j = 0
        while f != 0:
            a = f%g
            c = c + (a*(10 ** j))
            f = f // g
            j += 1
        return c
    if g>10:
        l=''
        while f != 0:
            j = f%g
            if j == 10:
                j = 'a'
                l = j + l
            elif j == 11:
                j = 'b'
                l = j + l
            elif j == 12:
                j = 'c'
                l = j + l
            elif j == 13:
                j = 'd'
                l = j + l
            elif j == 14:
                j = 'e'
                l = j + l
            elif j == 15:
                j = 'f'
                l = j + l
            else:    
                j = str(j)
                l = j + l
            f= f//g
        return l
def return_giurts(x):
    x = str(x)
    sm = 0
    for i in x:
        if i == '0'or '6' or '9':
            sm = sm + 6
        elif i == '1':
            sm += 2
        elif i == '2' or '3' or '5':
            sm += 5
        elif i == '4':
            sm += 4
        elif i == '7':
            sm += 3
        elif i =='8':
            sm += 7
    return sm
a =int(input("enter your number :"))
a_bace = int(input("enter your number :"))
bace2 = int(input("enter your number : "))
print(change_from_10_to_(change_to_10(a, a_bace), bace2))
print(return_giurts(change_from_10_to_(change_to_10(a, a_bace), bace2)))
'''

kooooooooooooooooooooosheeeeeeeeeeeeeeeeeeer

'''
