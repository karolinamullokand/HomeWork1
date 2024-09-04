# HomeWork1
> setwd("/Users/karolinamullokand/Desktop/ECO_B2000")
> #Directory will be same for experiment and code from lecture notes
> 
> dice.experiment <- read.csv(file.choose('dice_experiment.csv'), header = TRUE)
> 
> #Observe results from the dice experiment
> 
> 
> load("Household_Pulse_data_ph4c2.RData")
> 
> Household_Pulse_data[1:10,1:6]
   TBIRTH_YEAR    RHISPANIC RRACE     EEDUC        MS EGENID_BIRTH
1         1976 Not Hispanic Black  bach deg separated       female
2         1961 Not Hispanic White assoc deg  divorced       female
3         1988 Not Hispanic White   adv deg   married       female
4         1956 Not Hispanic White assoc deg   married         male
5         1970 Not Hispanic White  bach deg   married         male
6         1984 Not Hispanic White   adv deg   married       female
7         1968     Hispanic White some coll  divorced         male
8         1967 Not Hispanic White   adv deg   married         male
9         1972 Not Hispanic White some coll   married       female
10        1956 Not Hispanic White  bach deg   married         male
> attach(Household_Pulse_data)
The following objects are masked from Household_Pulse_data (pos = 12):

    ANXIOUS, ANYWORK, CHILDFOOD, CURFOODSUF, DOWN, EEDUC, EGENID_BIRTH, ENROLLNONE, EST_ST, EVICT, FORCLOSE,
    GENID_DESCRIBE, HADCOVIDRV, INCOME, INTEREST, KIDS_12_17Y, KIDS_5_11Y, KIDS_LT5Y, KINDWORK, LIVQTRRV, LONGCOVID,
    MHLTH_DIFFCLT, MHLTH_GET, MHLTH_NEED, MHLTH_SATISFD, MORTCUR, MS, Num_kids_homeschool, Num_kids_Priv_School,
    Num_kids_Pub_School, PRICESTRESS, PRIVHLTH, PUBHLTH, RECVDVACC, REGION, RENTCUR, RHISPANIC, RRACE, RSNNOWRKRV,
    SEXUAL_ORIENTATION, SOCIAL1, SOCIAL2, SUPPORT1, SUPPORT1EXP, SUPPORT2, SUPPORT3, SUPPORT4, SYMPTOMS, TBIRTH_YEAR,
    TENURE, TWDAYS, WORRY, WRKLOSSRV

