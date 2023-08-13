#!/usr/bin/python3

import argparse
import random

parser = argparse.ArgumentParser(description="Generate a secure, memorable password using the XKCD method")

parser.add_argument("-w", "--words", metavar="WORDS", required=False, 
                    help="include WORDS words in the password (default=4)", default=4, type=int)
parser.add_argument("-c", "--caps", metavar="CAPS", required=False, 
                    help="capitalize the first letter of CAPS random words (default=0)", default=0, type=int)
parser.add_argument("-n", "--numbers", metavar="NUMBERS", required=False, 
                    help="insert NUMBERS random numbers in the password (default=0)", default=0, type=int)
parser.add_argument("-s", "--symbols", metavar="SYMBOLS", required=False, 
                    help="insert SYMBOLS random symbols in the password (default=0)", default=0, type=int)

args = parser.parse_args()

syms = ["~","!","@","#","$","%","^","&","*",".",":",";"]
pwlist = []

for i in range(args.words):
    file = open("words.txt", "r")
    data = file.read()
    listdata = data.split("\n")
    pwlist.append(random.choice(listdata).lower())
for i in range(args.caps):
    index = random.randint(0, len(pwlist)-1)
    pwlist[index] = pwlist[index].capitalize()
for i in range(args.numbers):
    pwlist.append(str(random.randint(0,9)))
for i in range(args.symbols):
    pwlist.append(random.choice(syms))

random.shuffle(pwlist)
print(''.join(pwlist))

    

