# Traffic Sign Classes

Mapillary detects traffic signs on images. Traffic signs are divided to 5 different categories **Regulatory** (**Prohibitory**), **Warning** (**Danger**), **Mandatory**, **Information**, **Priority** (EU only). The same traffic sign can be visually different in different countries and regions.
In some cases, the same traffic sign class can have visual variation even in the same country/region. To handle all these, the naming of traffic signs follows the convention

{**category**}--{**traffic-sign-type**}--{**country_code**}--{**variant**}.

For instance, ***warning***--***crossroads-ahead***--***ca***--***ontario*** stands for the **Ontario**-variant of **Canadian** **crossroads-ahead** sign in the **warning** category.

Country variation of traffic signs are handled by country(region)-specific detector packages.
The number of available traffic sign classes and latest detector package version for each supported country(region) are summarized in the table below (Variants of a sign in the same country are counted as one class).


| Country | Country Code | Total | Version|
-----|:------:|:------:|:------:|
Australia | au | 75 | 2_0
Brazil | br | 82 | 5_0
Canada | ca | 86 | 2_0
Europe | eu | 79 | 6_0
USA | us | 84 | 3_0

<!-- | Country (Region) | Regulatory (Prohibitory) | Warning (Danger) | Mandatory | Information | Priority | Total
-----|:------:|:------:|:------:|:------:|:------:|:------:|
Australia | 23 | 52 | 0 | 0 | - |  75
Brazil | 29 | 46 | 5 | 2 | - |  82
Canada | 34 | 51 | 1 | 0 | - |  86
Europe | 30 | 24 | 16 | 4 | 4 | 78
USA  | 28 | 55 | 1 | 0 | - | 84 | -->

The traffic sign classes in each of the detector packages are listed below in details. The naming of the package follows the convention {**trafficsign**}_{**country_code**}_{**version**}.

## trafficsign_eu_6_0

### Priority
| Nbr | Name
:-----:|:---------------:
1 | priority--give-way--de
2 | priority--give-way-to-oncoming-traffic--de
3 | priority--give-way-to-oncoming-traffic--se
4 | priority--priority-road--de
5 | priority--stop--de


### Information
| Nbr | Name
:-----:|:---------------:
1 | information--bus-stop--de
2 | information--disabled-persons--de
3 | information--parking--de
4 | information--pedestrian-crossing--de


### Regulatory
| Nbr | Name
:-----:|:---------------:
1 | prohibitory--maximum-height--de
2 | prohibitory--maximum-speed-limit-10--de
3 | prohibitory--maximum-speed-limit-100--de
4 | prohibitory--maximum-speed-limit-110--de
5 | prohibitory--maximum-speed-limit-120--de
6 | prohibitory--maximum-speed-limit-130--de
7 | prohibitory--maximum-speed-limit-20--de
8 | prohibitory--maximum-speed-limit-30--de
9 | prohibitory--maximum-speed-limit-40--de
10 | prohibitory--maximum-speed-limit-50--de
11 | prohibitory--maximum-speed-limit-60--de
12 | prohibitory--maximum-speed-limit-70--de
13 | prohibitory--maximum-speed-limit-80--de
14 | prohibitory--maximum-speed-limit-90--de
15 | prohibitory--maximum-width--de
16 | prohibitory--no-bicycles--se
17 | prohibitory--no-entry--de
18 | prohibitory--no-heavy-goods-vehicles--de
19 | prohibitory--no-left-turn--de
20 | prohibitory--no-motor-vehicles--de
21 | prohibitory--no-motorcycles--de
22 | prohibitory--no-overtaking--de
23 | prohibitory--no-overtaking--ru
24 | prohibitory--no-overtaking-by-heavy-goods-vehicles--de
25 | prohibitory--no-parking--de
26 | prohibitory--no-pedestrians--se
27 | prohibitory--no-right-turn--de
28 | prohibitory--no-stopping-or-parking--de
29 | prohibitory--no-traffic-both-ways--de
30 | prohibitory--no-u-turn--de
31 | prohibitory--no-vehicles-carrying-dangerous-goods--de


