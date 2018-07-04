# OctoPrint-PrintTimeGenius

Provide better estimations on print time in OctoPrint.

## Setup

Install via the bundled [Plugin Manager](https://github.com/foosel/OctoPrint/wiki/Plugin:-Plugin-Manager)
or manually using this URL:

    https://github.com/eyal0/OctoPrint-PrintTimeGenius/archive/master.zip

### Install [GCodeAnalyser](https://github.com/eyal0/GCodeAnalyser) for best analysis.

Steps to run on your Raspberry Pi:
```
cd ~
sudo apt-get update
sudo apt-get -y install git wget
git clone https://github.com/eyal0/GCodeAnalyser.git
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
source .bashrc
nvm install 10.5.0
nvm use 10.5.0
cd GCodeAnalyser/js
npm install
/home/pi/.nvm/versions/node/v10.5.0/bin/node analyse.js ../samples/nonlinear.gco 
```
In about 5 seconds you should get a big json output looking something like this:
```
{"estimatedPrintTime":7100.64089243737,"progress":[[0,7100.64089243737],[0.00217832442953576,6977.040239581316],[0.007633798539501111,6916.083935589284],[0.009270992945983629,6848.9525986060835],[0.010916469954859818,6787.2125957613825],[0.017241617316160737,6722.108780872788],[0.020576745213346032,6660.071457105976],[0.025706436962493615,6600.048944570963],[0.03239601882911611,6540.009517938834],[0.03905247028616391,6479.008754427784],[0.04593255200784086,6418.164378580941],[0.05292306842810011,6357.401170324513],[0.05985008489667454,6297.077316604957],[0.06684060131693378,6237.063254893909],[0.07401333498985381,6175.4609042373595],[0.08118606866277385,6114.27774068009],[0.08835880233569388,6053.511828397467],[0.0955315360086139,5993.165105358425],[0.102803660910258,5933.1528175209],[0.11006198147457931,5871.830005279324],[0.11748871495423863,5810.802340910008],[0.12485194848221311,5750.246522175305],[0.1323697905882028,5689.8834782474205],[0.1399925456578457,5629.837099062193],[0.14789690920887344,5568.910343043778],[0.1556825554589252,5508.444320823655],[0.16346820170897697,5448.372464652279],[0.17155202164520092,5386.601520763011],[0.17973247194268438,5325.384562108757],[0.18776935713201087,5265.083427650453],[0.19583109012851838,5205.026457360744],[0.2042213663533082,5143.432889213078],[0.2124459905302246,5082.95858334563],[0.22071754945403846,5022.314781776227],[0.22940047763007138,4961.150676738992],[0.23785977554147514,4899.930103018065],[0.24654270371750803,4839.908625312799],[0.2550020016289118,4779.837532652718],[0.2638809513949283,4719.327400599373],[0.2728095967753068,4658.732844290873],[0.2817796551676537,4597.534469732084],[0.2908491047887246,4537.032483894554],[0.30002898910837783,4476.76976388845],[0.3089355475490399,4416.615604411386],[0.3182562361093856,4355.540183107876],[0.3274361204290388,4295.202797980784],[0.3367568089893845,4235.168711762859],[0.3456523239601883,4175.08981204778],[0.35506412114686436,4113.617372638646],[0.36425228806891125,4053.587771297959],[0.3736254331110835,3993.2323554614695],[0.3829875346833975,3932.018711373137],[0.39248491876147484,3870.6039746499496],[0.40202923758644965,3809.282857831721],[0.4113057522673624,3749.1882313071765],[0.42058226694827516,3689.154960329893],[0.4299940641349512,3628.1959540243124],[0.4394500352010602,3566.751395861169],[0.44881489764083876,3506.7260491640786],[0.45797545588824007,3446.6512614847675],[0.4674148617495617,3385.998619415565],[0.4769591805745365,3324.576692623637],[0.48623569525544924,3264.558328791622],[0.4955701881531177,3203.1948451181324],[0.5050068331469748,3142.4759143869674],[0.5145511519719496,3081.368604586644],[0.5238193840504687,3021.2886033610143],[0.5333526594055852,2959.9317893876596],[0.5426843914357892,2899.0279439194574],[0.5521127538272526,2838.0443903631167],[0.561546637953645,2777.2309488138308],[0.5709639568752503,2715.9423703382945],[0.580245993291092,2655.9409172236565],[0.5892326168882263,2595.741571675775],[0.5985919575930757,2534.6923133861856],[0.6078657114065239,2473.682156293903],[0.6170373131237835,2413.517055057153],[0.6262199583109013,2353.473105068292],[0.6355323642688533,2292.5717345096937],[0.6448917049737027,2231.671909397447],[0.6542510456785522,2170.5607706212004],[0.6636379950580472,2109.3650572449624],[0.6727930315705195,2049.1988208686907],[0.6821054375284714,1988.0641735177587],[0.6914813434381083,1927.5240118270558],[0.7006087712759349,1867.5202322834475],[0.7096782208970058,1806.6221305573554],[0.7190762137463591,1746.562556175747],[0.7283499675598073,1685.9525872918648],[0.7377093082646567,1625.2054404570936],[0.7470686489695062,1563.9321320887047],[0.7560525116991759,1503.0604078182905],[0.7651937438743253,1442.8265935365125],[0.7743819107963722,1381.5513792499642],[0.7835700777184191,1321.18129633027],[0.7925705056528761,1261.0847066764372],[0.8015543683825458,1200.9776718841895],[0.810684557087837,1140.0864688532201],[0.819947267431427,1079.3788843069697],[0.8292955646664182,1018.233292352028],[0.8383456882152373,958.2220672745107],[0.8476387681009373,896.9644137142031],[0.8565701743487804,836.8182250864229],[0.8656202978975994,776.4107996122266],[0.8745710302176944,716.1587087230282],[0.8835024364655375,655.5101697952659],[0.8925912121588603,594.9782931573682],[0.9015695531536009,534.9657985425138],[0.9104346985822945,474.65798836549766],[0.9193661048301376,412.886547648116],[0.9284548805234605,352.5899274536814],[0.9380185254206872,291.84624496434026],[0.9480570395218177,231.20626556532716],[0.9591087919824409,170.29814446522232],[0.9708203917670932,109.75988393745502],[0.9836308168026394,49.30783441503718],[0.9909333112463936,0],[1,0]]}
```

## Configuration

The default configuration will use 
