# taklif-8-mehr
استاد برو حال کن

#taklif_avali_va_dovomi:


list_kol = []

while True:
    esm = input("user name khod ra vared konid:")
    password = input("password khod ra vared konid:")

    if esm == "radin" and password == "1234":
        print("login")
        break
    else:
        print("user ya password eshtebahe")

nomre_py = float(input("nomre python khod ra vared konid:"))
nomre_java = float(input("nomre java khod ra vared konid:"))
nomre_html = float(input("nomre html khod ra vared konid:"))

list_kochak = []
list_kochak.append(esm)
list_kochak.append(password)
list_kochak.append(nomre_py)
list_kochak.append(nomre_java)
list_kochak.append(nomre_html)
list_kol.append(list_kochak)
print(list_kol)

avg = (nomre_html + nomre_java + nomre_py) / 3

while True:
    miyangin = input("aya myangin mikhay? 1.are    2. na")
    match miyangin:
        case "1":
            print(avg)
            break
        case "2":
            print("bye bye")
            break
#________________________________________________________________________________________________________________________________________________________________
_______________________________________________________________________________________________________________________________________________________________

#taklif_sevomi_va_chaharomi:

import random
import string

people = []
print("Esm-e afrad ro yeki yeki benevisid.")
print("Vaghti tamoom shod, faghat Enter bezanid.")
while True:
    name = input("Esm-e fard: ")
    if name == "":
        break
    people.append(name)

prizes = []
print()
print("Hala jayeze-ha ro yeki yeki benevisid (avali behtarin jayeze ast).")
print("Vaghti tamoom shod, faghat Enter bezanid.")
while True:
    prize = input("Jayeze: ")
    if prize == "":
        break
    prizes.append(prize)

print()
favorite = input("Ki jayeze-ye avval ro bebare? (agar hich kas, faghat Enter): ")
if favorite == "":
    favorite = None

if len(people) == 0 or len(prizes) == 0:
    print("List-e afrad ya jayeze-ha khali ast!")
    exit()

if favorite is not None and favorite not in people:
    print("In esm tooye list nist, pas ghore-keshi adilane anjam mishe.")
    favorite = None

winners = {}  # inja minevisim ki chi bord

if favorite in people:
    winners[favorite] = prizes[0]                      # nafar-e makhsoos, behtarin jayeze
    other_people = [p for p in people if p != favorite]
    other_prizes = prizes[1:]
else:
    other_people = people[:]
    other_prizes = prizes[:]

random.shuffle(other_people)   # makhloot kardan-e afrad
random.shuffle(other_prizes)   # makhloot kardan-e jayeze-ha

count = min(len(other_people), len(other_prizes))
for i in range(count):
    winners[other_people[i]] = other_prizes[i]

print()
print("*** Natije-ye Ghore-Keshi ***")
for person in people:
    print(person, ":", winners.get(person, "Jayeze-i nabord"))

upper = string.ascii_uppercase      # horoof-e bozorg
lower = string.ascii_lowercase      # horoof-e koochak
digits = string.digits              # adad
symbols = "!@#$%^&*"                # alayem

password = [
    random.choice(upper),
    random.choice(lower),
    random.choice(digits),
    random.choice(symbols),
]
all_chars = upper + lower + digits + symbols
while len(password) < 18:
    password.append(random.choice(all_chars))

random.shuffle(password)
print()
print("Ramz-e shoma:", "".join(password))