### Mandatory
| Nbr | Name
:-----:|:---------------:
1 | mandatory--bicycles-only--de
2 | mandatory--dual-path-cyclists-and-pedestrians--de
3 | mandatory--dual-path-pedestrians-and-cyclists--de
4 | mandatory--pass-on-either-side--de
5 | mandatory--pass-on-this-side-left--de
6 | mandatory--pass-on-this-side-right--de
7 | mandatory--pedestrians-only--de
8 | mandatory--pedestrians-only--gr
9 | mandatory--pedestrians-only--it
10 | mandatory--proceed-straight--de
11 | mandatory--proceed-straight-or-turn-left--de
12 | mandatory--proceed-straight-or-turn-right--de
13 | mandatory--roundabout--de
14 | mandatory--shared-path-pedestrians-and-cyclists--de
15 | mandatory--turn-left--de
16 | mandatory--turn-left-ahead--de
17 | mandatory--turn-right--de
18 | mandatory--turn-right-ahead--de
19 | mandatory--turn-right-ahead--it


### Danger
| Nbr | Name
:-----:|:---------------:
1 | danger--children--de
2 | danger--children--it
3 | danger--children--se
4 | danger--children--uk
5 | danger--crossroads-ahead--de
6 | danger--crossroads-with-priority-to-the-right--de
7 | danger--curve-left--de
8 | danger--curve-right--de
9 | danger--cyclists-crossing-ahead--de
10 | danger--cyclists-crossing-ahead--de--right
11 | danger--cyclists-crossing-ahead--fi
12 | danger--cyclists-crossing-ahead--it
13 | danger--cyclists-crossing-ahead--se
14 | danger--double-curve-first-left--de
15 | danger--double-curve-first-right--de
16 | danger--junction-with-a-side-road-perpendicular-left--de
17 | danger--junction-with-a-side-road-perpendicular-right--de
18 | danger--other-danger--de
19 | danger--pedestrian-crossing--de
20 | danger--pedestrian-crossing--es
21 | danger--pedestrian-crossing--pl
22 | danger--pedestrian-crossing--se
23 | danger--road-bump--de
24 | danger--road-narrows-ahead--de
25 | danger--road-narrows-ahead--es
26 | danger--road-narrows-ahead--it
27 | danger--road-narrows-left-ahead--de
28 | danger--road-narrows-right-ahead--de
29 | danger--roadworks-ahead--de
30 | danger--roadworks-ahead--de--v1
31 | danger--roundabout-ahead--de
32 | danger--roundabout-ahead--es
33 | danger--slippery-road-surface--de
34 | danger--traffic-signals-ahead--de
35 | danger--two-way-traffic-ahead--be
36 | danger--two-way-traffic-ahead--de
37 | danger--two-way-traffic-ahead--es
38 | danger--uneven-road-ahead--de
39 | danger--unprotected-quayside-or-riverbank--de
40 | danger--wild-animals--de




## trafficsign_ca_2_0

### Regulatory
| Nbr | Name
:-----:|:---------------:
1 | regulatory--maximum-speed-limit-10--ca
2 | regulatory--maximum-speed-limit-100--ca
3 | regulatory--maximum-speed-limit-110--ca
4 | regulatory--maximum-speed-limit-120--ca
5 | regulatory--maximum-speed-limit-15--ca
6 | regulatory--maximum-speed-limit-20--ca
7 | regulatory--maximum-speed-limit-25--ca
8 | regulatory--maximum-speed-limit-30--ca
9 | regulatory--maximum-speed-limit-35--ca
10 | regulatory--maximum-speed-limit-40--ca
11 | regulatory--maximum-speed-limit-45--ca
12 | regulatory--maximum-speed-limit-5--ca
13 | regulatory--maximum-speed-limit-50--ca
14 | regulatory--maximum-speed-limit-55--ca
15 | regulatory--maximum-speed-limit-60--ca
16 | regulatory--maximum-speed-limit-65--ca
17 | regulatory--maximum-speed-limit-70--ca
18 | regulatory--maximum-speed-limit-75--ca
19 | regulatory--maximum-speed-limit-80--ca
20 | regulatory--maximum-speed-limit-85--ca
21 | regulatory--maximum-speed-limit-90--ca
22 | regulatory--no-bicycles--ca
23 | regulatory--no-entry--ca
24 | regulatory--no-heavy-goods-vehicles--ca
25 | regulatory--no-left-turn--ca
26 | regulatory--no-motor-vehicles--ca
27 | regulatory--no-motorcycles--ca
28 | regulatory--no-overtaking--ca
29 | regulatory--no-parking--ca
30 | regulatory--no-pedestrians--ca
31 | regulatory--no-right-turn--ca
32 | regulatory--no-stopping--ca
33 | regulatory--no-u-turn--ca
34 | regulatory--stop--ca


