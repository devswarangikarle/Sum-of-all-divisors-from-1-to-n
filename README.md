# Sum-of-all-divisors-from-1-to-n
Given a positive integer N. The task is to find the value of Σi from 1 to N F(i) where function F(i) for the number i is defined as the sum of all divisors of i.

def sum_of_divisors(n):
    result = 0

    for i in range(1, n + 1):
        result += sum_of_divisors_for_number(i)

    return result

def sum_of_divisors_for_number(num):
    result = 0
    i = 1

    while i * i <= num:
        if num % i == 0:
            result += i

            if num // i != i:
                result += num // i

        i += 1

    return result


n = int(input())


print(sum_of_divisors(n))
