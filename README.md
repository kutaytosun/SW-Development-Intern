# SW-Development-Intern
# Question 3
def isPrime(num):
    flag = True
    if num > 1:
        for i in range(2, num):
            if (num % i) == 0:
                flag = False
                break
    return flag


def maxPathSum(tri,m,n):
    for i in range(m - 1, -1, -1):
        for j in range(i + 1):
            if (tri[i + 1][j] > tri[i + 1][j + 1]):
                tri[i][j] += tri[i + 1][j]
            else:
                tri[i][j] += tri[i + 1][j + 1]

    return tri[0][0]


tri = [[1, 0, 0, 0],
       [8, 4, 0, 0],
       [2, 6, 9, 0], [8, 5, 9, 3]]

print(maxPathSum(tri,2,2))