### Warning
| Nbr | Name
:-----:|:---------------:
1 | warning--bump-in-road--ca
2 | warning--crossroads-ahead--ca
3 | warning--crossroads-ahead--ca--ontario
4 | warning--curve-left-ahead--ca
5 | warning--curve-left-ahead--ca--ontario
6 | warning--curve-right-ahead--ca
7 | warning--curve-right-ahead--ca--ontario
8 | warning--cyclists-crossing--ca
9 | warning--dip-in-road--ca
10 | warning--divided-highway-ahead--ca
11 | warning--divided-highway-ends--ca
12 | warning--domestic-animals--ca
13 | warning--double-curve-first-left-ahead--ca--ontario
14 | warning--double-curve-first-right-ahead--ca--ontario
15 | warning--double-turn-first-left-ahead--ca
16 | warning--double-turn-first-right-ahead--ca
17 | warning--emergency-vehicles--ca
18 | warning--equestrians--ca
19 | warning--falling-rocks-or-debris-right--ca
20 | warning--farm-vehicles--ca
21 | warning--hairpin-curve-right-ahead--ca
22 | warning--hairpin-curve-right-ahead--ca--ontario
23 | warning--height-restriction-ahead--ca--feet
24 | warning--height-restriction-ahead--ca--meters
25 | warning--junction-with-a-side-road-perpendicular-left-ahead--ca
26 | warning--junction-with-a-side-road-perpendicular-left-ahead--ca--ontario
27 | warning--junction-with-a-side-road-perpendicular-right-ahead--ca
28 | warning--junction-with-a-side-road-perpendicular-right-ahead--ca--ontario
29 | warning--level-railroad-crossing-with-barriers-ahead--ca
30 | warning--loose-road-surface--ca
31 | warning--narrow-bridge-ahead--ca
32 | warning--opening-or-swing-bridge--ca
33 | warning--pavement-ends--ca
34 | warning--pedestrian-crossing--ca
35 | warning--pedestrian-crossing--ca--quebec
36 | warning--playground-ahead--ca
37 | warning--road-narrows-ahead--ca
38 | warning--road-narrows-left-ahead--ca
39 | warning--road-narrows-right-ahead--ca
40 | warning--roundabout-ahead--ca
41 | warning--shared-road-motocycles-cyclists--ca
42 | warning--slippery-road-surface--ca
43 | warning--steep-hill-downwards--ca
44 | warning--steep-hill-upwards--ca
45 | warning--stop-ahead--ca
46 | warning--stop-ahead--ca--ontario
47 | warning--traffic-merges-left-ahead--ca
48 | warning--traffic-merges-left-ahead--ca--ontario
49 | warning--traffic-merges-right-ahead--ca
50 | warning--traffic-merges-right-ahead--ca--ontario
51 | warning--traffic-signals-ahead--ca
52 | warning--tunnel-ahead--ca
53 | warning--turn-left--ca
54 | warning--turn-right--ca
55 | warning--two-way-traffic-ahead--ca
56 | warning--uncontrolled-railroad-crossing-ahead--ca
57 | warning--uneven-road--ca
58 | warning--wild-animals--ca
59 | warning--winding-road-first-left-ahead--ca
60 | warning--winding-road-first-right-ahead--ca
61 | warning--workers-in-road-ahead--ca
62 | warning--yield-ahead--ca


### Mandatory
| Nbr | Name
:-----:|:---------------:
1 | mandatory--pass-on-either-side--ca




## trafficsign_au_2_0

