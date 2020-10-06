
SUBMISSION QUESTION TO ANSWER
    Describe the data that you will be using to solve the problem or execute your idea. 
    So make sure that you provide adequate explanation and discussion, with examples, of the data that you will be using.

    This submission will eventually become your Data section in your final report. 
    So I recommend that you push the report (having your Data section) to your Github repository and submit a link to it.




Data Section (Data Understanding)

The data used will be a subset of the information provided in the Seattle Data-Collisions.csv that will allow for plotting of vehicle accidents and predicting accident severity. As the focus is on vehicle accidents, all incidents with a vehicle count of 0 will be removed. Also, because there is 16 years of data, any incomplete incidents (i.e. missing data) will be removed.

Plotting Accidents
    To plot the accident location, the map co-ordinates (X, Y) and the time of the incident (INCDTTM) to limit what is plotted.


Predicting Severity
    To predict accident severity and train the model. A combination of these data items will be used:
        Severity of the incident (SEVERITYCODE)
        number of vehicles involved in accident (VEHCOUNT)
        number of people involved in accident (PERSONCOUNT)
        the type of collision (COLLISIONTYPE)
        weather (WEATHER) 
        road condition (ROADCOND) 
        light condition (LIGHTCOND) 
        Date and Time (INCDTTM)

    Data Observations
        SEVERITYCODE - the dataset has 194673 incidents with 136485 as SEVERITYCODE=1 and 58188 as SEVERITYCODE=2. The other severity codes are not reflected in the dataset and may affect the model training.
        
        VEHCOUNT - there are 5085 incidents that have a value of 0 which means no vehicles were involved. Since models will focus on vehicles, these incidents will be omitted.
        
        PERSONCOUNT - there are 5536 incidents whthout a person count included. These incidents will be omitted.
        
        COLLISIONTYPE - appears to be balanced across the available options but as this is a text field, new types may affect perdictions. 
                        When combined with SEVERITYCODE tbe results make it easy to see that injuries (severitycode=2) are most common in 'Read Ended' and 'Angles' collision types.
                        SEVERITYCODE  COLLISIONTYPE    NORMALIZED
                        1             Parked Car       0.341761
                                      Angles           0.158722
                                      Rear Ended       0.146424
                                      Other            0.132640
                                      Sideswipe        0.121420
                                      Left Turn        0.062524
                                      Right Turn       0.017697
                                      Head On          0.008686
                                      Pedestrian       0.005067
                                      Cycles           0.005059
                        2             Rear Ended       0.256724
                                      Angles           0.238403
                                      Other            0.106952
                                      Pedestrian       0.103872
                                      Left Turn        0.094686
                                      Cycles           0.083014
                                      Parked Car       0.046582
                                      Sideswipe        0.043852
                                      Head On          0.015259
                                      Right Turn       0.010657
                                      
        WEATHER - the vast majority of accidents happen in clear weather with rain being a distant second.
                        Clear                       111135
                        Raining                      33145
                        Overcast                     27714
                        Unknown                      15091
                        Snowing                        907
                        Other                          832
                        Fog/Smog/Smoke                 569
                        Sleet/Hail/Freezing Rain       113
                        Blowing Sand/Dirt               56
                        Severe Crosswind                25
                        Partly Cloudy                    5
        
                         SEVERITYCODE  WEATHER                    NORMALIZED
                        1             Clear                       0.568316
                                      Raining                     0.165819
                                      Overcast                    0.143175
                                      Unknown                     0.107746
                                      Snowing                     0.005555
                                      Other                       0.005404
                                      Fog/Smog/Smoke              0.002883
                                      Sleet/Hail/Freezing Rain    0.000642
                                      Blowing Sand/Dirt           0.000309
                                      Severe Crosswind            0.000136
                                      Partly Cloudy               0.000015
                        2             Clear                       0.627627
                                      Raining                     0.195713
                                      Overcast                    0.153142
                                      Unknown                     0.014290
                                      Fog/Smog/Smoke              0.003275
                                      Snowing                     0.002995
                                      Other                       0.002031
                                      Sleet/Hail/Freezing Rain    0.000490
                                      Blowing Sand/Dirt           0.000263
                                      Severe Crosswind            0.000123
                                      Partly Cloudy               0.000053
 
        ROADCOND - the majority of accidents happen on dry roads
        
                        Dry               124510
                        Wet                47474
                        Unknown            15078
                        Ice                 1209
                        Snow/Slush          1004
                        Other                132
                        Standing Water       115
                        Sand/Mud/Dirt         75
                        Oil                   64
                                    
                        SEVERITYCODE  ROADCOND          NORMALIZED
                        1             Dry               0.637170
                                      Wet               0.239329
                                      Unknown           0.108116
                                      Ice               0.007062
                                      Snow/Slush        0.006315
                                      Other             0.000672
                                      Standing Water    0.000641
                                      Sand/Mud/Dirt     0.000392
                                      Oil               0.000302
                        2             Dry               0.701302
                                      Wet               0.275784
                                      Unknown           0.013111
                                      Ice               0.004779
                                      Snow/Slush        0.002923
                                      Other             0.000753
                                      Standing Water    0.000525
                                      Oil               0.000420
                                      Sand/Mud/Dirt     0.000403
        
        LIGHTCOND - most accidents are happening in daylight
        
                        Daylight                    116137
                        Dark - Street Lights On      48507
                        Unknown                      13473
                        Dusk                          5902
                        Dawn                          2502
                        Dark - No Street Lights       1537
                        Dark - Street Lights Off      1199
                        Other                          235
                        Dark - Unknown Lighting         11

                        SEVERITYCODE  LIGHTCOND               
                        1             Daylight                    0.586028
                                      Dark - Street Lights On     0.257030
                                      Unknown                     0.097187
                                      Dusk                        0.029893
                                      Dawn                        0.012673
                                      Dark - No Street Lights     0.009086
                                      Dark - Street Lights Off    0.006669
                                      Other                       0.001382
                                      Dark - Unknown Lighting     0.000053
                        2             Daylight                    0.675050
                                      Dark - Street Lights On     0.253512
                                      Dusk                        0.034047
                                      Dawn                        0.014431
                                      Unknown                     0.010596
                                      Dark - No Street Lights     0.005850
                                      Dark - Street Lights Off    0.005534
                                      Other                       0.000911
                                      Dark - Unknown Lighting     0.000070
        
        INCDTTM - The collision dataset ranges from 2004-01 to 2020-05 and clearly shows the accident trend throughout the day, 5pm-6pm is only second to the midnight-1am hour. 
                        Hour  Accidents
                        0     34381
                        1      3408
                        2      3606
                        3      1665
                        4      1222
                        5      1667
                        6      3199
                        7      6543
                        8      8570
                        9      8052
                        10     7465
                        11     8209
                        12    10384
                        13    10219
                        14    10615
                        15    11514
                        16    12122
                        17    12947
                        18     9743
                        19     7256
                        20     6236
                        21     5571
                        22     5468
                        23     4611