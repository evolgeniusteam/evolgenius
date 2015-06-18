# 系统设置 #

把evolview从一台电脑转移到另一台时，需要更改配置文件：
> war/WEB-INF/confs/sys.conf

# 如何测试EvolView #

每个新版本发布之后，需要进行以下测试，以

  1. 测试老的bug是否会重新出现
  1. 测试所有功能是否运行顺利
  1. 及时发现新的bug

# Details #

  1. 系统测试
    * 新建一个用户
    * 登陆
    * 登出
    * click "Forgot your password"，重置密码
    * 检查email，用得到的新密码登陆
    * click 右上角的"Account settings"，把密码更为原来的
    * 其它
  1. 测试 tree
    * 可能的问题：输入下面的tree时，leaf node 'b'的label可能会消失；另外，系统可能误认为此tree含有bootstrap信息
    * ((a:1,b):3,(c:1,(d:1,e:3):1):2);
    * 如果一切没有问题，删除此tree
  1. 测试 tree与dataset
    * 可能的问题：输入下面的tree与dataset，然后导出为非svg格式，如pdf / png 等，会出现文字溢出现象，如下图所示：![https://lh4.googleusercontent.com/-D-rlUbKUMZM/UWQPTXUys8I/AAAAAAAAAQI/Rzasjkb4ljQ/w312-h428-p-o/5K0_%255BR5DV%2540Y%256029S70%255BRF0%257BD.jpg](https://lh4.googleusercontent.com/-D-rlUbKUMZM/UWQPTXUys8I/AAAAAAAAAQI/Rzasjkb4ljQ/w312-h428-p-o/5K0_%255BR5DV%2540Y%256029S70%255BRF0%257BD.jpg)
    * 这个问题是由后台负责将svg转换为其它格式的library 引起的。在Mac上测试时，并没有此问题出现，因此可能与特写的平台有关。
    * 解决方案：导出svg格式；或者更新后台的library。
    * tree:
```
(Ostreococcus tauri:2.329830596545600e-01,Micromonas:1.402869611346490e-01,(((((((((((((Fucus vesiculosus:1.129135509065288e-01,Desmarestia viridis:6.651077842601015e-02)0.862:2.492019215950645e-02,((((((Saccharina longipedalis:1.968956159271516e-03,(Saccharina diabolica:2.417654596255546e-04,Saccharina ochotensis:6.383859045359108e-04)0.197:3.640229157391900e-04)0.158:4.191501237244531e-04,Saccharina religiosa:2.446101803407194e-04)0.289:4.824315266913515e-04,Saccharina japonica:5.713098900545059e-04)1.000:1.101089825919027e-02,Saccharina coriacea:5.028690312294724e-03)1.000:1.871392097891347e-03,Saccharina angustata:2.775148691123087e-03)1.000:1.751306435639599e-02,Laminaria digitata:2.103641365585508e-02)1.000:4.031082832063766e-02)0.862:3.625205590549387e-02,Pylaiella littoralis:7.712588865202352e-02)1.000:1.428339420771389e-01,Dictyota dichotoma:1.924387635554760e-01)1.000:2.201715311652546e-01,(Chattonella marina:1.090234836535004e-01,Heterosigma akashiwo:8.059211080434317e-02)1.000:1.786743258702910e-01)1.000:6.207462375090114e-02,(Ochromonas danica:4.144847415133856e-01,((Synedra acus:3.357686500804963e-01,Phaeodactylum tricornutum:2.842095511223842e-01)1.000:6.639993812793736e-02,Thalassiosira pseudonana:2.011373030696694e-01)1.000:1.199058138851505e-01)0.875:5.417514767443494e-02)0.993:1.157846524868795e-01,(((Rhodomonas salina:2.807451920656215e-01,Hemiselmis andersenii:2.427610101608995e-01)1.000:1.125520149303331e-01,((((Porphyra umbilicalis:4.542086830158999e-02,Porphyra purpurea:6.244327636114112e-02)1.000:4.136646450846784e-02,(Pyropia yezoensis:5.790293838230302e-02,Pyropia haitanensis:7.529582217435524e-02)1.000:3.581042364735887e-02)1.000:1.844365832018763e-01,((((Gracilariophila oryzoides:4.346693784849582e-02,Gracilariopsis andersonii:2.690905653682255e-02)1.000:2.309125342780853e-02,Gracilariopsis lemaneiformis:3.466669404598162e-02)1.000:1.327330466320034e-01,Chondrus crispus:1.562729045399354e-01)0.592:3.976493667814861e-02,Plocamiocolax pulvinata:2.491281837578249e-01)1.000:7.912741578385257e-02)1.000:8.793897701920246e-02,Cyanidioschyzon merolae:3.845955503307672e-01)1.000:9.793408748347872e-02)0.651:3.903607360007784e-02,(Glaucocystis nostochinearum:1.987507960606057e-01,Cyanophora paradoxa:2.759162278206744e-01)1.000:1.450025136210064e-01)0.822:5.155067932463448e-02)0.829:5.162723043634034e-02,Emiliania huxleyi:4.622388660252577e-01)0.717:7.986664377222655e-02,(((((((Chlamydomonas moewusii:2.240725941063483e-01,Dunaliella salina:2.769450901256776e-01)1.000:9.656934685620826e-02,Chlamydomonas reinhardtii:1.908965603795848e-01)1.000:1.701680334633268e-01,Polytomella capuana:5.071569773109753e-01)0.908:1.988915802070240e-01,Acutodesmus obliquus:4.354845773597565e-01)0.796:1.553635839042141e-01,Pedinomonas minor:7.458308642516888e-01)0.928:1.551279506762699e-01,Pycnococcus provasolii:3.592732960129574e-01)0.842:9.497479841304879e-02,Pseudendoclonium akinetum:4.137853488175750e-01)0.586:6.729266202117729e-02)0.658:6.879653113295311e-02,Oltmannsiellopsis viridis:2.901510255031181e-01)0.901:5.838185269504416e-02,((Coccomyxa:6.879178648426970e-02,Trebouxiophyceae:8.259589402825604e-02)1.000:1.672853059721672e-01,(Helicosporidium Simulium:1.579630807867813e-01,Prototheca wickerhamii:1.335392426583669e-01)1.000:1.009513988196631e-01)1.000:5.206475329353972e-02)0.882:5.157820690603761e-02,((Chlorokybus atmophyticus:1.512626759835014e-01,Mesostigma viride:2.998717134442788e-01)1.000:4.206051224397947e-02,((Chara vulgaris:5.531076738796480e-03,Nitella hyalina:1.740398882474715e-03)1.000:9.415557955080321e-02,Chaetosphaeridium globosum:1.315448245532939e-01)1.000:8.385449381720875e-02)1.000:3.979352898842201e-02)0.882:3.662521706545938e-02,Nephroselmis olivacea:1.941520695899159e-01)1.000:1.038310931605587e-01);
```
    * dataset (leaf background color):
<pre>
## leaf background color<br>
!LegendText	green algae,brown algae,Raphidophyceae,Bacillariophyta,Cryptophyta,red algae,grey algae,Charophyceae,Chrysophyceae,Haptophyceae<br>
!LegendColors	green,brown,purple,blue,orange,red,grey,pink,yellow,black<br>
!showlegends	1<br>
<br>
Ostreococcus tauri	green	ad<br>
Micromonas	green	ad<br>
Fucus vesiculosus	brown	ad<br>
Desmarestia viridis	brown	ad<br>
Saccharina longipedalis	brown	ad<br>
Saccharina diabolica	brown	ad<br>
Saccharina ochotensis	brown	ad<br>
Saccharina religiosa	brown	ad<br>
Saccharina japonica	brown	ad<br>
Saccharina coriacea	brown	ad<br>
Saccharina angustata	brown	ad<br>
Laminaria digitata	brown	ad<br>
Pylaiella littoralis	brown	ad<br>
Dictyota dichotoma	brown	ad<br>
Chattonella marina	purple	ad<br>
Heterosigma akashiwo	purple	ad<br>
Synedra acus	blue	ad<br>
Phaeodactylum tricornutum	blue	ad<br>
Thalassiosira pseudonana	blue	ad<br>
Rhodomonas salina	orange	ad<br>
Hemiselmis andersenii	orange	ad<br>
Porphyra umbilicalis	red	ad<br>
Porphyra purpurea	red	ad<br>
Pyropia yezoensis	red	ad<br>
Pyropia haitanensis	red	ad<br>
Gracilariophila oryzoides	red	ad<br>
Gracilariopsis andersonii	red	ad<br>
Gracilariopsis lemaneiformis	red	ad<br>
Chondrus crispus	red	ad<br>
Plocamiocolax pulvinata	red	ad<br>
Cyanidioschyzon merolae	red	ad<br>
Glaucocystis nostochinearum	grey	ad<br>
Cyanophora paradoxa	grey	ad<br>
Chlamydomonas moewusii	green	ad<br>
Dunaliella salina	green	ad<br>
Chlamydomonas reinhardtii	green	ad<br>
Polytomella capuana	green	ad<br>
Acutodesmus obliquus	green	ad<br>
Pedinomonas minor	green	ad<br>
Pycnococcus provasolii	green	ad<br>
Pseudendoclonium akinetum	green	ad<br>
Oltmannsiellopsis viridis	green	ad<br>
Coccomyxa	green	ad<br>
Trebouxiophyceae	green	ad<br>
Helicosporidium Simulium	green	ad<br>
Prototheca wickerhamii	green	ad<br>
Chlorokybus atmophyticus	pink	ad<br>
Mesostigma viride	pink	ad<br>
Chara vulgaris	pink	ad<br>
Nitella hyalina	pink	ad<br>
Chaetosphaeridium globosum	pink	ad<br>
Nephroselmis olivacea	green	ad<br>
Ochromonas danica	yellow	ad<br>
Emiliania huxleyi	black	ad<br>
</pre>