> summary(Household_Pulse_data)
  TBIRTH_YEAR          RHISPANIC       RRACE                EEDUC               MS        EGENID_BIRTH       GENID_DESCRIBE 
 Min.   :1936   Not Hispanic:64658   White:57562   less than hs:  585   NA       :  477   male  :31510   NA         :36702  
 1st Qu.:1957   Hispanic    : 6494   Black: 6345   some hs     : 1282   married  :39339   female:39642   male       :15089  
 Median :1969                        Asian: 3379   HS diploma  :10094   widowed  : 4551                  female     :18830  
 Mean   :1970                        Other: 3866   some coll   :15415   divorced :11585                  transgender:  147  
 3rd Qu.:1983                                      assoc deg   : 7614   separated: 1300                  other      :  384  
 Max.   :2006                                      bach deg    :19137   never    :13900                                     
                                                   adv deg     :17025                                                       
      SEXUAL_ORIENTATION                      KIDS_LT5Y                         KIDS_5_11Y                        KIDS_12_17Y   
 NA            :  969    NA                        :63953   NA                       :60784   NA                        :60641  
 gay or lesbian: 2386    Yes children under 5 in HH: 7199   Yes children 5 - 11 in HH:10368   Yes children 12 - 17 in HH:10511  
 straight      :62989                                                                                                           
 bisexual      : 2756                                                                                                           
 something else: 1177                                                                                                           
 dont know     :  875                                                                                                           
                                                                                                                                
                              ENROLLNONE                     WRKLOSSRV                              ANYWORK     
 NA                                :66789   NA                    : 1558   NA                           : 1819  
 children not in any type of school: 4363   yes recent HH job loss: 6685   yes employment in last 7 days:41672  
                                            no recent HH job loss :62909   no employment in last 7 days :27661  
                                                                                                                
                                                                                                                
                                                                                                                
                                                                                                                
                KINDWORK                                              RSNNOWRKRV                                   TWDAYS     
 NA                 :30263   NA                                            :44596   NA                                : 2550  
 work for govt      : 6654   concerned about spreading                     :16005   had 1-2 telework days in past week: 6797  
 work for private co:23400   caring for elderly                            : 3830   had 3-4 telework days in past week: 4617  
 work for nonprofit : 5025   employer closed because covid                 : 2835   had 5+ telework days in past week :11121  
 self employed      : 5011   sick or disabled                              : 1022   had no telework days in past week :46067  
 work in family biz :  799   am/was sick w covid or caring for sick w covid: 1021                                             
                             (Other)                                       : 1843                                             
                                            ANXIOUS                                                  WORRY      
 NA                                             : 5480   NA                                             : 5580  
 no anxiety over past 2 wks                     :37174   no worry over past 2 wks                       :43087  
 several days anxiety over past 2 wks           :19618   several days worried over past 2 wks           :15509  
 more than half the days anxiety over past 2 wks: 4329   more than half the days worried over past 2 wks: 3386  
 nearly every day anxiety                       : 4551   nearly every day worry                         : 3590  
                                                                                                                
                                                                                                                
                                                 INTEREST                                          DOWN      
 NA                                                  : 5566   NA                                     : 5600  
 no days in past 2 wks with little interest in things:45234   no days in past 2 wks feeling depressed:44300  
 several days over past 2 wks                        :14309   several days over past 2 wks           :15438  
 more than half the days over past 2 wks             : 3240   more than half the days over past 2 wks: 2965  
 nearly every day                                    : 2803   nearly every day                       : 2849  
                                                                                                             
                                                                                                             
                                     MHLTH_NEED                                                     MHLTH_GET    
 NA                                       :51723   NA                                                    :67609  
 all children need mental health treatment: 1324   all children get the mental health treatment they need: 2743  
 some but not all children                : 2266   some but not all children                             :  347  
 no, none of the children                 :15839   no, none of the children                              :  453  
                                                                                                                 
                                                                                                                 
                                                                                                                 
                                                 MHLTH_SATISFD                                             MHLTH_DIFFCLT  
 NA                                                     :68076   NA                                               :67608  
 satisfied with all the mental health treatment they get: 2061   not difficult to get kids mental health treatment: 1244  
 some but not all                                       :  816   somewhat difficult                               : 1332  
 no, none                                               :  199   very difficult                                   :  719  
                                                                 unable to get treatment due to difficulty        :  186  
                                                                 did not try to get                               :   63  
                                                                                                                          
                                SOCIAL1               SOCIAL2     
 NA                                 : 6563   NA           : 6518  
 always get social emotional support:19032   always lonely: 2381  
 usually                            :23055   usually      : 4847  
 sometimes                          :12604   sometimes    :17999  
 rarely                             : 5844   rarely       :23362  
 never                              : 4054   never        :16045  
                                                                  
                                                         SUPPORT1                                                     SUPPORT2    
 NA                                                          : 6579   NA                                                  : 6638  
 talk on phone w family friends neighbors less than once week:11831   get together w friends or family less than once week:25546  
 1 or 2 per week                                             :18093   1 or 2 per week                                     :25665  
 3 or 4 per week                                             :14001   3 or 4 per week                                     : 8552  
 5 + per week                                                :20648   5 + per week                                        : 4751  
                                                                                                                                  
                                                                                                                                  
                                                              SUPPORT3                                         SUPPORT4    
 NA                                                               : 6703   NA                                      : 7353  
 attend church or religious ceremony never or less than 1 per year:35992   attend clubs or orgs less than once week:50214  
 1 to 3 per year                                                  : 8433   1 or 2 per week                         :10676  
 4 to 11 per year                                                 : 3948   3 or 4 per week                         : 2909  
 12+ times per year                                               :16076                                                   
                                                                                                                           
                                                                                                                           
                                                             SUPPORT1EXP                             CURFOODSUF   
 NA                                                                :11402   NA                            : 8111  
 text on phone w friends or family or neighbors less than once week: 7990   had enough food               :42018  
 1 or 2 per week                                                   :10780   had enough but not what wanted:16391  
 3 or 4 per week                                                   :40980   sometimes not enough food     : 3442  
 5 + per week                                                      :    0   often not enough food         : 1190  
                                                                                                                  
                                                                                                                  
                                               CHILDFOOD                                PRICESTRESS   
 NA                                                 :63887   NA                               :21815  
 often kids not eating enough because couldnt afford:  370   very stressed about price changes:18189  
 sometimes kids not eating enough                   : 1425   Moderate stress price changes    :13888  
 kids got enough food                               : 5470   a little stress price changes    :13278  
                                                             no stress                        : 3982  
                                                                                                      
                                                                                                      
                           TENURE                                     LIVQTRRV                RENTCUR     
 NA                           : 9149   live in detached 1 family          :41925   NA             :55782  
 housing owned free and clear :15998   NA                                 : 9749   current on rent:13906  
 housing owned with mortgage  :29700   live in bldg w 5+ apts             : 8145   behind on rent : 1464  
 housing rented               :15439   live in 1 family attached to others: 4758                          
 housing occupied without rent:  866   live in mobile home                : 2637                          
                                       live in building with 3-4 apts     : 2115                          
                                       (Other)                            : 1823                          
                MORTCUR                                             EVICT                                             FORCLOSE    
 NA                 :41545   NA                                        :69734   NA                                        :69931  
 current on mortgage:28370   very likely evicted in next 2 months      :  190   very likely forclosed in next 2 months    :   52  
 behind on mortgage : 1237   somewhat likely evicted in next 2 months  :  354   somewhat likely forclosed in next 2 months:  182  
                             not very likely evicted in next 2 months  :  394   not very likely forclosed in next 2 months:  452  
                             not at all likely evicted in next 2 months:  480   not at all forclosed in next 2 months     :  535  
                                                                                                                                  
                                                                                                                                  
               RECVDVACC                                  HADCOVIDRV                                  LONGCOVID    
 NA                 :10284   NA                                :10717   NA                                 :36298  
 yes got vaxx       :52519   yes tested + or doc told had Covid:36478   had symptoms 3mo or more Long Covid: 9685  
 no did not get vaxx: 8349   no                                :23957   no                                 :25169  
                                                                                                                   
                                                                                                                   
                                                                                                                   
                                                                                                                   
                                    SYMPTOMS                          INCOME             EST_ST                        PRIVHLTH    
 NA                                     :34850   NA                      :12256   California: 5215   has private health ins:45139  
 had no covid symptoms although tested +: 1350   HH income $100k - 149   :10444   Texas     : 3456   no private health ins :12251  
 had mild Covid symptoms                :13155   HH income $50k - 74.9   : 9461   Washington: 2892   NA                    :13762  
 had moderate Covid symptoms            :16783   HH income $75 - 99.9    : 7844   Florida   : 2613                                 
 had severe Covid symptoms              : 5014   HH income $200k +       : 7480   Michigan  : 2033                                 
                                                 HH income less than $25k: 6782   Arizona   : 2018                                 
                                                 (Other)                 :16885   (Other)   :52925                                 
                  PUBHLTH            REGION      Num_kids_Pub_School Num_kids_Priv_School Num_kids_homeschool
 has public health ins:24916   Northeast:10731   Min.   :0.0         Min.   :0.00         Min.   :0.00       
 no public health ins :30126   South    :23680   1st Qu.:1.0         1st Qu.:1.00         1st Qu.:1.00       
 NA                   :16110   Midwest  :15071   Median :2.0         Median :1.00         Median :1.00       
                               West     :21670   Mean   :1.7         Mean   :1.26         Mean   :1.22       
                                                 3rd Qu.:2.0         3rd Qu.:2.00         3rd Qu.:2.00       
                                                 Max.   :4.0         Max.   :2.00         Max.   :2.00       
                                                 NA's   :58066       NA's   :69107        NA's   :70079      

                                                 
