2-2 dplyr
================

참고문헌 윤종식(2020) 위컴, 그롤문드(2019). pp.43-72 3장 데이터변형,
pp.163-184 10장 dplyr로 하는 관계형데이터

1.  dplyr 패키지

Q1. Cars93 데이터의 모델번호(Model), 종류(Type), 가격(Price) 변수들만
추출해보자.

``` r
# select를 사용하여 특정 변수만 추출
Cars93 %>% select(Model, Type, Price)
```

    ## Error in select(., Model, Type, Price): 사용되지 않은 인자 (Model, Type, Price)

``` r
# 에러 발생 이유: MASS 패키지의 select()와 dplyr 패키지의 select()가 충돌하기 때문
# 해결방법: select()가 dplyr 함수임을 명시해주기
Cars93 %>% dplyr::select(Model, Type, Price)
```

    ##             Model    Type Price
    ## 1         Integra   Small  15.9
    ## 2          Legend Midsize  33.9
    ## 3              90 Compact  29.1
    ## 4             100 Midsize  37.7
    ## 5            535i Midsize  30.0
    ## 6         Century Midsize  15.7
    ## 7         LeSabre   Large  20.8
    ## 8      Roadmaster   Large  23.7
    ## 9         Riviera Midsize  26.3
    ## 10        DeVille   Large  34.7
    ## 11        Seville Midsize  40.1
    ## 12       Cavalier Compact  13.4
    ## 13        Corsica Compact  11.4
    ## 14         Camaro  Sporty  15.1
    ## 15         Lumina Midsize  15.9
    ## 16     Lumina_APV     Van  16.3
    ## 17          Astro     Van  16.6
    ## 18        Caprice   Large  18.8
    ## 19       Corvette  Sporty  38.0
    ## 20       Concorde   Large  18.4
    ## 21        LeBaron Compact  15.8
    ## 22       Imperial   Large  29.5
    ## 23           Colt   Small   9.2
    ## 24         Shadow   Small  11.3
    ## 25         Spirit Compact  13.3
    ## 26        Caravan     Van  19.0
    ## 27        Dynasty Midsize  15.6
    ## 28        Stealth  Sporty  25.8
    ## 29         Summit   Small  12.2
    ## 30         Vision   Large  19.3
    ## 31        Festiva   Small   7.4
    ## 32         Escort   Small  10.1
    ## 33          Tempo Compact  11.3
    ## 34        Mustang  Sporty  15.9
    ## 35          Probe  Sporty  14.0
    ## 36       Aerostar     Van  19.9
    ## 37         Taurus Midsize  20.2
    ## 38 Crown_Victoria   Large  20.9
    ## 39          Metro   Small   8.4
    ## 40          Storm  Sporty  12.5
    ## 41        Prelude  Sporty  19.8
    ## 42          Civic   Small  12.1
    ## 43         Accord Compact  17.5
    ## 44          Excel   Small   8.0
    ## 45        Elantra   Small  10.0
    ## 46         Scoupe  Sporty  10.0
    ## 47         Sonata Midsize  13.9
    ## 48            Q45 Midsize  47.9
    ## 49          ES300 Midsize  28.0
    ## 50          SC300 Midsize  35.2
    ## 51    Continental Midsize  34.3
    ## 52       Town_Car   Large  36.1
    ## 53            323   Small   8.3
    ## 54        Protege   Small  11.6
    ## 55            626 Compact  16.5
    ## 56            MPV     Van  19.1
    ## 57           RX-7  Sporty  32.5
    ## 58           190E Compact  31.9
    ## 59           300E Midsize  61.9
    ## 60          Capri  Sporty  14.1
    ## 61         Cougar Midsize  14.9
    ## 62         Mirage   Small  10.3
    ## 63       Diamante Midsize  26.1
    ## 64         Sentra   Small  11.8
    ## 65         Altima Compact  15.7
    ## 66          Quest     Van  19.1
    ## 67         Maxima Midsize  21.5
    ## 68        Achieva Compact  13.5
    ## 69  Cutlass_Ciera Midsize  16.3
    ## 70     Silhouette     Van  19.5
    ## 71   Eighty-Eight   Large  20.7
    ## 72          Laser  Sporty  14.4
    ## 73         LeMans   Small   9.0
    ## 74        Sunbird Compact  11.1
    ## 75       Firebird  Sporty  17.7
    ## 76     Grand_Prix Midsize  18.5
    ## 77     Bonneville   Large  24.4
    ## 78            900 Compact  28.7
    ## 79             SL   Small  11.1
    ## 80          Justy   Small   8.4
    ## 81         Loyale   Small  10.9
    ## 82         Legacy Compact  19.5
    ## 83          Swift   Small   8.6
    ## 84         Tercel   Small   9.8
    ## 85         Celica  Sporty  18.4
    ## 86          Camry Midsize  18.2
    ## 87         Previa     Van  22.7
    ## 88            Fox   Small   9.1
    ## 89        Eurovan     Van  19.7
    ## 90         Passat Compact  20.0
    ## 91        Corrado  Sporty  23.3
    ## 92            240 Compact  22.7
    ## 93            850 Midsize  26.7