### Regulatory
| Nbr | Name
:-----:|:---------------:
1 | prohibitory--maximum-speed-limit-10--au
2 | prohibitory--maximum-speed-limit-100--au
3 | prohibitory--maximum-speed-limit-110--au
4 | prohibitory--maximum-speed-limit-120--au
5 | prohibitory--maximum-speed-limit-130--au
6 | prohibitory--maximum-speed-limit-20--au
7 | prohibitory--maximum-speed-limit-30--au
8 | prohibitory--maximum-speed-limit-40--au
9 | prohibitory--maximum-speed-limit-50--au
10 | prohibitory--maximum-speed-limit-60--au
11 | prohibitory--maximum-speed-limit-70--au
12 | prohibitory--maximum-speed-limit-80--au
13 | prohibitory--maximum-speed-limit-90--au
14 | regulatory--no-bicycles--au
15 | regulatory--no-entry--au
16 | regulatory--no-heavy-goods-vehicles--au
17 | regulatory--no-left-turn--au
18 | regulatory--no-pedestrians--au
19 | regulatory--no-right-turn--au
20 | regulatory--no-u-turn--au
21 | regulatory--stop--au
22 | regulatory--yield--au
23 | regulatory--yield-to-oncoming-traffic--au


### Warning
| Nbr | Name
:-----:|:---------------:
1 | warning--added-lane-left--au
2 | warning--added-lane-right--au
3 | warning--bump-in-road--au
4 | warning--children--au
5 | warning--crossroads-ahead--au
6 | warning--curve-left-ahead--au
7 | warning--curve-right-ahead--au
8 | warning--cyclists-crossing--au
9 | warning--dip-in-road--au
10 | warning--divided-highway-ahead--au
11 | warning--divided-highway-ends--au
12 | warning--domestic-animals--au
13 | warning--double-curve-first-left-ahead--au
14 | warning--double-curve-first-right-ahead--au
15 | warning--double-turn-first-left-ahead--au
16 | warning--double-turn-first-right-ahead--au
17 | warning--emu-crossing--au--left
18 | warning--emu-crossing--au--right
19 | warning--equestrians--au
20 | warning--falling-rocks-or-debris-left--au
21 | warning--farm-vehicles--au
22 | warning--hairpin-curve-left-ahead--au
23 | warning--hairpin-curve-right-ahead--au
24 | warning--horizontal-alignment-left--au
25 | warning--horizontal-alignment-right--au
26 | warning--junction-with-a-side-road-perpendicular-left-ahead--au
27 | warning--junction-with-a-side-road-perpendicular-right-ahead--au
28 | warning--koala--au
29 | warning--koala-crossing--au
30 | warning--narrow-bridge-ahead--au
31 | warning--pedestrian-crossing--au
32 | warning--pedestrian-crossing--au--retired
33 | warning--pedestrians-cyclists--au
34 | warning--railway-level-crossing-with-flashing-signals-ahead--au
35 | warning--road-narrows-ahead--au
36 | warning--roundabout-ahead--au
37 | warning--slippery-motorcycles--au--victoria
38 | warning--slippery-road-surface--au
39 | warning--steep-hill-downwards--au
40 | warning--steep-hill-upwards--au
41 | warning--stop-ahead--au
42 | warning--traffic-merges-left-ahead--au
43 | warning--traffic-merges-right-ahead--au
44 | warning--traffic-signals-ahead--au
45 | warning--truck-crossing--au
46 | warning--turn-left--au
47 | warning--turn-right--au
48 | warning--two-way-traffic-ahead--au
49 | warning--uncontrolled-railroad-crossing-ahead--au
50 | warning--wild-animals--au
51 | warning--winding-road-first-left-ahead--au
52 | warning--winding-road-first-right-ahead--au
53 | warning--wombat-crossing--au
54 | warning--wombat-crossing--au--victoria
55 | warning--yield-ahead--au




## trafficsign_br_5_0