> summary(TBIRTH_YEAR[GENID_DESCRIBE == "female"])
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   1936    1957    1970    1970    1983    2006
> 
> summary(TBIRTH_YEAR[GENID_DESCRIBE == "male"])
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   1936    1956    1969    1970    1983    2006
> 
> summary(TBIRTH_YEAR[GENID_DESCRIBE == "transgender"])
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   1936    1983    1992    1988    1998    2006
> 
> summary(TBIRTH_YEAR[GENID_DESCRIBE == "other"])
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   1936    1962    1978    1976    1990    2006
> 
> summary(TBIRTH_YEAR[GENID_DESCRIBE == "NA"])
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   1936    1956    1969    1970    1983    2006
> 
> # here i want to find average ages of men and women
> mean(TBIRTH_YEAR[GENID_DESCRIBE == "female"])
[1] 1970.346
> sd(TBIRTH_YEAR[GENID_DESCRIBE == "female"])
[1] 15.56546
> mean(TBIRTH_YEAR[GENID_DESCRIBE == "male"])
[1] 1969.691
> sd(TBIRTH_YEAR[GENID_DESCRIBE == "male"])
[1] 16.09923
> hist(TBIRTH_YEAR[(TBIRTH_YEAR < 1950)])
> hist(TBIRTH_YEAR[(TBIRTH_YEAR < 1950)])
> mean(TBIRTH_YEAR[ (GENID_DESCRIBE == "female") & (TBIRTH_YEAR > 1936) ])
[1] 1970.493
> mean(TBIRTH_YEAR[(GENID_DESCRIBE == "male") & (TBIRTH_YEAR >1942)])
[1] 1970.615
> summary(EEDUC)
less than hs      some hs   HS diploma    some coll    assoc deg     bach deg      adv deg 
         585         1282        10094        15415         7614        19137        17025 
