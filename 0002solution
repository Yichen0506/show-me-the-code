# coding=utf-8
import MySQLdb
import random
import string

Voucher = string.ascii_letters + string.digits

f = open('voucher.txt', 'w')

for x in range(200):
    result = ""
    for y in range(20):
        result += random.choice(Voucher)
    f.write(result + '\n')
    print(result)

f.close()


def save_code():
    conn = MySQLdb.connect(host="localhost", user="root", passwd="123456", db="pythontest")
    cursor = conn.cursor() # connect the cursor with python

    with open('voucher.txt', 'r') as collect:
        codes = collect.readlines() # codes here is a list actually
        for i in range(200):
            cursor.execute("insert into code values('%d','%s')" %(i, codes[i]))

    conn.commit() # store this operation
    cursor.close() # finish this connection


if __name__ == '__main__':
    save_code()
