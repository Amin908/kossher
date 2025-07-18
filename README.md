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
