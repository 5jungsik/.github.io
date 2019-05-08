---
title: "Welcome to Jekyll!"
date: 2019-05-08 11:43:28 -0400
categories: baekjoon 2941 CroatiaNumber 크로아티아 알파벳 algorithm
---
백준에서 처음 접했던 문제는 2941번 문제인 크로아티아 알파벳 문제였다.
[baekjoon-2941]

처음에 나는 이문제를 일단 유일한 3글자인 'dz=' 이 문자열을 골라 낸 후 나머지 두글자 애들을 풀어나갈 생각이였다.

하지만, 'nijj' 라는 입력값에서 'ij'를 지운 후 'nj'도 해당이 되어서 'nj'도 결국에는 지워버리기 때문에 문제가 발생하였다.

때문에 나는 삭제하지 말고 '\*'같은 기호로 치환하자는 생각을 하였고, '\*'기호로 치환함으로써 코드가 전보다 단순해 졌으며
훨씬 쉽게 문제를 풀 수 있었다.

​```python

    def EnglishToCroatia_count(_input):
        Croatia_alpha = ['dz=', 'c=', 'c-', 'd-', 'lj', 'nj', 's=', 'z=']
    
        for num in range(0, 8):
            if _input.count(Croatia_alpha[num]) >= 1:
                _input = '*'.join(_input.split(Croatia_alpha[num])) #_input에서 카운트한 크로아티아 알파벳들을 *로 치환
        return len(_input)
    
    _input = input()
    print(EnglishToCroatia_count(_input))
​```

<순서도>
![1557326876550](https://user-images.githubusercontent.com/50315641/57384572-d4071d00-71eb-11e9-8094-cfc1d974d207.jpg)