> 
> 
> install.packages("tidyverse")
Error in install.packages : Updating loaded packages
> library(tidyverse)
> summary(EST_ST)
             Alabama               Alaska              Arizona             Arkansas           California             Colorado 
                1074                  825                 2018                  932                 5215                 1860 
         Connecticut             Delaware District of Columbia              Florida              Georgia               Hawaii 
                1237                  693                  757                 2613                 1957                  764 
               Idaho             Illinois              Indiana                 Iowa               Kansas             Kentucky 
                1099                 1625                 1387                 1204                 1166                 1107 
           Louisiana                Maine             Maryland        Massachusetts             Michigan            Minnesota 
                1021                  759                 1634                 1892                 2033                 1461 
         Mississippi             Missouri              Montana             Nebraska               Nevada        New Hampshire 
                 781                 1350                  680                  896                 1001                  981 
          New Jersey           New Mexico             New York       North Carolina         North Dakota                 Ohio 
                1287                 1340                 1381                 1410                  474                 1287 
            Oklahoma               Oregon         Pennsylvania         Rhode Island       South Carolina         South Dakota 
                1195                 1880                 1906                  691                 1170                  752 
           Tennessee                Texas                 Utah              Vermont             Virginia           Washington 
                1385                 3456                 1551                  597                 1896                 2892 
       West Virginia            Wisconsin              Wyoming 
                 599                 1436                  545 
> summary(INCOME)
                      NA HH income less than $25k  HH income $25k - $34.9k    HH income $35k - 49.9    HH income $50k - 74.9 
                   12256                     6782                     5156                     6192                     9461 
    HH income $75 - 99.9    HH income $100k - 149     HH income $150 - 199        HH income $200k + 
                    7844                    10444                     5537                     7480 
> Household_Pulse_data %>%
+   group_by(EST_ST) %>%
+   summarize(
+     avg = mean(2024 - TBIRTH_YEAR),
+     stdev = sd(2024 - TBIRTH_YEAR),
+     n_obs = n()
+   )
# A tibble: 51 × 4
   EST_ST                 avg stdev n_obs
   <fct>                <dbl> <dbl> <int>
 1 Alabama               55.1  16.1  1074
 2 Alaska                53.7  15.6   825
 3 Arizona               56.6  16.0  2018
 4 Arkansas              54.2  16.2   932
 5 California            53.9  15.8  5215
 6 Colorado              53.2  16.1  1860
 7 Connecticut           54.4  15.9  1237
 8 Delaware              57.2  15.8   693
 9 District of Columbia  45.3  14.3   757
