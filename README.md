# cryptanalysisSHMW
Cryptanalysis of Song et al. rank-based signature scheme (ePrint 2019/053)

## Compiling

Use `make signature` to compile the scheme executable and `make attack` to compile the attack executable. The executables are placed in the `bin/` folder.
The signature executable has to be ran first in order to generate the public key and signature files used by the attack.

## Usage

The signature executable generates and writes public key, private key and signature files in the folder `files/`. These files can then be used by the attack executable.

To change the number of keypairs and signatures generated, edit the line `#define ITERATIONS 1` in both `src/test_signature.cpp` and `attack.cpp`.

You can obtain non-verbose outputs (for both executables by setting `#define VERBOSE 1` to `0` (useful when using multiple iterations).

### Choosing the parameters set

By default the parameters are set to `RQCS-1`. Simply overwrite `parameters.h` with `parameters-RQCS-(1,2,3).h` and recompile both executables to switch parameters.

## Example verbose outputs

Examples are given for RQCS-1 :

### Signature verbose output

```
M: 89   N: 67   W: 5

Secret key :
530F8AFBC74536B9DBCFE7005507795CFF3B0FC7FB847F01C4497952F5F1AB8FE8BE2700FC944C8EB9395A1C0FB318009878405E6C584DC35997B3015507795CFF3B0FC7FB847F015A39CAABA1D7DF3291620C009E70B3F9542674BD79DC2B0038DD35DC4CC8F193E70D3F00C4497952F5F1AB8FE8BE27009E70B3F9542674BD79DC2B000F3EB3F75EECD0F56AE673016DDA4C80B3F3FE541C8940015A39CAABA1D7DF3291620C006BD2BF278B8DC72A3CC2D800093640506692E98B4AADEB00F5A20CDEDFABB397451EF3005A39CAABA1D7DF3291620C00914E000E0ACAA448133A58015507795CFF3B0FC7FB847F01CB77CAA5AB1D7B7A82585401A6AD862518EE852E9ED1140062E4FF77ED1F2EA1766F33005C31390C99A9E64CB1299401CD7F390293634204A213CC006DDA4C80B3F3FE541C894001914E000E0ACAA448133A58019E70B3F9542674BD79DC2B00A0A575822090BC50BE9A8C01CD7F390293634204A213CC005C31390C99A9E64CB1299401530F8AFBC74536B9DBCFE7005C31390C99A9E64CB129940137E3862B122421668DEB4C010F3EB3F75EECD0F56AE673019E70B3F9542674BD79DC2B000F3EB3F75EECD0F56AE67301F5A20CDEDFABB397451EF300CB77CAA5AB1D7B7A825854010608F3A7387E397E204B9801914E000E0ACAA448133A5801AF9BC6757E7C6CA5D47CFF00FC944C8EB9395A1C0FB318009E70B3F9542674BD79DC2B005C31390C99A9E64CB12994019E70B3F9542674BD79DC2B00C2418AF5CD8F92F1C8F5BF015C31390C99A9E64CB1299401C4497952F5F1AB8FE8BE27000F3EB3F75EECD0F56AE6730138DD35DC4CC8F193E70D3F005507795CFF3B0FC7FB847F01FC944C8EB9395A1C0FB31800C4497952F5F1AB8FE8BE270064EC0CD0D56117DF5624AB0138DD35DC4CC8F193E70D3F0031EB758C2A5A1818ADA0D4009878405E6C584DC35997B30131EB758C2A5A1818ADA0D400530F8AFBC74536B9DBCFE700530F8AFBC74536B9DBCFE7009878405E6C584DC35997B3019878405E6C584DC35997B30131EB758C2A5A1818ADA0D40031EB758C2A5A1818ADA0D4009746F3A932B49D363371C0005507795CFF3B0FC7FB847F01A99335D2460255DBF43767019E70B3F9542674BD79DC2B00FC944C8EB9395A1C0FB31800FC944C8EB9395A1C0FB318005507795CFF3B0FC7FB847F015A39CAABA1D7DF3291620C00AF9BC6757E7C6CA5D47CFF0031EB758C2A5A1818ADA0D4005A39CAABA1D7DF3291620C00000000000000000000000000F5A20CDEDFABB397451EF3009878405E6C584DC35997B301000000000000000000000000FA9CBF29814763622FF8800164EC0CD0D56117DF5624AB01C4497952F5F1AB8FE8BE2700093640506692E98B4AADEB00F5A20CDEDFABB397451EF300093640506692E98B4AADEB0031EB758C2A5A1818ADA0D400914E000E0ACAA448133A58010F3EB3F75EECD0F56AE6730138DD35DC4CC8F193E70D3F00A99335D2460255DBF43767019878405E6C584DC35997B301FA9CBF29814763622FF880019878405E6C584DC35997B3013ED5C67B74B6C8EDC746A70164EC0CD0D56117DF5624AB015507795CFF3B0FC7FB847F01000000000000000000000000CB77CAA5AB1D7B7A82585401000000000000000000000000AF9BC6757E7C6CA5D47CFF00CB77CAA5AB1D7B7A825854010F3EB3F75EECD0F56AE67301914E000E0ACAA448133A5801F5A20CDEDFABB397451EF300FC944C8EB9395A1C0FB3180037E3862B122421668DEB4C01FC944C8EB9395A1C0FB31800C4497952F5F1AB8FE8BE270038DD35DC4CC8F193E70D3F009746F3A932B49D363371C00062E4FF77ED1F2EA1766F330062E4FF77ED1F2EA1766F3300CB77CAA5AB1D7B7A82585401C2418AF5CD8F92F1C8F5BF016BD2BF278B8DC72A3CC2D800CB77CAA5AB1D7B7A8258540131EB758C2A5A1818ADA0D4006BD2BF278B8DC72A3CC2D800C2418AF5CD8F92F1C8F5BF01530F8AFBC74536B9DBCFE7009E70B3F9542674BD79DC2B00F5A20CDEDFABB397451EF300FC944C8EB9395A1C0FB3180038DD35DC4CC8F193E70D3F005507795CFF3B0FC7FB847F015507795CFF3B0FC7FB847F01000000000000000000000000FC944C8EB9395A1C0FB318005C31390C99A9E64CB1299401A6AD862518EE852E9ED11400C4497952F5F1AB8FE8BE27009746F3A932B49D363371C000C2418AF5CD8F92F1C8F5BF01A99335D2460255DBF43767015C31390C99A9E64CB12994010608F3A7387E397E204B98016DDA4C80B3F3FE541C894001914E000E0ACAA448133A5801

Public key :
8A50E7FB1CC3102FFCDC6201DC5BD313A4D5DA8782E21C01EA031360A29D0AB3BD973100228795377789B823CAB14301927A28386D8F87B3DB464D01CC3D99188F85CED327C4E800F4EECF948DFB703AF9F6A6013FCCC22BB450D5444FF1DB01E749D6C5636E1FDD196B0900E3916709FFE10CA2C1C96600DA821630699701FCED763D01166D360DFA369EA0A21DD001ACA5470F89947BCB9BFBEF01647EBEA7B7AA245F457200010573252B0BDFBE63AFB1A101294C78EAE7173816BA96E8016EC86093D189E13609D04D018078E5E592B704E6B1928E00E22B835D058A4D4C7C74C20109DD1CDAB14731FCDCDDCB007D8ABCAD0C4AA8CB189725010C10520B41E28497FB7D3300B310727C0125F664D9BC5200AF6A4AF0AEB7F0E124B83300048171545CD16F753293B601A8192913C1424B074A4FEC01C4A2D38C24DA00AA439541000987F78AB94485D6314A3A00D1432BE55FEC776406339B018F49614E3881A86CEA5156019F99360F0E51E702F66EE300A377E596DC3286F837854901E70B2A1BFCD290B821EAC600981F5F9FAABB90FEDF53A9002ED776B6E9070E9F1795E100AA76A96A9D48F11BC1CAF20042198097F73DC70A03BE380082795026D2D85AE8042EC900AE0AA12B1DF531645E6FAF01BEECBEE15F386C6E72061A0160847ADF0E0A3F909A990D00AC378E9B8DF8CA3F574615004EA1CBA63110E016F8646C001A7D4E9E6FC541A8781D1C0178B4F38DFDECDF02B32C0D007C9C867C849A12286EB78A018CAB83891EE86EDB34D37A008B8B02B4E5DF1B2DFDFAF6003AA7299A978750C11EA4EE0054329E77059904C0D87ECC0003F846C3412CB75D0D91A1003385332D3325B615EA647100A689D7DC8A5B784BC3C30000A71C4BB529A463AE8FB9280136A0B4C9B9EB99C709FA8700041EE73AD0A33028C3A7ED00F16E29382CDBDB30336B380158F12D8249B3641DDFF76B0077E036EE6A65C3829313130085B2140DA99990D68E7AEF017DA7B94059AF86CA7E3E0A00C58AF1F6EC229307CF9385001BAD5DA2026EEC87E340E8001DC590709BB04B4A49FB4B01C31DEBB3F7B7CA148A4D190157649D702087AFD1B3521C01D571CBEC1B7B80B316F5DB013AE801930BD397A64E990D00E77A29DCDC55D5621D84D101F185576C32EA2269A5D4160098F892201147C482A5642101D2B4605768D7350572C012009F79341BCB30CF6597BD3D014528CD4BFD78D97043BC0100024C8BC2E1D7674AC08FAF01590EB57D64D7FA1C5A086B00583C08EDF3F1B491B15D5001AC97F61161B5E7A8876D3A01E8DB2294E2AB2C248A73EF00C8B189FDCDF41521968F5F016BC41F98A7E352B8733CD8006EBF0F1C07BD238B6C867900E449DD4D870F2CD564F0C10069AFF7B85B9469108007F601DCC205585DC892DB553C9C0161B6D414150B17BD6FF74000B40CD7393E6D8B35A9F2450003C25EE21FBD1ADF079BC401D5ACCCF10B6B19F22B6D8D0082EAF28D8A3843E35B8D0D008E3CD41100CCEEA1BE5D4200D5F79B48314ADFDA82B6FA009F09DE67ECF50CA4B1B77E01450E2984D5675A40B611D5014CD13FF7EC4AC9CCF1F50A0011B840A19095BCA2690E7A008D2E9236EE72DE7793685A006AD257C722DF9DE47A765E0111B8E8AC1D40889EDA498A01B9AAB420348374D689FCD900FE57F500E9D72ECE17480900FF6AED51E9E31B030D32E100CCD5C0F0D9ACF1D85FC380017339FF4A626FE7F4E3D14F019394319481E3AEC85FDF5B010A3823E5C10F543668FF240083D0F11A02B52E9DCB017900A733CFB6FDD43A8A0E2D89006AD7C6F21FC366973BD519001087238B6309BC194A06BE0080282B5CE9BD157DA0FB920162AEF2F0C137EFBB7DA56000AD8ABE22FC4598133A3002000045D3F39E3CCB36D6AF4400358B8A73EA2096E744B98E0062A8B0A8157B8D470AB3E60050B86DA69F48BD95B660D200D966A40292B9EA49F78B63002A193ADDD5B4959439441701A345A933F114AF93C955D00147D9CE721F2926B688F00E019828D17D37DD8DAB1D8A1F00BAB744F1F30101B89854F600291E084C43C14B815A51A30082A875EC2615B7355D1D060056937A1AE52237AC0DE5900039C68E87E1BE7AE4409D1800B27CA18B6478CA84D4987F006E36DEA8CB734690BC1E5001DAB627DC27BECC891C7BA1014FFC367EE7F747763960A500178177ABB5B8D0317467260019470B4DC7F5BE734116B2004D61EC2D7F28278446312601

Message :
toto

Signature :
423BA52A6382F84EFE60A30155664F23535261B9A3A41F00E91359F310D1466CEC8985001FC7F67BF76AF0944F6474015DFC535194E808DAB104D700AB28FCD97353BE2212E92601F6D4AF88E7BBB6F8A3EDF101FB2A1C3E799C3140A4BC2400A6D64F6FED74399A15B8F300BC7516D0438327D54F2D9A00F6D4AF88E7BBB6F8A3EDF101E4EDEA458EF6C1D4EBD85001B4EF0AA284394EB65D8D52005DFC535194E808DAB104D7001FC7F67BF76AF0944F647401E1894581D76B2F0FFE294D004FC5169CFDA57FF6F9317600AB28FCD97353BE2212E926014AA1B958A438912DECC06B01123945CD694D772C4835A100B4EF0AA284394EB65D8D5200AB28FCD97353BE2212E92601475F0AEE3A1F1695EB91BE00FB2A1C3E799C3140A4BC24000564AFC4599DEEDB15F11D01EC77F637494CA8B7F9789801F6D4AF88E7BBB6F8A3EDF101AE4C531D2ACE50F907183B005898FC95CD75E601A4F5CA01B4EF0AA284394EB65D8D5200000000000000000000000000BC7516D0438327D54F2D9A00B4EF0AA284394EB65D8D5200FB2A1C3E799C3140A4BC2400E91359F310D1466CEC898500A3B2E0ABB4E9D7410049EE01A6D64F6FED74399A15B8F300175DEA0930D099F75DC4BC01089A1C72C7BA696312A0C800E4EDEA458EF6C1D4EBD85001475F0AEE3A1F1695EB91BE004FC5169CFDA57FF6F9317600089A1C72C7BA696312A0C8000564AFC4599DEEDB15F11D01FB2A1C3E799C3140A4BC2400FB2A1C3E799C3140A4BC2400A6D64F6FED74399A15B8F3001FC7F67BF76AF0944F647401FE4EB3FA2001DF9BB14D3901089A1C72C7BA696312A0C800EC77F637494CA8B7F9789801089A1C72C7BA696312A0C8005002E0E70ACF8F62B6550201475F0AEE3A1F1695EB91BE00E4EDEA458EF6C1D4EBD85001123945CD694D772C4835A1005DFC535194E808DAB104D700FE4EB3FA2001DF9BB14D390155664F23535261B9A3A41F000564AFC4599DEEDB15F11D01BC7516D0438327D54F2D9A005898FC95CD75E601A4F5CA01F6D4AF88E7BBB6F8A3EDF101E1894581D76B2F0FFE294D005898FC95CD75E601A4F5CA01EC77F637494CA8B7F97898014AA1B958A438912DECC06B01075800FCC165B51C0FAD4900E4493FD9A76C1F88D5094900C0F62D1AA48E6EE67B0CF001DD6D3D1EB53FF63E173BFB0094C64B68E64F9341A72DE801F43D7B18C88A8B793BCA9E001F4B017DE8974F48800E820143D002127B875CA7D5540401A08D1B1B1714AD65044ED200655DA472E08E867206895F01BD15C6AE3F8591BCAE640901D3889C4B36782262CBACE001953CC638D7FD7C63B1612601F99B24BC248479A012F05B0162178B9081B59F7976C6E200655BCA2109D0F51277917500E75681A4405D373F70232600A7D58960221354A51A0928018CBE6BBBC2384C047101550129C7A44A61CF056C48BFD2011449F6EEAA5D4196B789BE00BE287D57DA0F8BCB66751C00A4BB69F1C074FE3C1894AF0067856B833C7A240FFFBFED0138D38DC74C1C4EBB35256500362919D92C82625638B0E7003565E833EA7BA3B31407D001C97A3EEB8E0B9F6C40ED6500F683A29325F5A57443D50B008979C506D2E3A7EC27AA23010F70E53FD09F0C2716C81E018E834F22A0A82A1207898E00642BB7894261BB1E6F365700873AC20409A806DA3838A80001872FDA045EF528EDAB8301741FBD0A3CBFD1A9FEDC1F00073DE60F8E1F109CB0033E01C2AF03921FBCCED32C4D640155BE30F0ED80D03F3CE943013AA2AC6EA5D52E7D9B81BE00BB37DB62C4539358BBAA8900E54F59D51159D6A0A0BA2B00231DA00FDD734E58E4E01F019E71E0FE66F2C5299F086B018B42E2D72CD881FF5915E2001A9D92696544BE51F572910103ADA0429A794B3C0917E700074E254EE22B8FF2672E4E01F9506CE206B3C647762457003A0852D348EB341714AE0801B99E7FF7E4886F082857780184C0F2798F322538775DC3011D8F5E0961B7D36F7BFC090178AD1BE319360EE0BD719301063EA3CFBF13E60433DC7A0178DDE0C62FEB9FC6C5E72700C7EFFB382109ABFA5895F101CF31742C385088C4D30BC600558E8F49A6E361B7BEDC7B01DD25DB9F83D0C81244879901DF98F5053AC14D41B7FD2F01168CEB8E6C6B0C221EBC8C01E590914F01A99E95CBB91C01B26028F0968892850A6BBC01EC022FA500DEC588B2225200B770DBBB787D77DB6725040054BCE3768585E58FFEBB28017681448ECA1D423AE3B48600A1A133965ADCB129C4BB3A0099DD3687558B0F0496543C010D051E7682E45AD528DAC700E882668ED980E7F69485CD01F4BE28BDC36A87DABEF6CC00565443782F62705D06A13F007F9A0CAC4C1117D5159C1B00B9EC048C6FFCF2536A6E6B00E1C013876C532C5A3E198400564987FA88F81213CBECA600EC18119FD1AF353DD6AE80017DF1BD00BC27BED53EE28900D2777F172D265A43E74567011D86D6313E7FF9D53BA95000EC576FF851E9696CA15ECA0175E5DDD4DD26081067922F01F37A1C53FD773C9F6736B800CA59C3431731B89D3F6CFB00A89C5CD4CED11D2512392F01E88163EB7F72D2411AD37000CD676231ACB4DB14B975AC019867C409A71756FFA21ECD01EA76FA680B681B3A0B8536011A7F7C0CDCAC266C65F629012BD7470662066D445EE63800E5196E06B40CF20ECA403201A990DA2506B2154A67E28B01ABF4591466CD6CD737CBED01B4BFEB27DB4C50F0729520008C51F647725F8ACF8F21CD00BD173FFBB92FBC86B460B400736422B9C35FE127A64C3A00918EEB83D8245D20278B41007274E81C484704BF2A468F01105BAB5B189312F6D8051B011986F155A8929472AC7B7600CDF1E8507C05D6BF8B7498015BF7EA6395069B0E76587C0130E41A517F6C796AB401D701663A8370AE6B76DBD577590041A87DB080D4FAB371DECB00F8EA663CC56DC41A3298A401A183E7C45510FA8A25F69500EB04A6B01A03056A91A88901A978EBCD2D608E06889BB701D689419AD375A06EDE177600A9FF0B058AFB48491A5E3701A63C8C011EDBF6497617F100F636D2B8358EF2CC37BE350196CB15CFD1FCD916C1696901B8C00D37A0A99D2863FD7F01B93F5C3797B53203EB1814017580A90E532C5C5A944896005AC935813EAAF082FC10B201C299CF71C61206A1651AC60016F359AC003BAF409066EE01AFABA8470B8F022E4DBB2601B16381D97DE7D842296622009D70F487454CC9A54E1AC8013180F6CE77D68F1B15A1C00044484551927284E69F21CF00328C768E4BC0085F541E4D007566476BE68BEA1A0C95C600C82773EB8D27008725FAA300DF374799F0A6AE356A49D000E5470CFE2BDFC7995701E100

Signature OK
```

### Attack verbose output

```
Attack executable 
M: 89   N: 67   W: 5   
Loaded public key :
8A50E7FB1CC3102FFCDC6201DC5BD313A4D5DA8782E21C01EA031360A29D0AB3BD973100228795377789B823CAB14301927A28386D8F87B3DB464D01CC3D99188F85CED327C4E800F4EECF948DFB703AF9F6A6013FCCC22BB450D5444FF1DB01E749D6C5636E1FDD196B0900E3916709FFE10CA2C1C96600DA821630699701FCED763D01166D360DFA369EA0A21DD001ACA5470F89947BCB9BFBEF01647EBEA7B7AA245F457200010573252B0BDFBE63AFB1A101294C78EAE7173816BA96E8016EC86093D189E13609D04D018078E5E592B704E6B1928E00E22B835D058A4D4C7C74C20109DD1CDAB14731FCDCDDCB007D8ABCAD0C4AA8CB189725010C10520B41E28497FB7D3300B310727C0125F664D9BC5200AF6A4AF0AEB7F0E124B83300048171545CD16F753293B601A8192913C1424B074A4FEC01C4A2D38C24DA00AA439541000987F78AB94485D6314A3A00D1432BE55FEC776406339B018F49614E3881A86CEA5156019F99360F0E51E702F66EE300A377E596DC3286F837854901E70B2A1BFCD290B821EAC600981F5F9FAABB90FEDF53A9002ED776B6E9070E9F1795E100AA76A96A9D48F11BC1CAF20042198097F73DC70A03BE380082795026D2D85AE8042EC900AE0AA12B1DF531645E6FAF01BEECBEE15F386C6E72061A0160847ADF0E0A3F909A990D00AC378E9B8DF8CA3F574615004EA1CBA63110E016F8646C001A7D4E9E6FC541A8781D1C0178B4F38DFDECDF02B32C0D007C9C867C849A12286EB78A018CAB83891EE86EDB34D37A008B8B02B4E5DF1B2DFDFAF6003AA7299A978750C11EA4EE0054329E77059904C0D87ECC0003F846C3412CB75D0D91A1003385332D3325B615EA647100A689D7DC8A5B784BC3C30000A71C4BB529A463AE8FB9280136A0B4C9B9EB99C709FA8700041EE73AD0A33028C3A7ED00F16E29382CDBDB30336B380158F12D8249B3641DDFF76B0077E036EE6A65C3829313130085B2140DA99990D68E7AEF017DA7B94059AF86CA7E3E0A00C58AF1F6EC229307CF9385001BAD5DA2026EEC87E340E8001DC590709BB04B4A49FB4B01C31DEBB3F7B7CA148A4D190157649D702087AFD1B3521C01D571CBEC1B7B80B316F5DB013AE801930BD397A64E990D00E77A29DCDC55D5621D84D101F185576C32EA2269A5D4160098F892201147C482A5642101D2B4605768D7350572C012009F79341BCB30CF6597BD3D014528CD4BFD78D97043BC0100024C8BC2E1D7674AC08FAF01590EB57D64D7FA1C5A086B00583C08EDF3F1B491B15D5001AC97F61161B5E7A8876D3A01E8DB2294E2AB2C248A73EF00C8B189FDCDF41521968F5F016BC41F98A7E352B8733CD8006EBF0F1C07BD238B6C867900E449DD4D870F2CD564F0C10069AFF7B85B9469108007F601DCC205585DC892DB553C9C0161B6D414150B17BD6FF74000B40CD7393E6D8B35A9F2450003C25EE21FBD1ADF079BC401D5ACCCF10B6B19F22B6D8D0082EAF28D8A3843E35B8D0D008E3CD41100CCEEA1BE5D4200D5F79B48314ADFDA82B6FA009F09DE67ECF50CA4B1B77E01450E2984D5675A40B611D5014CD13FF7EC4AC9CCF1F50A0011B840A19095BCA2690E7A008D2E9236EE72DE7793685A006AD257C722DF9DE47A765E0111B8E8AC1D40889EDA498A01B9AAB420348374D689FCD900FE57F500E9D72ECE17480900FF6AED51E9E31B030D32E100CCD5C0F0D9ACF1D85FC380017339FF4A626FE7F4E3D14F019394319481E3AEC85FDF5B010A3823E5C10F543668FF240083D0F11A02B52E9DCB017900A733CFB6FDD43A8A0E2D89006AD7C6F21FC366973BD519001087238B6309BC194A06BE0080282B5CE9BD157DA0FB920162AEF2F0C137EFBB7DA56000AD8ABE22FC4598133A3002000045D3F39E3CCB36D6AF4400358B8A73EA2096E744B98E0062A8B0A8157B8D470AB3E60050B86DA69F48BD95B660D200D966A40292B9EA49F78B63002A193ADDD5B4959439441701A345A933F114AF93C955D00147D9CE721F2926B688F00E019828D17D37DD8DAB1D8A1F00BAB744F1F30101B89854F600291E084C43C14B815A51A30082A875EC2615B7355D1D060056937A1AE52237AC0DE5900039C68E87E1BE7AE4409D1800B27CA18B6478CA84D4987F006E36DEA8CB734690BC1E5001DAB627DC27BECC891C7BA1014FFC367EE7F747763960A500178177ABB5B8D0317467260019470B4DC7F5BE734116B2004D61EC2D7F28278446312601

Loaded signature :
423BA52A6382F84EFE60A30155664F23535261B9A3A41F00E91359F310D1466CEC8985001FC7F67BF76AF0944F6474015DFC535194E808DAB104D700AB28FCD97353BE2212E92601F6D4AF88E7BBB6F8A3EDF101FB2A1C3E799C3140A4BC2400A6D64F6FED74399A15B8F300BC7516D0438327D54F2D9A00F6D4AF88E7BBB6F8A3EDF101E4EDEA458EF6C1D4EBD85001B4EF0AA284394EB65D8D52005DFC535194E808DAB104D7001FC7F67BF76AF0944F647401E1894581D76B2F0FFE294D004FC5169CFDA57FF6F9317600AB28FCD97353BE2212E926014AA1B958A438912DECC06B01123945CD694D772C4835A100B4EF0AA284394EB65D8D5200AB28FCD97353BE2212E92601475F0AEE3A1F1695EB91BE00FB2A1C3E799C3140A4BC24000564AFC4599DEEDB15F11D01EC77F637494CA8B7F9789801F6D4AF88E7BBB6F8A3EDF101AE4C531D2ACE50F907183B005898FC95CD75E601A4F5CA01B4EF0AA284394EB65D8D5200000000000000000000000000BC7516D0438327D54F2D9A00B4EF0AA284394EB65D8D5200FB2A1C3E799C3140A4BC2400E91359F310D1466CEC898500A3B2E0ABB4E9D7410049EE01A6D64F6FED74399A15B8F300175DEA0930D099F75DC4BC01089A1C72C7BA696312A0C800E4EDEA458EF6C1D4EBD85001475F0AEE3A1F1695EB91BE004FC5169CFDA57FF6F9317600089A1C72C7BA696312A0C8000564AFC4599DEEDB15F11D01FB2A1C3E799C3140A4BC2400FB2A1C3E799C3140A4BC2400A6D64F6FED74399A15B8F3001FC7F67BF76AF0944F647401FE4EB3FA2001DF9BB14D3901089A1C72C7BA696312A0C800EC77F637494CA8B7F9789801089A1C72C7BA696312A0C8005002E0E70ACF8F62B6550201475F0AEE3A1F1695EB91BE00E4EDEA458EF6C1D4EBD85001123945CD694D772C4835A1005DFC535194E808DAB104D700FE4EB3FA2001DF9BB14D390155664F23535261B9A3A41F000564AFC4599DEEDB15F11D01BC7516D0438327D54F2D9A005898FC95CD75E601A4F5CA01F6D4AF88E7BBB6F8A3EDF101E1894581D76B2F0FFE294D005898FC95CD75E601A4F5CA01EC77F637494CA8B7F97898014AA1B958A438912DECC06B01075800FCC165B51C0FAD4900E4493FD9A76C1F88D5094900C0F62D1AA48E6EE67B0CF001DD6D3D1EB53FF63E173BFB0094C64B68E64F9341A72DE801F43D7B18C88A8B793BCA9E001F4B017DE8974F48800E820143D002127B875CA7D5540401A08D1B1B1714AD65044ED200655DA472E08E867206895F01BD15C6AE3F8591BCAE640901D3889C4B36782262CBACE001953CC638D7FD7C63B1612601F99B24BC248479A012F05B0162178B9081B59F7976C6E200655BCA2109D0F51277917500E75681A4405D373F70232600A7D58960221354A51A0928018CBE6BBBC2384C047101550129C7A44A61CF056C48BFD2011449F6EEAA5D4196B789BE00BE287D57DA0F8BCB66751C00A4BB69F1C074FE3C1894AF0067856B833C7A240FFFBFED0138D38DC74C1C4EBB35256500362919D92C82625638B0E7003565E833EA7BA3B31407D001C97A3EEB8E0B9F6C40ED6500F683A29325F5A57443D50B008979C506D2E3A7EC27AA23010F70E53FD09F0C2716C81E018E834F22A0A82A1207898E00642BB7894261BB1E6F365700873AC20409A806DA3838A80001872FDA045EF528EDAB8301741FBD0A3CBFD1A9FEDC1F00073DE60F8E1F109CB0033E01C2AF03921FBCCED32C4D640155BE30F0ED80D03F3CE943013AA2AC6EA5D52E7D9B81BE00BB37DB62C4539358BBAA8900E54F59D51159D6A0A0BA2B00231DA00FDD734E58E4E01F019E71E0FE66F2C5299F086B018B42E2D72CD881FF5915E2001A9D92696544BE51F572910103ADA0429A794B3C0917E700074E254EE22B8FF2672E4E01F9506CE206B3C647762457003A0852D348EB341714AE0801B99E7FF7E4886F082857780184C0F2798F322538775DC3011D8F5E0961B7D36F7BFC090178AD1BE319360EE0BD719301063EA3CFBF13E60433DC7A0178DDE0C62FEB9FC6C5E72700C7EFFB382109ABFA5895F101CF31742C385088C4D30BC600558E8F49A6E361B7BEDC7B01DD25DB9F83D0C81244879901DF98F5053AC14D41B7FD2F01168CEB8E6C6B0C221EBC8C01E590914F01A99E95CBB91C01B26028F0968892850A6BBC01EC022FA500DEC588B2225200B770DBBB787D77DB6725040054BCE3768585E58FFEBB28017681448ECA1D423AE3B48600A1A133965ADCB129C4BB3A0099DD3687558B0F0496543C010D051E7682E45AD528DAC700E882668ED980E7F69485CD01F4BE28BDC36A87DABEF6CC00565443782F62705D06A13F007F9A0CAC4C1117D5159C1B00B9EC048C6FFCF2536A6E6B00E1C013876C532C5A3E198400564987FA88F81213CBECA600EC18119FD1AF353DD6AE80017DF1BD00BC27BED53EE28900D2777F172D265A43E74567011D86D6313E7FF9D53BA95000EC576FF851E9696CA15ECA0175E5DDD4DD26081067922F01F37A1C53FD773C9F6736B800CA59C3431731B89D3F6CFB00A89C5CD4CED11D2512392F01E88163EB7F72D2411AD37000CD676231ACB4DB14B975AC019867C409A71756FFA21ECD01EA76FA680B681B3A0B8536011A7F7C0CDCAC266C65F629012BD7470662066D445EE63800E5196E06B40CF20ECA403201A990DA2506B2154A67E28B01ABF4591466CD6CD737CBED01B4BFEB27DB4C50F0729520008C51F647725F8ACF8F21CD00BD173FFBB92FBC86B460B400736422B9C35FE127A64C3A00918EEB83D8245D20278B41007274E81C484704BF2A468F01105BAB5B189312F6D8051B011986F155A8929472AC7B7600CDF1E8507C05D6BF8B7498015BF7EA6395069B0E76587C0130E41A517F6C796AB401D701663A8370AE6B76DBD577590041A87DB080D4FAB371DECB00F8EA663CC56DC41A3298A401A183E7C45510FA8A25F69500EB04A6B01A03056A91A88901A978EBCD2D608E06889BB701D689419AD375A06EDE177600A9FF0B058AFB48491A5E3701A63C8C011EDBF6497617F100F636D2B8358EF2CC37BE350196CB15CFD1FCD916C1696901B8C00D37A0A99D2863FD7F01B93F5C3797B53203EB1814017580A90E532C5C5A944896005AC935813EAAF082FC10B201C299CF71C61206A1651AC60016F359AC003BAF409066EE01AFABA8470B8F022E4DBB2601B16381D97DE7D842296622009D70F487454CC9A54E1AC8013180F6CE77D68F1B15A1C00044484551927284E69F21CF00328C768E4BC0085F541E4D007566476BE68BEA1A0C95C600C82773EB8D27008725FAA300DF374799F0A6AE356A49D000E5470CFE2BDFC7995701E100

Recovered support : 
[
[1 0 0 0 1 1 0 0 1 1 0 1 0 1 1 1 1 0 1 0 1 1 1 0 0 0 1 1 0 0 0 1 0 1 0 1 0 1 0 0 0 1 0 1 1 0 1 0 0 0 0 1 1 0 0 0 0 0 0 1 1 0 0 0 1 0 1 1 0 1 0 1 0 0 0 0 0 1 0 1 0 0 1 0 1 0 1 1]
[0 1 0 0 0 1 1 0 0 0 1 0 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 0 1 0 1 1 0 1 1 1 1 1 1 1 1 0 0 0 0 1 1 1 0 1 0 0 1 0 0 0 0 1 0 1 0 1 1 0 1 1 1 0 1 1 1 1 0 1 1 0 1 1 0 0 1 1]
[0 0 1 0 0 1 1 0 0 0 1 1 0 1 1 1 0 0 1 1 0 0 0 0 0 0 0 0 1 0 1 1 1 0 1 0 1 0 1 1 1 0 0 0 0 1 1 0 1 1 1 0 1 0 0 0 1 1 1 1 1 0 1 1 0 1 1 0 1 0 1 0 0 0 1 0 0 1 0 0 1 1 0 1 0 1 0 1 1]
[0 0 0 1 1 0 0 1 0 0 0 1 1 1 1 0 0 0 0 0 0 0 1 0 0 1 1 1 1 0 1 0 0 0 1 1 0 1 1 0 0 0 0 1 1 0 1 0 1 0 1 1 0 0 1 0 1 1 0 0 0 0 1 1 1 0 0 1 1 0 1 0 1 1 1 0 1 0 0 1 1 1 0 0 1 1 0 1 1]
[0 0 0 0 0 1 0 1 1 0 1 0 0 1 0 1 1 0 1 0 1 1 1 0 0 1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 0 1 0 0 1 0 0 1 1 1 1 0 1 0 0 0 0 1 0 1 0 0 1 1 1 1 1 0 1 0 1 0 1 1 0 0 1 0 0 1 1 0 0 0 1 1]
]
Successfully recovered x and y such that x + hy = s
1 secret keys recovered out of 1
Average recovery time : 0.054970s
```