### Regulatory
| Nbr | Name
:-----:|:---------------:
1 | prohibitory--maximum-speed-limit-10--br
2 | prohibitory--maximum-speed-limit-100--br
3 | prohibitory--maximum-speed-limit-110--br
4 | prohibitory--maximum-speed-limit-120--br
5 | prohibitory--maximum-speed-limit-130--br
6 | prohibitory--maximum-speed-limit-20--br
7 | prohibitory--maximum-speed-limit-30--br
8 | prohibitory--maximum-speed-limit-40--br
9 | prohibitory--maximum-speed-limit-50--br
10 | prohibitory--maximum-speed-limit-60--br
11 | prohibitory--maximum-speed-limit-70--br
12 | prohibitory--maximum-speed-limit-80--br
13 | prohibitory--maximum-speed-limit-90--br
14 | regulatory--no-bicycles--br
15 | regulatory--no-entry--br
16 | regulatory--no-heavy-goods-vehicles--br
17 | regulatory--no-heavy-goods-vehicles--br--v1
18 | regulatory--no-left-or-u-turn--br
19 | regulatory--no-left-turn--br
20 | regulatory--no-motor-vehicles--br
21 | regulatory--no-motorcycles--br
22 | regulatory--no-overtaking--br
23 | regulatory--no-parking--br
24 | regulatory--no-parking--br--v1
25 | regulatory--no-pedestrians--br
26 | regulatory--no-right-turn--br
27 | regulatory--no-stopping--br
28 | regulatory--no-straight-through--br
29 | regulatory--no-u-turn--br
30 | regulatory--stop--br
31 | regulatory--yield--br


### Information
| Nbr | Name
:-----:|:---------------:
1 | information--parking--br
2 | information--two-way-traffic--br


### Warning
| Nbr | Name
:-----:|:---------------:
1 | warning--added-lane-right--br
2 | warning--bump-in-road--br
3 | warning--cyclists-crossing--br
4 | warning--divided-highway-ahead--br
5 | warning--domestic-animals--br
6 | warning--double-curve-first-left-ahead--br
7 | warning--double-curve-first-right-ahead--br
8 | warning--double-reverse-curve--br
9 | warning--double-turn-first-left-ahead--br
10 | warning--double-turn-first-right-ahead--br
11 | warning--falling-rocks-or-debris-right--br
12 | warning--farm-vehicles--br
13 | warning--flaggers-in-road-ahead--br
14 | warning--height-restriction-ahead--br--feet
15 | warning--horizontal-alignment-right--br
16 | warning--junction-with-a-side-road-acute-left-ahead--br
17 | warning--junction-with-a-side-road-perpendicular-left-ahead--br
18 | warning--junction-with-a-side-road-perpendicular-right-ahead--br
19 | warning--loop-pretzel--br
20 | warning--loose-road-surface--br
21 | warning--pass-left-or-right--br
22 | warning--pedestrian-crossing--br
23 | warning--playground-ahead--br
24 | warning--road-narrows-ahead--br
25 | warning--road-narrows-left-ahead--br
26 | warning--road-narrows-right-ahead--br
27 | warning--roundabout-ahead--br
28 | warning--school-zone--br
29 | warning--slippery-road-surface--br
30 | warning--stop-ahead--br
31 | warning--t-roads--br
32 | warning--traffic-merges-right-ahead--br
33 | warning--traffic-signals-ahead--br
34 | warning--triple-reverse-curve--br
35 | warning--trucks-rollover--br
36 | warning--turn-curve-left--br
37 | warning--turn-curve-right--br
38 | warning--turn-left--br
39 | warning--turn-right--br
40 | warning--two-way-traffic-ahead--br
41 | warning--uneven-road--br
42 | warning--wild-animals--br
43 | warning--winding-road-first-left-ahead--br
44 | warning--winding-road-first-right-ahead--br
45 | warning--workers-in-road-ahead--br
46 | warning--y-roads--br


### Mandatory
| Nbr | Name
:-----:|:---------------:
1 | mandatory--bicycles-only--br
2 | mandatory--keep-right--br
3 | mandatory--proceed-straight--br
4 | mandatory--transit-only--br
5 | mandatory--turn-right--br




## trafficsign_us_3_0