10 Florida               57.2  16.1  2613
# ℹ 41 more rows
# ℹ Use `print(n = ...)` to see more rows
> Household_Pulse_data %>%
+   group_by(EST_ST) %>%
+   summarize(
+     age90th = quantile((2024 - TBIRTH_YEAR),probs = 0.9),
+     age10th = quantile((2024 - TBIRTH_YEAR),probs = 0.1),
+     n_obs = n()
+   ) %>%
+   arrange(desc(age90th), .by_group = TRUE)
# A tibble: 51 × 4
   EST_ST        age90th age10th n_obs
   <fct>           <dbl>   <dbl> <int>
 1 Arizona          77      34    2018
 2 Florida          77      34    2613
 3 Hawaii           77      37.3   764
 4 New Mexico       77      35    1340
 5 Delaware         76      35     693
 6 Idaho            76      34    1099
 7 Nevada           76      34    1001
 8 New Hampshire    76      35     981
 9 West Virginia    76      34     599
10 Arkansas         75.9    32     932
# ℹ 41 more rows
# ℹ Use `print(n = ...)` to see more rows
> table(EEDUC,GENID_DESCRIBE)
              GENID_DESCRIBE
EEDUC            NA male female transgender other
  less than hs  342   98    134           3     8
  some hs       713  233    319           3    14
  HS diploma   5279 1929   2818          15    53
  some coll    7877 3200   4204          41    93
  assoc deg    3987 1373   2200           8    46
  bach deg     9842 4432   4721          49    93
  adv deg      8662 3824   4434          28    77
> xtabs(~EEDUC + GENID_DESCRIBE)
              GENID_DESCRIBE
EEDUC            NA male female transgender other
  less than hs  342   98    134           3     8
  some hs       713  233    319           3    14
  HS diploma   5279 1929   2818          15    53
  some coll    7877 3200   4204          41    93
  assoc deg    3987 1373   2200           8    46
  bach deg     9842 4432   4721          49    93
  adv deg      8662 3824   4434          28    77
> prop.table(table(EEDUC,GENID_DESCRIBE))
              GENID_DESCRIBE
EEDUC                    NA         male       female  transgender        other
  less than hs 4.806611e-03 1.377333e-03 1.883292e-03 4.216326e-05 1.124353e-04
  some hs      1.002080e-02 3.274680e-03 4.483360e-03 4.216326e-05 1.967619e-04
  HS diploma   7.419328e-02 2.711097e-02 3.960535e-02 2.108163e-04 7.448842e-04
  some coll    1.107067e-01 4.497414e-02 5.908478e-02 5.762312e-04 1.307061e-03
  assoc deg    5.603497e-02 1.929672e-02 3.091972e-02 1.124353e-04 6.465033e-04
  bach deg     1.383236e-01 6.228918e-02 6.635091e-02 6.886665e-04 1.307061e-03
  adv deg      1.217394e-01 5.374410e-02 6.231729e-02 3.935237e-04 1.082190e-03
> mean(TBIRTH_YEAR[(REGION == "Northeast")])
[1] 1970.11
> 
> # alternatively
> restrict1 <- as.logical((REGION == "Northeast"))
> dat_northeast <- subset(Household_Pulse_data, restrict1)
> 
> detach()
> attach(dat_northeast)
The following objects are masked from Household_Pulse_data:

    ANXIOUS, ANYWORK, CHILDFOOD, CURFOODSUF, DOWN, EEDUC, EGENID_BIRTH, ENROLLNONE, EST_ST, EVICT, FORCLOSE,
    GENID_DESCRIBE, HADCOVIDRV, INCOME, INTEREST, KIDS_12_17Y, KIDS_5_11Y, KIDS_LT5Y, KINDWORK, LIVQTRRV, LONGCOVID,
    MHLTH_DIFFCLT, MHLTH_GET, MHLTH_NEED, MHLTH_SATISFD, MORTCUR, MS, Num_kids_homeschool, Num_kids_Priv_School,
    Num_kids_Pub_School, PRICESTRESS, PRIVHLTH, PUBHLTH, RECVDVACC, REGION, RENTCUR, RHISPANIC, RRACE, RSNNOWRKRV,
    SEXUAL_ORIENTATION, SOCIAL1, SOCIAL2, SUPPORT1, SUPPORT1EXP, SUPPORT2, SUPPORT3, SUPPORT4, SYMPTOMS, TBIRTH_YEAR,
    TENURE, TWDAYS, WORRY, WRKLOSSRV

> 
> mean(TBIRTH_YEAR)
[1] 1970.11
> detach()
>
#Interesting, why do we need sd? -> As far as I understand the most of birth years in the dataset deviate from the mean by about 15.57 years for females and 16.1 for males.
