from random import randint

class Hero():
    def __init__(self, name, health, armor, power):
        self.name = name
        self.health = health
        self.armor = armor
        self.power = power
        self.new = True

    def print_info(self):
        print('Уровень здоровья:', self.health)
        print('Уровень брони:', self.armor)

    def check_alive(self):
        if self.health <= 0:
            return False
        else:
            return True

    def strike(self, enemy):
        enemy.armor = enemy.armor - self.power
        if enemy.armor < 0:
            enemy.health += enemy.armor
            enemy.armor = 0
            if enemy.health <= 0:
                enemy.health = 0

class Warrior (Hero):
    def hello(self):
        if self.new == True:
            print('-> НОВЫЙ ГЕРОЙ! Из глубины леса появляется искусный воин', self.name)
        else:
            print('Снова появляется', self.name)
    def attack(self, enemy):
        print(self.name,'бесстрашно набрасывается на',enemy.name)
        print('Результат схватки для', self.name)
        self.print_info()
        print('Результат схватки для', enemy.name)
        enemy.print_info()
class Dragon (Hero):
    def hello(self):
        if self.new == True:
            print('-> НОВЫЙ ГЕРОЙ! С неба спускается свирепый дракон', self.name)
        else:
            print('И вновь перед нами разъярённый дракон', self.name)
    def attack(self, enemy):
        print(self.name,'направляет поток смертельного огня',enemy.name)
        print('Результат схватки для', self.name)
        self.print_info()
        print('Результат схватки для', enemy.name)
        enemy.print_info()

knight = Warrior ('Ричард', 50, 25, 20)
answer = input(f'Приветствуем тебя, славный рыцарь {knight.name}.\n Ты стоишь у входа в лес, полный смертельных опасностей.\n Готов ли ты войти внутрь и сразиться с врагами (да/нет)?').lower()
if answer == 'да':
    play = True
    print('***Да начнётся битва!***')
else:
    play = False
    print('Тут и сказочке конец')
enemies = []
enemies.append(Warrior('Питер', randint(20,50), randint(20,50), randint(20,50)))
enemies.append(Warrior('Сержио', randint(20,50), randint(20,50), randint(20,50)))
enemies.append(Dragon('Дрогон', randint(20,50), randint(20,50), randint(20,50)))
enemies.append(Dragon('Визерион', randint(20,50), randint(20,50), randint(20,50)))
while play:
    enemy = enemies[randint(0,3)]
    enemy.hello()
    enemy.print_info()
    answer1 = input('Вступить в бой (да/нет)?').lower()
    if answer1 == 'да':
        if randint(0,1)==1:
            knight.strike(enemy)
            knight.attack(enemy)
        else:
            enemy.strike(knight)
            enemy.attack(knight)
            
    if enemy.check_alive() == False:
        print(enemy.name, 'погиб')
        enemies.remove(enemy)
    if knight.check_alive() == False:
        print(knight.name, 'погиб')
        play = False
    if len(enemies) == 0:
        print(knight.name, 'победил всех')
        play = False
print('Тут и сказочке конец')