### Regulatory
| Nbr | Name
:-----:|:---------------:
1 | regulatory--maximum-speed-limit-10--us
2 | regulatory--maximum-speed-limit-15--us
3 | regulatory--maximum-speed-limit-20--us
4 | regulatory--maximum-speed-limit-25--us
5 | regulatory--maximum-speed-limit-30--us
6 | regulatory--maximum-speed-limit-35--us
7 | regulatory--maximum-speed-limit-40--us
8 | regulatory--maximum-speed-limit-45--us
9 | regulatory--maximum-speed-limit-50--us
10 | regulatory--maximum-speed-limit-55--us
11 | regulatory--maximum-speed-limit-60--us
12 | regulatory--maximum-speed-limit-65--us
13 | regulatory--maximum-speed-limit-70--us
14 | regulatory--maximum-speed-limit-75--us
15 | regulatory--maximum-speed-limit-80--us
16 | regulatory--maximum-speed-limit-85--us
17 | regulatory--no-bicycles--us
18 | regulatory--no-entry--us
19 | regulatory--no-heavy-goods-vehicles--us
20 | regulatory--no-left-or-u-turn--us
21 | regulatory--no-left-turn--us
22 | regulatory--no-left-turn--us--v1
23 | regulatory--no-parking--us
24 | regulatory--no-pedestrians--us
25 | regulatory--no-right-turn--us
26 | regulatory--no-right-turn--us--v1
27 | regulatory--no-straight-through--us
28 | regulatory--no-u-turn--us
29 | regulatory--no-u-turn--us--v1
30 | regulatory--stop--us
31 | regulatory--yield--us


### Warning
| Nbr | Name
:-----:|:---------------:
1 | warning--added-lane-from-entering-roadway--us
2 | warning--added-lane-right--us
3 | warning--crossroads-ahead--us
4 | warning--cyclists-crossing--us
5 | warning--divided-highway-ahead--us
6 | warning--domestic-animals--us
7 | warning--double-curve-first-left-ahead--us
8 | warning--double-curve-first-right-ahead--us
9 | warning--double-reverse-curve--us
10 | warning--double-turn-first-left-ahead--us
11 | warning--double-turn-first-right-ahead--us
12 | warning--emergency-vehicles--us
13 | warning--falling-rocks-or-debris-right--us
14 | warning--flaggers-in-road-ahead--us
15 | warning--hairpin-curve-right-ahead--us
16 | warning--height-restriction-ahead--us--feet
17 | warning--height-restriction-ahead--us--meters
18 | warning--horizontal-alignment-left--us
19 | warning--horizontal-alignment-right--us
20 | warning--junction-with-a-side-road-acute-left-ahead--us
21 | warning--junction-with-a-side-road-acute-right-ahead--us
22 | warning--junction-with-a-side-road-perpendicular-left-ahead--us
23 | warning--junction-with-a-side-road-perpendicular-right-ahead--us
24 | warning--loop-270-degree--us
25 | warning--loop-pretzel--us
26 | warning--motorcycle-crossing--us
27 | warning--narrow-bridge-ahead--us
28 | warning--offset-roads--us
29 | warning--pass-left-or-right--us
30 | warning--pedestrian-crossing--us
31 | warning--playground-ahead--us
32 | warning--road-narrows-ahead--us
33 | warning--road-narrows-left-ahead--us
34 | warning--road-narrows-right-ahead--us
35 | warning--roundabout-ahead--us
36 | warning--slippery-bicycles--us
37 | warning--slippery-road-surface--us
38 | warning--steep-hill-downwards--us
39 | warning--stop-ahead--us
40 | warning--t-roads--us
41 | warning--traffic-merges-right-ahead--us
42 | warning--traffic-signals-ahead--us
43 | warning--tram-crossing--us
44 | warning--triple-reverse-curve--us
45 | warning--trucks-rollover--us
46 | warning--turn-curve-left--us
47 | warning--turn-curve-right--us
48 | warning--turn-left--us
49 | warning--turn-right--us
50 | warning--two-way-traffic-ahead--us
51 | warning--uncontrolled-railroad-crossing-ahead--us
52 | warning--winding-road-first-left-ahead--us
53 | warning--winding-road-first-right-ahead--us
54 | warning--workers-in-road-ahead--us
55 | warning--y-roads--us
56 | warning--yield-ahead--us


### Mandatory
| Nbr | Name
:-----:|:---------------:
1 | mandatory--pass-on-either-side--us







