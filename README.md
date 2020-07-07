# mycode-akhi
def last_reading(n:int) ->int:
    return int(digits[-n:])
#print(last_reading(3))

def is_valid(n:int) -> bool:

    return int("".join(sorted(set(str(n))))) == n
#print(is_valid(122))


def next_reading(n:int) -> int:

    if last_reading(len(str(n))) == n:
        return first_reading(len(str(n)))
    else:
        while n > 0:
            n += 1
            if is_valid(n):
                return n


#print(next_reading(123))


def next_nth_reading(n:int,step:int) -> int:
    for _ in range(step):
        n = next_reading(n)
    return n
def distance(r1:int,r2:int) -> int:
    if len(str(r1)) != len(str(r2)):
        print("uncomparable odometers")
    dist = 0

    while r1 != r2:
        r1 = next_reading(r1)
        dist += 1
    return dist
print(distance(123,145))


print(next_nth_reading(123,13))
