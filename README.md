[Instruction video](https://www.youtube.com/watch?v=83tnWs_YBRQ&t=973s)
Dataset
--
- [link](https://huggingface.co/datasets/back2classroom/sidewalks)
1. Stream the dataset from HuggingFace
- Train
```
from datasets import load_dataset
dataset = load_dataset("back2classroom/sidewalks", split='test', streaming=True)    ## train? maybe
print(next(iter(dataset)))
```
- Val
```
from datasets import load_dataset
dataset = load_dataset("back2classroom/sidewalks", split='val', streaming=True)
print(next(iter(dataset)))
```

2. (optinal) Save the dataset to loacal
```
for record in dataset: 
	## image
	image_bytes = record['image']
	image = Image.open(io.BytesIO(image_bytes)) 
	image.show()
```



```
{'filename': '1001_10_1', 'tfw': b'1.0000000000\r\n0.0000000000\r\n0.0000000000\r\n1.0000000000\r\n0.0000000000\r\n2304.0000000000\r\n', 'tif': b'\xff\xd8\xff\xe0\x00\x10JFIF\x00\x01\x01\x00\x00\x01\x00\x01\x00\x00\xff\xdb\x00C\x00\x08\x06\x06\x07\x06\x05\x08\x07\x07\x07\t\t\x08\n\x0c\x14\r\x0c\x0b\x0b\x0c\x19\x12\x13\x0f\x14\x1d\x1a\x1f\x1e\x1d\x1a\x1c\x1c $.\' ",#\x1c\x1c(7),01444\x1f\'9=82<.342\xff\xdb\x00C\x01\t\t\t\x0c\x0b\x0c\x18\r\r\x182!\x1c!22222222222222222222222222222222222222222222222222\xff\xc0\x00\x11\x08\x01\x00\x01\x00\x03\x01"\x00\x02\x11\x01\x03\x11\x01\xff\xc4\x00\x1f\x00\x00\x01\x05\x01\x01\x01\x01\x01\x01\x00\x00\x00\x00\x00\x00\x00\x00\x01\x02\x03\x04\x05\x06\x07\x08\t\n\x0b\xff\xc4\x00\xb5\x10\x00\x02\x01\x03\x03\x02\x04\x03\x05\x05\x04\x04\x00\x00\x01}\x01\x02\x03\x00\x04\x11\x05\x12!1A\x06\x13Qa\x07"q\x142\x81\x91\xa1\x08#B\xb1\xc1\x15R\xd1\xf0$3br\x82\t\n\x16\x17\x18\x19\x1a%&\'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz\x83\x84\x85\x86\x87\x88\x89\x8a\x92\x93\x94\x95\x96\x97\x98\x99\x9a\xa2\xa3\xa4\xa5\xa6\xa7\xa8\xa9\xaa\xb2\xb3\xb4\xb5\xb6\xb7\xb8\xb9\xba\xc2\xc3\xc4\xc5\xc6\xc7\xc8\xc9\xca\xd2\xd3\xd4\xd5\xd6\xd7\xd8\xd9\xda\xe1\xe2\xe3\xe4\xe5\xe6\xe7\xe8\xe9\xea\xf1\xf2\xf3\xf4\xf5\xf6\xf7\xf8\xf9\xfa\xff\xc4\x00\x1f\x01\x00\x03\x01\x01\x01\x01\x01\x01\x01\x01\x01\x00\x00\x00\x00\x00\x00\x01\x02\x03\x04\x05\x06\x07\x08\t\n\x0b\xff\xc4\x00\xb5\x11\x00\x02\x01\x02\x04\x04\x03\x04\x07\x05\x04\x04\x00\x01\x02w\x00\x01\x02\x03\x11\x04\x05!1\x06\x12AQ\x07aq\x13"2\x81\x08\x14B\x91\xa1\xb1\xc1\t#3R\xf0\x15br\xd1\n\x16$4\xe1%\xf1\x17\x18\x19\x1a&\'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz\x82\x83\x84\x85\x86\x87\x88\x89\x8a\x92\x93\x94\x95\x96\x97\x98\x99\x9a\xa2\xa3\xa4\xa5\xa6\xa7\xa8\xa9\xaa\xb2\xb3\xb4\xb5\xb6\xb7\xb8\xb9\xba\xc2\xc3\xc4\xc5\xc6\xc7\xc8\xc9\xca\xd2\xd3\xd4\xd5\xd6\xd7\xd8\xd9\xda\xe2\xe3\xe4\xe5\xe6\xe7\xe8\xe9\xea\xf2\xf3\xf4\xf5\xf6\xf7\xf8\xf9\xfa\xff\xda\x00\x0c\x03\x01\x00\x02\x11\x03\x11\x00?\x00\xe1&\x8a\xd8F\xf3\x14W8\xe3\xd6\x96=\xcd\x12\xb4K\x80\x0eq\xd2\xa8F\x92D\xb1\x86f`\xe7\x18#\xda\xb4\xf6\xc9\x10\x009\x03\x19\x00\x1a\x9b\xb5\xb1\xd8\xf4K[\x95\xaeD\xafq\xe6y@\x8c\x01\x8c\x9e\xd4\xb6\xc5\xdeM\xa4\x98\xc7\xa8\x1c~\xb5m]Z<\xb3\x10rFGZ\x99\x92? 1\x01\xc1\xech!\xc9\xa5f\xbc\x85\xb4*\x83d\xac[\x92rh\x95\xd1\x8b\x84\x19\xc0\xce\x07ZsB\xa0\x02\x08@\xa07\'\x19\xcdP\x9a\xedD\x8e-T\x89\x88\x038\xc0\xfc\xe8M\xa4d\x92\x93mo\xf8\x11\x89\x928\xc8\x11\xe5\xd8\x90\x01\x04b\x98"x33\x1c\xe7\x9c\x03\x9a\xb1\xf6f\xb9\x84\r\xf8\x97\xbe\x08\xa6Y)\xe5\'$\xe0\x91\x92*\x1b\xbe\xa3\x9c\x93M\xaf\x9a,\xc7\xe6\\\xc0@\x00.9\x03\xbdV\xb7a\x05\xc3\xae\xdeq\xe9V-\x19\xe1\xb9 ;l\'\xa1\xa8b,\xda\x8c\xa5\x94\x11\x81\x8f\xce\x9fr#h\xddt\xdc\xa9%\x89\x96\xf09<1\xc7=\xaa\x9d\xdd\xcb$\xa6\xdd\x9b \xf02x\x15\xad;\xf9E\x99\xb0\x068\xc1\xe4V%\xe4K1,\xb9,}F)\xa7\xae\xa6\xd0\x93\x93W\xd8"\x92R\x00\x87p`x$`~u%\xda\xaa[\x92\xed\x99\x00\xc9\x19\xcd6I$\x8e!\xb0\x95\xc0\x03\x02\xa1\xb0\xb7\x92\xf6\xf8$\xc5\x8a\xb1\x00\x92(\xebr\x95\xde\xbb%\xf7\x9bZU\xa4o`\xb2\x90\xb9$\xf2M@ex.\xc8\x03\n:\x10j\xfd\xbc+k\x1bA\x9c\x8e\xc3\xd2\xa8\xdea\xa4%W\x18\x00p)\xdd\x12\x9arw\xd53^\xca\xfd\'\x9c,\xaa\x19@\x1c\x1a\x8a\xe2(\x8c\xacV$\x04\x9e\x08<\xd65\xbd\xd8\xb6g\'\xa9\x18\x1e\xd5<Z\xa4m&\x19C\x0fz\x1e\xd6\x13\x8bM\xb5\xb1\xa35\xa4\x11D\xb3`1\x07\x91\x8aH-$\xdc\x1b\x01A\xe4\x10y\xa8c\x98\xcf(\x08p\x01\xe8+D\x13\x18\x05\x8e}\x8d\thCN\xdd\xd9O\xcaW\x90\xb1\xe4\x83\x8c\x9e\xb5c;-\xf6\xa3\x05l\x93\x90y\xa8\x01\xda\xe4\x93\x80Ny\xac\xe9\xe7vbA \x03\x8c\xf6\xa6\x9d\x95\x90\xf9n\xed\xd0\xban\xd7v\xd7 \xb0\xeaMVb\x12\x19g\x04\x80\x01\xc0\x03=\xe9\x89\xa7\xbc\xea\x18\xbf\x07\xb9"\x9b(\x9a\x051\x0c\x95\xef\x9e\x94\xbaY\n\xcbd\xf5\x0b"\xd3L\x0e>\\\xf1\x9e\xb5\xa1r\xf1\x98\xbc\xb6 \xe3\xd3\x9a\xa9\th\x948PO\xa0\xa6F\x8egi\x19\x89$|\xa9\xdb4\x9e\xd7)\xdeN\xefK\x16"Di\xc3D0\xaa\x01 w5b\xea\xd3\xed\xa5Af\x8c\x0e\xb8\x1f\xe3N\xb2\xb6\x10\x1f9\x98\x06\'\x91O\x95\xe4w8bG\xa0\xa4\xf4\xd4\x96\xed-\x1e\xddJ\xae\xcb\n\x8e\xac\x07\x19#\xd2\x9c\xd6\xe2P\x19F\x0fP}*W\x83.\xaaGNN}\xe9\xd2N\x91\'\x00\x1czQn\xa2\xda\xdc\xbb\x99\xd7\xeb*[\xf2s\x8e\xe0\xf3\\\xf4\x01\xa6\xba \x92\x06pI\xed]K\xa3K\x03aCn\xce\x01\xac\xa5\xd3\x19\xe4\x90\x86*\x00\xc9\x1d\x8f5I\xa4\x9fsX\xc9$\xd3\xd0\xd5 \x0b\xb2\xccO\x96\xa0`\x01\xc6i\xc6\xea)YJ\xa66\xb1\xc9#\x19\xab_d_!\x18\xb1 \xa8\xcf\x1c\xf4\xaa\xd7\x10\xc4\x91d\x8c\x8f\xa74Y\\\xb8\xb8\xb6\xbe\xe2\xc3@\xa6\xd7r\xa8\x04\x92r*\x08\\\xa3\x1d\xfb\x8a\x81\x9cb\xad[8x\x15\x03q\xd8\x1a\x8aBC\x95\'#\xd2\x93v\xd8\xceRvh\x84\\.\xa1(\x0c3\x188*x\xce*\xa6\xa3/\xd9\xd4\x08\x06\xd2\t?-C\xe6\xb4s\xe5F\x14\x9cqWa\x81n\t,r@\xce\x08\xa1o`IGW\xb7b\x85\x95\xe4\xd6\xd3\x12\xf9r@<\xfb\xd6\xbb\xcf\x11!\x88\n\x08\x19\xc74\x92\xd9)!\x82\x81\xc0\x15Fx\x99" \xb8\'\'\xbd\x17\xbe\xe4\xb5\x194\xd6\x8d\x97\xed\xe5I\xe7\xd8\x84\x03\xebP\xdeJ\xf6Re\x00,N94\x96\x93\xc0\xa0\xc7\x15\xba\xf9\xe4\x0f\x9c\x03\x9a\x87U\xbaQ\xf30!\x80\x03\x18\xe34\x92\xd4\xcdE\xf3Z\xday\x8c\x9a\xe1$Ui\x95A\xcf95\x96\xf3<\xf39\\,`p\x01\xa7G\x9b\xf6Db\xc13\x8cb\xac\xfd\x95!-\x08PA\x1dqM$\xb77QPV\xeb\xdb\xb1\x14D<\x80\x11\x91\x801]-\x9cp\xc1\x18b\x8a\x18\x81\x83\xe9Xp\xda\x98\x18LT\xec\x1c\xf285\xab\x0c\xcbq\x85\x00\x1faC\xb5\xf4&vz-\x863)v\x90\x12q\xdb\x15B{\x92\x8aUP31 g\x8a\xb6\xe0\x99LJ\xa0\x1f~*\x19\xa0\xdc\xdd\x00 v\xa5d\xb7)Y=L9\x8b\xc8\xc4\x11\x83\xedO\x82\xcaE`\xe5\x8e\x0f\xa9\xabk\x06r\xe4w#\xf2\xa9\xed\xc0\xb9R\x8c\xa0\x01\xe9\xd6\xa9\xbb"\xe5&\x93\xb6\xddIl t1N\x1f\x00\xb1\x18\xcf\xa5mL\xe8\xcb\xb8\x00N1\x9a\xcc\x8a\x19\x05\xb8D\x00\x00I\x04\x9cS\xa1IQ\xfel\x91\xec2(V\xeeb\xd2n\xf7\xd8\x9aT\x0f\x8c\x8c\x00s\xcdQ\xb8\x88:\x14\x18\x02\xae\xdd\xde\xae\xd0\x822\xa4\xf1\x9c\x1a\xa8\x914\xb6\xcc\xeeH\x00\x9e@\xc9\xa4(\xb6\xac\xde\x82\xc2\xed\x10\x16\xc7$\x01\x9c\xf6\xe6\xa6\xb9G\x9f \xbb\x04*\x00\x03\xa52EV\xb7\x01\x1f\x0e8\xdcN\rE\x1d\xd9X\x99\x1d\xf7\x1e\x9c\x9a/\xd8Z\xb7t\xb5\xfe\xb5\'\x80F\x14\xc7\x1e\x0b\xe3\x19<P\xb1n\xb9\xf2\xb2\x15\xf0\x0esP\xda\xa8K\xac\x17$\x90\x0f\xb75i\xd1\x1a}\xea\x01l\x01\xc7&\x8bk\xb8J\xc9\xb4\x9e\xfdAm\xe6\x92p\x8c\xe4 9$s\x9a\x9c\x81\x07\n\x01a\xdc\xf1J\xb3\xecB\xa4\xe0\x91\x80\t\xaa\xd7\xb3\x97\x89\x82\x01\xb8\x8c\n\x04\x9b\x93I\xad\t.\xaf\x14lE\x1b\xa4c\x8fa\xc5G\r\xa0E\xf3f;\xb2I\xdazT\x16V\xe62\xb2J\xc5\x98\x9e\x87\xb5Zy\x0c\x8cQA\x00zP\xfc\xca\xdbD\xfed\xfedh\x83\x08\x00\xec+>\xec\x13\x1b\x98\xc67\x0c\x13\xe8)\xe4\xb4L\x19\xdc\x95\x07$R\xc9:J\x00Q\xc0<\xd2]\xc4\xa2\xafu\xa9j\x0b\x8d\xe0\x128\xce\x004N\x81\x81b\x06\x0fj\x88\x8d\x91\xae;\x1c\x9asI\xba"@\'\x038\xa7{\xeeh\xec\x9d\xd0\x88\xe8\x19\x02\xa8\x04\x1c\x92*;\xb6!e\x94\x1e\x8a8\xaa\xf1\xc94\x93\x15E\n}I\xc5[\x01\x1c\x14}\xbb\x8fS\x9e\xb4?2e\xa6\xac\xcd\xf2\x97p\'vH\x07\x00z\xd5\xeb;\x947K\x18R\x01\xc0\xc9\x18\xab\x01\xe3f\xf9@\x18\x18\xcf\xd2\xb3\xae\x1dE\xd1ew\x04\x01\xc1\x18\x1f\x9d%\xbd\x89\xbf6\x8f\xb1u\xaf\x14\x87@\xe5\x8a\x93\xc0\xfa\xd6R\xc1<\xecI$)\'\x19\xa2\xd6H\xe2w"%g\xc9$\x9c\xf3\xcd=\xef.%\x9c*\xa7\x96\x87\x03 \x9f\xebT\xaf\xb24\x8aqo\x95|\xd9~\x1bAg\x19\x9by.F\x00\xac\xeb\xb2u\x17\x10\x81\xb5\x81\xe5\x88\xc7\xf3\xab\x93\x17*\x8cdb\x07\\s\x9e*T\xb7V#(I \x1c\x91I\x19\xa7g\xcc\xf73\xb0\xb6\x8cc\xda\t\x00`\x8fZ\xb4\xc1\x16\xcaI]C\x12\xbcTW\x11\x86\x94F\x06\t8\xcdNJy+\x06rI\xc1\xf4\xa5m\x87-lT{\xcb\xab\xab8\xedDl\x91\xab\x12[\x04\x02\x0f\xd6\xa7\xd2\xe7X.v\x90\x01\x18\xe6\xb6/\xf5{c\xa5\x8b\x05\xb4\x89\\\xae\x04\x88Il\xe0\x7f\x85r\xeb\x0b\xc5)frG\xa1\xe2\xa9i\xa8\xa9\xb7(\xb4\xe3d\xef\xf3\xf36\xf5!\xd6e<\x91\xda\xabG:4`d\x96\xef\xc58^\xdb$\x0ee\xcb\x00\xbd1\x9a\xce\xb7s-\xc1\n\xb8Rr*S\xd3T\\"\xda\xb3[\x1a\xb3A\xb6\xddX\x05\x01\x89\xef\xcdP\x88\x98\xa6;N>\x95<\xd3\x89\n\xa0f\x1b{c\x8a\xabpY\x1bv\x08\x18\xc7JkR\x92\xb2\xb3\xeahO> $\x1eH\xc5\x11j!a\x00\x9e}k\x18\xcf.yf+\xe9R[:\xbc\xd8pq\xe9\x8a-\xd0\x97\x05k=M)\xdd\xe7\x1eqc\xb7\xa6\x0fN)\xa6y\xa2\x8b\x8c\x94\xf4\x06\xa7m\xbfe(\x06P\x8e\x01\x1d)mU\x0ccr\x8cg\x184\'~\x84\xa6\x94om\x0cI\xe6i\t\xc6T\xfa\xf4\xa2%VR\x08\x04\x81\x92}j{\xf4V\xb8(\xb8^3\x90j4\x88\xa2\xe0d\xfa\x91N\xe6\xb7\xbcU\xb4\x1c\x1c\xb1\xd8\xb9\x0cx\x04v\xad\xed>\xd9QVB\xe7z\xf2s\xde\xb1\xda$\x81C\x96\xc9\xc6qZ\xb0\xc8\xb2\xc4\x08#\x04`\x8aW\xea\x8cj6\xe3e\xb1\x15\xd3\xc1=\xd0U\xc6\xe0rx\xebM}\xa83\x80G\xa0\xa8-\xa1\x0f|X\x0c\x0c\xe3\xf5\xab\x8fh\xca\xe5\x8bdzS\xbd\xf4\x1bJ6W\xd2\xc3\x19\x82\x00zq\x91G\x9d\xb0\xe5F\x0e9=\xf1\xedUf\x9d%eNA\x04\x801\xc1\xa7\x05(\xbbe!\x9c\x1c\x83\x9c\x90;Rkd.]\x15\xc5\x94\x19I\xf9\x8f>\xb5,6\x0c\xe0a\xb1U\xe4r\xb2\xa2s\x968\xadpDQ"dd\xf7\xcf\xb55\xb1M\xb8\xc5X\xcb\x92\xf5\x15J\x1c\x96\xc9<\x8atWaFA\xeb\xda\xb3oKy\x84*\xf3\xeazR\xc4\xe1c\x19P[\xbe)5tS\x82q^f\x8c\xae\x10\xef\x03$\x8c\xf1D\x16\xfb\xa4\xf3er\x10\xf6\xc6i\x96\xac\x18\x00\xe39=\xea\xf3\x98c\x88\x12\xe4{\nK\xb1\x9b|\xbe\xea\xdc\xa55\xd2\xc93D\x91\xaa*\x81\xf3\x83\xc9\xa4\x8cI9(\xc0\x14\x039\'\x93U\xbeK\xab\xa3\x1a\x96P\x7f\x88\n\xd2h\x05\xacAC\x168\xce{\x9am\x03J6Kr\x81\x80Z\xb7\x9c@\xdaN0}\xaa\x19\xe5\x90\xc3\x90\xe7\x19$\x00zU\xa9\xa0y\xe2;\xe5;\x07!\x7f\xfa\xd5\x1b\xc0\x82"\x8a\xbc\xa8\xceqE\xf5\xb1\xa2i\xb4\xde\xe4\xb6\xeb!\x8a3\x90Nz\x13\x8c\xd5\xc5\xbe"<1$\x83\x8cc\x8a\xa9bE\xee\xa1\n\xe5\xa3H\xc8\xce\x07^1\xde\xac4\x01\x03rH\xdcpH\xc6y\xa4\xfb39\xa4\xdd\xa5\xb9\x14\xb2\xefM\xea\x8395VY\n&v)v\xe0\x10rE>{\x8f\xde\x84\x88\x10O\x1d8\xa9\xec W9\x94a\xf2y\x03&\x85\xdc\xa4\xb9U\xda!\x89C\xe1\xb6\x10\xfe\xb8\xe6\xa6\x9e\x05\x95\xc1~\x06\x00\xc6*\xd4\xb14l\x190\x009\xcfsPJK\x90{\x83\xcd7\xa6\xa4]\xb7tPK\x06{\x80\x00\x0c\x99\xe8x\x06\xa7\x93dw\x9b\x95U@P0:dT\xace@\\\x90\x14\x0c\xf5\xac\x86\xb9-rrN=i;\xb4V\xb2wodh-\xcc;\xd8\xb2\x02\x00\xa9\xae\xe5\xb7\xb9\x9a\x00\tE\x04d\x01\xc7J\xa3a\x08\x96b\x1c\x82\t\xeej\xd3\xc4\x86\xe1U\x14\x02\x0fQMo`\xb2R\xbaoAd\xb0\x0b!*\tL\x03\x92*\x99>U\xd1e@\xc0\x01\xc5k\xac\x8e\xc5\x90\xb9 \xa8\x00g\xa5A\r\xb6\xcb\x93\x92\x0e\xee\x05\tu\x087\xaf6\xba\x16#Q,\x01\x8e\x01=\xb3U\xee%\x11\xa1U8#\xd2\xa5\xb9"5!z\x8fJ\xcbwf,Nx\x19\xe6\x95\xb5\xb8\xa1\x1b\xbb\xf4+\xca0\x0b9\x0cI=MiY\x85\xf2\x18\x95\x07\x8e\x05P\xfb\x134\x88\xccw+\x1cc\xd2\xaeE*\xc0v( \x8e\xd8\xa6\xd6\x9a\x1bMs+"\t\xa2y\xdc\x84,O\xa1\x18\x02\xb4,m%\x82\x02]\xf9=\xb3\xd2\xa6\xb7\xdb\x11\xcb\xa8%\xfa\x13\xdb\xbdL\xd1o\x1fx\x81\xedE\x95\x88\x93\xba\xe5\xe8C\x01X\x8e\t\x00\x93\x9c\x93Oy\x9aS\xb0\x01\x8fPj&\xb5\x12(f9\x00\x9c\x03\xdf\xebMIS\x7f\x94\x85\x95\xc7|`~t4\xecC\x8a\xd5\xad_\xe4Av\xa9\x12\xa6\xd3\x96$\xfe\x158T\x00M\xb7#\x00\x1c\x8c\x1c\x8a\xac\xe6!;/2\x1crH\xe9\xf4\xabeK\x80\xd9$\x00\x05-\x01\xbd\x93 p\xb8\x17,H\ns\x81\xd6\xab\xb5\xf3\x1d\xa4\xe7\x00\x93\x9e\xf5u\xa0\x12\xca\x00$\x01\xd4c\x8a\x81\xac\xe1\xf3\x082\x90}0)\xa9t4R\x8d\xb5\x19\xe6Bc\xdb)\xc9$\xf1\x8c\xd5Hy\xbb#h\x11\xf1\x8c\xf1E\xc4/\x10\x12*n \xf3\x9a`g\xbd\xb9U\x03h\x00\x02\x07J\x17q\xa4\xac\xdaz?\xc0\xd1\x94\xefu\xdb\xb5@\xee\rT>t\x97\x0e[&5\x00\xf3\xd0\xd6\x9d\xb5\x9a\x10\x15\xd4\x1f\xadI<\nI\x89AUQ\x92@\xeb\x9a\x16\x8fC(\xb4\x9e\x83l`F\x00\x80\x01=\xea\xcc\x88R\xeb{r\x98\x03\x07\xda\xa0\x86\x06\x88\x87V$/8\xf5\xa9\xef\xa6\x08\x91J\x14\x90N\x08\x03=\xa9\xb7\xd5\x93&\xf9\xb4\xea@\xc1\x10\x19\xf0\x02\x92F3\xe9YbYg\xf3\x08b\xa8\xc3h \xfa\x1a\xba\xb1<\x91\x02\xea\xa6=\xc4\xe0\x9ey\xf6\xa4\x82 \x01&4X\xf2@\x19\xe7\xf2\xa9\xbbE&\xa2\x9b\xdd\x8f\xb7\x91m\xa3*\xa0\x17#\xef\x1a\x86ig\xbd+\t\x1b\x14\x1c\x96\x07\xaei\xfeR<\x84\x03\x9fj\x95I\n\xca\x01\x01FzS[i\xb8\xd5\xaft\xae\xc8\x84\x0b\x0b"\x91\xb8\x93\x8c\x91W\xa2\x88 \x04\x0c\xfb\n\x89\\1PG$\xf0Oj\x99\x9c\xc4\xbb\x81\xfc\xa8A&\xf4Ops\x90s\xc0\xf7\xaaj7\xdc2\x03\xc0\x00\xe7\xb5I\xa8\xdfF\x96\x80*fG\xc8\xc8\xea*\xbce"\x8d\x90\xbb\x19\x19A\xc8\x19#<\xd0\xef\xb9);_\xbf\xf5p\xba \xc4\xc8\xa4\x12\x07@rMa\xbcN\xc0\xa0R\x1b$\xe7\x15\xbf\x1cP\x82\xac\xa0\x87\xcf$\x8c\x13K*\xa8\xcb\x05\x00\xfa\xd0\x9fb\xa3%\x1d\x121\xa1G]\xa8\x18\x82N3ZV\xaec\x8c\xa1\x01\x9f\xb15Jw\xc3\x12\x06H\xf4\xad\x1b(\x08\x8c\xc8\xc7%\x861M\xeb\xb8N\xca7d\x10$\x82rY\x8f\'\xa5X\x12\xbf\x9c\xa0\xa8\x01NsNU\xf2\x89f\xf5\xefR)_/\xe6 \x82I\xe4\xd2oRg=ok\x90\xc7,\x02\xe8o\x90\xb1\'\x18\xc53P\x8e(\xf2\xc1\x80\x04v\xaa\xb2\xdb\x08g7\x00\x8cv\x00\xd3\xc5\xbbN\xca\xee\xd9\\\xf4&\x8b&\xefr\xa3\x15u+\xe8O\x04\x07\xe59$pFjI\xa1\xdb:\xba\xa8;\xb00{U\xb2\xf0\xc7\x1a\x05<\x9e1\x8e:To*\x05%\xb3\xc8\xe3\x038\xa5k\x0b\x9d\xb7qJ\x97`x\x18\x00`\x1a\x97%\x17$dU{d\xde\x18\x968\x1c\xf4\xe6\xac\xdcL \xb7\x0c\xcb\x95\xec{\xd5-\x85}l\xb5+\xcaK\xc5&\xdc\xae\x07\x15\x99yp\xd2\xaa\xa23F\xcb\xd5\x80\xe6\xb5P\xee\x05\xa5b\xaa\xc3\x809\x18\xaa7\x01\x12\'\x18\xdc\xcd\x90\t\x1c\xd2\xbaz\xb3H\xb4\x9d\xadr(J" \xb3\x93\x82\xc4rj\xfa8X\xc9#\xa8\xc0\xac\xb4\x95\x94\xa8\x08\xd9\x07<\x03S\xbc\xd3\x18\x94$D\xb0$\x9d\xc0\x8a-t9A\xb3F&V\x94\xa6\xe0\x08\x00\xf2qPId\xa1\x8c\xdb\xf2\xd9\xe0q\xc1\xa7.\x9c\xd2\x91v\xd9B\xa0\x12\xbd\x8e*G\xd8\x15v\xa8\xe0\xe4\xe2\x9aVFQvj\xcf\xd4\xaf4\xd1E\x1b4\xc7\xe4\\\xf09\xaa\xda:\xa4\xf2\x99\x14\x10\xa5\x8e\t\x18\xefT\x8b\x9dBC\n\x86 \xf7"\xb6#1i\xf6%\x0cC8<\xe2\x85\xd7CE\x0bE\xae\xac\xb3q(\xb6S/P\x9c\x9cw\xa6\xbd\xeeB\xb1\x04\x86\x1d1U`\x13^\xdb\x97%V2H\xc6}=\xaaI1\x12\xc6\xa4g\x07\xaf\xe1E\xec\x89QI\xd9\xea\xd1|l\x11+\xe7\xbf \xd5InV6!\xf2Cp\xa0\x0c\xe0\xd5\x19\xaf\x99\xe7\nAT\x18\xe4w\xaa\xd7w\x12\xcbq\x19\x88\x00\x14\xe4\x92q\x9e);\xe8J\xa7v\x93\xea_\xb8\x94E\x18\x08Ibs\x91\xd6\xa83\xccg\x198S\xc7Z\x96 \xc6@\xecF~\xb5q,|\xf7Vl\x10\x0ey4\x97b\xe2\x94w"\x85d\x8aB#P]\xc0\x00\x93\x8c~4\xd6\xb8\xb9\xb7!nS(I\x04\xa1$\xd6\xac\xd0\xc2\xb6\xa5\x83`\xc63\xc7z\x85#c\x00f%\x86I\x19\xa7~\xe3\x8c\xd3\xd5\xaf\xf3+\xb5\xccf4+\xc6N\x06x5$2\xa3\xcc"\x91\x88\x18\x07#\x9a\xafz\x91(F\x01Cg\xafz\x8a2\x0ef\x0b\x82\x063\x8fJ.\r&\xaeZ\xbb\x96\xd9%\xca\xc0\x8c\x00\xe0\x9c\x83M\x08\x8d \x90\r\x84\x81\xc8\xe6\xa2\x8a\x15\xb9fRI$c\x06\xaf\x88\x15#\x08N1\xdcRl\xcaV\x8a\xb2n\xe50\xf23\x90\x00#=I\xc14\xc7\x99\x8c\x89\x18PK\x1cu\xe9RI(w+\x10\x00\x8e9\xe2\x98\x91\x91 -\x8c\x8am+\xd8\xa4\xba\xb4@\xd63\x02\x08 \x92O\x19\xabP\x17\xb7M\xf2\x1c\x80q\x8a\xb3\x03\x81 \xdc\x01\x03\xd6\xab\\\xe5\xbc\xc2\x85N\xd1\x9c\x13\x8a\x1b\xb899>V\x8a\xba\x85\xdb4D\xa98\xf4\x15\x15\xbb<\x90\x12X\x8c\x0c\xd3\xc5\xa3\xed2\xb9\x04\x11\xf7A\xce)\xf1DI\xd8\x01\x03\xe9E\xd3Z\x16\xac\x95\x97A\xc8\x04\x96\xe5\x9c\xe4\x0c\xf0j\x17w\x0b\x85b\x17\xb0\x15\x1c\xec\xd6\xe0\xc5\x9c\xf7\xe3\xde\x9b\x1b\xe2E\x07\x9c\xd1gk\xb1\xa4\xd6\xbb\x8f\x13\xb1 \x12r*\xc5\xbc\xaf(\x0c\xc0mC\x93\xcfZ\xaa\xc5|\xd3\x9c\x81\xec+F\xd6\x10T`\xe0\x1f^3H$\xd2Z\xa2\xe6V\xda\xdf\xcd<\x89\x06\x00\x1d\xbb\xd3.\x0c\xb2\xc3\x136<\xb5$\x90O^*\x19\xa6\x11\x80\xac\xaa@\xe9\xcdA%\xcb\xdd\xc6c\x8aB\xa1984\xda\xd2\xc6J.\xf7_x\\\x1b\x89T\x84\xc9Q\xe9\xce)\xf6\xeaD{%R\xc5y\x04\x8e\x84\xd6\x96\x9a\xc9me(p\x1aG\\\x06\xee\x0ei\x81\xe20\x90\xc7\xe7\x04\x92Oq\xe9J\xca\xd6\x05;]%\xa2bG"D\x03\x08\x81>\xf4\xa2\xe8;\x10\xc0c\xb0\xa8m\xe6Y\xdaE\x0b\xd0q\xc7\xbdJ\xf6\xca\x14>\x06G#\xd4\x1aiYX|\xaa\xee\xebQ\xedv\xceYd\xca\xc2\x00\xc8\x02\xabM2\xc7\x06\xd8\xd0\r\xc4\x80\xd8\xe6\x92\xe7z\xc0Ab\xcax+\xea)m\xa3y\xf5\x1bDp<\x95`J\x93\xc7JV\xb2\x13\\\xaa\xfd\x17\xe9\xfa\x92\xd9\xd8-\x9d\xba\x9f,\x16\x1e\xb4\xd9@\x9d\x8a8\x18\xf4\xedW.u(\xa4m\xaa\xa0`b\xaa,\xf1H\t\xdb\xb4\xe7\x19\x02\xa9\xb6\x86\x9b\xb5\xda\xd4\x95\xec\xd5-PE\x85\xc1$\x80k/Q\xbbX\xbc\xb4 e\x0eI\xf5\xe2\xad4\xcf+\x9d\x8c\xca\xa3\x8e\x98\xac\xfb\xdbPa,\xe03\x12y4\xaf\xdcpJ\xeb\x99\xff\x00L\xa5=\xc1|*\xe7\x83\x92G\xbd69^i\xb7\x06!@\x03\x1fJ\x9d\xa0\x10[\x17RK0\xc0\x00t\xab\x11\xd8\x84\xb5\np\x1c\xf3\x92y\xe6\x84\xcd=\xd4\xad\xfdy\x84Q0\x9dT\x80\xc0\xe3\xafJ\xd8\x03e\xb9\xc1\n@\xcf\x06\xab\xc3\x07\xee\xc0?xw\xa9]\x07\x01\xc9\xda\x0f>\xf4\xd6\xd7dJI\xd9>\x85X\xa2\x96U*\xf2a\x01$\x9c\x8eA\xab\xb2J\xc6\xdc\x08\xb0\xc0q\x82p+*{\x90w$h\xc1A\xc6pj\xec/\xbe,\x00@\x03=)IYj9\xa6\xdam\x10\xcble\x91^P6\x8e\xab\x9e*\xd0H\xc4\x1bQ@\x1e\xd5\'\x92\x1e\xdc1 \xf2F)\x92\x03\x1a\xa8P98\xc14\xaddC\x95\xd5\xaee\xc5p-\xa7\x04\xf4,Eiy\x86T\x0e\x01\x00\xd5F\xb1\x8b\xcd\x0f3d\x13\xd3\xa8\x15,O\xe6\x8f*6`\x80\xe0\x0c`SoK\x8e\\\xad\xa6\xbel_!Co\x00\x02{\xd3\xa3\x88<\x9fx\xe7\xdcqR\x03\xb0m#$RfBxP\x07\xa8<\xd2\xbd\x9d\xc16\xd9\x14\xfb\xd2a\x12\x0c\x93\xde\xaa\xa6\x9f;\xceKJ@=FEiA\x13!\xdcI-\x9e\rB\xfb\xd2grI\x00g\x14\xd6\x9a\x8d6\x9d\x90\x89\x1a\xa1\xd8\xd8\xc8\xeei\xfe|@\xee\n8\xe3\xf2\xa8\xd5Zf\xc9P\x07\xaejU\x82 0\xc81\xeahKR$\x95\xf51\xaf\x8e\xc1\xb8\xa9 \x93\xce*\xed\xad\x88k5\xba!H\xc9\x03\x9ex\xa9\xaf\xe3\x0fo\xb5U\x18\x0c\xe01\xc0\xa4\xb0o\xdc\x08\n\xa89\'\x83\x91\xcd\x1d\n\xbb\xe5\xba\xd3\xfc\x8a\xd1\xd8<\xf2\xb9$*\x81\x9eH\x19\xabp\xb8r\x06\x19Dg\x92\x07^\xd5b+CrNHDC\x93\x83\xc9\x15#*\xa9h\xd0\x12\x08\xc7\x03\xbd\x17\x14\xa6\x9b\xb3{~\x06f\xa5l\xe5\xcb#p@\xeaqL\x82\xda;h\x18\x02\xcd4\x83\x03\x03 w\xea*\xc5\xcc\x17W\x00\x97\x18\x88p0y\xe3\xda\x99y-\xd6\x99\x14L\x91\xa1V8\r\xbb\x91\xc5\x0fr\x93|\xaa)\xab\xf6\xbfo1 \x8a\xea#\xb5\xd8\x95\xeb\x8a\x9b` o\x19\x00\x92A\xee)\x96Z\x8bo&\xe5X\x8c\x03\x9c\x12*c{\x1c\xb2\x90\xaaq\xdb\x83E\x98{\xcd\xdd\xaf\xb8\xb1n\x8b\x17\xcc\x88\x00=\xaaY\x94\xed\xdc\xceP\x1fNi\xf10\n\t\x15\x05\xdc\x91\x86,\xecB\xe3\x18\x03&\xab}\xc9M\xb7a\x90\x95i0\x02\xb9\xff\x00h\xe2\xac\xa5\xcd\xa5\x8d\xe0y\xa2\xf3X\x00B`\x91\x9f\xa8\xaa0\xc6d\x18\x82,\xe4\xf2\xe4\x10@\xab\x91\xd8\xca\x14\x16r\xcf\x9e\x84\x8cT\xad\xc2QM\xea\xfe]Jok\x98\x04\xaeB\x93\xdf<\xd1\x12\x0f,\x80\t\x03\x9c\xe3\xadGx\xc6(\xd2)\x0f\x99\x9e\x0f~\xde\xd5\xa4\x8e\x9f\xd9\xc8\xc0\x05\x00\x9c\x8a\x1a\xb2\x1c\xdb\xb2o[\xb2\x96\t\x1bA\xfc*\xbd\xe6\xe3\x10E\\\x92qL\x9a\xe5\xad\xaf\x81\x008\x188\xedV\x16\xe9]2\x17\x0eI8#\x02\x8f0Qj\xd2\xb5\xd1V\xc9\x06\x0bLF\x17\xb153\xdb\xbd\xfb\xb0F\x08\x8a3\x95 \x9a\x856J\x8e\xae\xaa\x19\x89\x1c\x9fz\xb5\xa6Y=\xb2\xb1/\x90\xdd\x00>\xf4\xef\xa9\xabi&\xfa\x93\xe7f\x14\x03\xc0\x03$u\xa9\xa4\x8b\xcf\x85Ux$\xe3#\xb5Eyy\x1a.\x02r\x063\x83I\xa6\xce\xcf\x14\x84!bG\x00\x83\xc74#\x17\tY4\x86\xde\x08V\xd3\xc8M\xab1\xc8\xdcx\xfdjh\xed\x9cD\xa0\xed<\x0c\x90sI{g\x03\xc6\x0c\xe8\x01\xc6I\xc5JP[i\x80D\xf9\xc9 \x11\xd4S\x92\xba\t$\xa2\xac\xf5o\xfa\xd4\xa1"K\xbc\xaa9\x18\xf44\xaf\x0c\x928>k\x1c\x001N\xb5$Y\xf9\xcc\xdb\x8b\xb9Q\x9e\xa3\x14[;=\xd1P\xc4\x1e*5\xb0;\xa6\xfc\x81\xed\xb3\x118\xc1Q\x9c\xd5[fho\xcc$\x92\x18\x0cz\x0c\xd6\xa5\xd6b\x88\xe4\xe4\xb7\x15V\xde \x92\x19\xd8d\x80)\xa48;\xa7}\x89dM\xa4\xb1\x14\x02\xab8F8\x04\x03\x91\xefV&+,\x00\xae\x01=\xab6\xe1\x8a\x14byS\xcd\x1dlJW6\x04J\xd1\x8d\xa4\x1a\xab:*H\x10\x00\xccz\xe7\xa5R\x87Px\xa1\xdf\xb4\xb7\'\x83\x9a|S\x99\xc9\x99\xc6\xdcv<S^a\x188\xb6\xde\xc5\xd5\xb6#+\x80\t\x03\x04T\r\x16\xe61\x96\'\x1d\x88\xe2\x9bo\xa9\xb3LU\xc7\xc8\x07QR4\xf1\xcb \x10\x9d\xceN)\xa7\xa0ZQve\x03\x14W3<\x06W\xe0g\x04qS%\xaa\xc7$`\x12\xa1NI\xc7Z\x16!\x1c\xc4\x92w\x93\xcf\x15,\x97p\xca\xca\x81NG\\\x8a\x13\xd4\xd1\xc9\xde\xcbb\xd0\x9a\x1c\xedT\x1d0N:\xd2\r\xe03\xc4\xaaJ\x8c\xe0\x9c\n\x8aE\x11\xc6\xae\x00\xc18\xc0\xa8\x16\xef%\xd0\x1c\x121I\xf62QmhL\xd7sI\x17\x92\x13\x0f\x92x\xce9\xa6\\Bot\xe3m*\xaa\xc8\xa4\x9d\xe0\xf3\xcdZ\x9a\xe1\x10\xa1\n\x14\x802G$\xf1T\x12u}h\xc0N\xe5\x91T\x0c\xf6=hK\xa8\xd4l\xae\x95\xad\xa9c\xecM\x14\n\x8d\xb5\x90\x01\xcey<T\x1fgT`\xc0\x00\x01\xa9\xd2|\xb9V\x0c\x14\x121\x8fJ\xb0\xf6\xeb$Y\xdeH=\x88\xa1$\xb6*\t\xc7FD\xb7i$\x8a\xaa\xa0\x01\x8c\xe2\x9f\x1aC#\x96\x965e\xce0EU\x82\xd9\x93$\x02\x06Oj\xba\xa9\x81\x8cU$h\xe0\x96\x89\x96 \x9a$}\x8a\x81W\xb0\x03\x8as\xba\x92z\x81\xedU\xca\x107\x0e\r\x00\x10rN}\xa9\xda\xc0\xa9\xab\xdc\xc2I\x03\xc6\x11\x87\xef\x87R\x06\x7fZ\x96Ws\x12\xc4\t\x195Z\xd5^)\xdd\x9c\x92\x14\x02G\xe3V\x16\xfe9\xee\x82\x04\x03\x80\x07\x15\x9b\xd3S9]=5H\xac\x91<\xa5\x98\x1c\xb0\xe3\x93\x8a\x96\x18\xe4\x9dA\xc0\x18b\t\x06\xa3gdl\xaa\xf4bH=\xea\x08\xde\xea\x08\xdd\xd5\xc8\xc1\'\x00\xf1\xd6\x9aN\xe5\xfb\xcd6\xad\xe4X\xbf@d\x86(\x86\x1d\x9b\x04\x8e\xbd+B9\x8d\xb1X\x98\x82\xc4\x01\xc9\xe9Xq\xea2Kx\x9bWl\xb9\x18c\xc74\x8c\x97W\x17\xec\xed#\x12\x00\xa6\x95\xadr\x94]\x94e\xb2GC\xe4\xb5\xdd\xd0\x84\xaa\x80\x00$\x83\xd75yP[\t\x1a\xddB\xba($\xf4\x07\xf1\xac\xc8nU%PX\x06\xda\x019\xab\x93^,\x96\xee\xa82\xc0rG9\xa6\x9a2\x92m%m\x08&\xb8{\xbbrfF\xcb\x12\xb9\x00\x9e\x94\x91|\x91\x95,H\xc7\x00\xf6\xa1\xb5\x17[R\x98+\xb7\'\xbek\x9f\x8fT\x98\xea;]IRq\x9ej[L\xde0m4\x95\x91\xa9\x02\xbaB\x80\x92@\x95\x8e>\xb5-\xac\xf1$\xe6DP\\\x1c\x10}\xa8\xb7v\x13\r\xc4y|\x103U\xe0XR\xf6E\x04e\xce\x07\xb74\xadqJ\xd2\xbd\xcd)$\xf3\x88,\x00\xcfA\x9e)\xd8\x05v\x8e*\xb5\xc0\x04\xaa\x07\xc1\x1c\x929\xa7\x89C\xc4v\x10J\x8e\x84\xe0\x9ai\xe9c5\x14\x92h\x8a\x17)|Q\x9b#\x00\xe2\x96\xe25yA \x10\x0eH5^\xd5\x1aK\xf0\\\xe0\x12\x06GAZ7V\x9b\xceU\xc0\x18\xc6r)\xeaT\xac\xa4\xae\xfa\re\x84\xc0\x10(Q\xec)/b\x84\xdb\x82\x84\x81\x8c`\x0e\xb4\x91\x01+l\xcfN3Q_\\\xb5\xba\x80\x101\x0789\xe6\x89#6\x9d\xd2[\x94\xe1\xb5\x94)\x05\x88L\xf5\xa9\xf4\xf7\x8a\xc6\t\xe5\x19\x91\xd4\x127\x0e:\xfbSb\x9a\xe4\xc6\xea\xd0\xa9\x0c8\x04\x90\x05,0\xc8\xf1\xbcL\x8a\xa5\xbd\r+y\x96\xee\xd3Rz]l\xcb\xee\xc9$BS\x80\xcc3\x81Y\xe4\x84\x94\xf1\x92\xdc\n\xba\x91\x03*\x06\x19U\x00\x11\xeb\xc5\x17v\xee."d\x8dB1\xc7\\c\x8am$\xf43I^\xdd\xc6G(\x90\x04l\x80:\x10*0\xb1Gp2\x08\xc9\xc6q\xcdOml\xe1\xc2\xbb\x0e\x18\x93\xcf\x18\xa9\xa5\x89\x1e\xe1K\x85\n\xb8\xe4\x1a\x15\xde\xe5$\x93\xb2\xfc\x08n"\t\x1f\x9a\xa0\x1f\xaf\x15\x14kle\x8ee\\L\xa7$\x81\xfdj\xfc\xb6\xf19\xdcf>^\x00\xdb\xc6*\x14\x868\xd4\x88\xd4\x13\x92A\xa2\xda\x95\x1b\xb4\xb7&\x90\xac\xd2+**\xa8\x038\xeei\xc66\x1bpx\'\x14\xd5\x04\x01\x90\x01\xf4\x15$r\xa1\x19$\xe4\x1e\x84U\x14\x93J\xc9l=A\x03i<P\x00V\xe4qN 8\xe1\x80?ZF\xc2\xae\t\x07\xde\xa9>\x80\x92\x11\x81?w\x07\xd8\x9aU@9)\xcf\xa8\x14\xc1"\x83\xc98\xf6\xe6\xa5\x13\x820\x1c\x81\xed\xd6\x8f\x99M\xb4\xac\x91\x97h\xb0\xceg\x9bp\x08\xcb\xb4}A\xac\xb9\xac]oVU "\x9c\x93\x9e\xa2\x9c\xb6\x8doh\xcc\x93\x1e\xa4\xe0c\x1c\x9a\xb41=\xa3d\x8f\xbb\x8c\x9a\xcb\xa9\x9d\x94[i\xdd=\x08\x9c)\x94\x82\xd9P\x01\xc0\xe6\xa4\x88F`d`y\xcf8\xaa\xd2\xc2\xd6\x92#\xa6\xd2I\xeez\xf1S\x0b\xef\x98\xc4c\x1b\x88\x1c\xf3\x8f\xce\x92Kr9n\x92Z\xa2\x9d\xdd\x88R\x92\'\x1bNI\xf5\xab\x13\xa1\x80\x07\\\xe5\x94\x0c\x8f\xa5iI\x12\\\xc0\x00`\x1b\x18 \x1a\xaa\xcc#t\x8d\xd4\xb6N\x01#\xa5;hR\x93i\'\xad\xaf\xa1\x9bwl"\xb5IK\xb3H\t$c\xb5Y\xd1n\x95Y\xa4b\xd8Q\xc8#\x00\xf3VZ\x1f?r\x91\xc1\x18\x153i\xd1\xa5\xa60\x06s\x9cR\xbe\x859\xa7\x1eW\xbb)=\xda\xdd]\xb2\xaa\xe0\x1e\xe0qMh\xa1\x82\xeb\x12D\xa4\xe0\x1c\x91\xebVm`Hc\xda\x14\x13\x92s\x8ei\xb7q\x19\xd9\x8a\x8c\x10\x074\xda\xb2\xb9\\\xe9>U\xa2\x18!\x05\xb0\x18`\xf2\x06k:(\x98^\x86$\x90[\x03\xdb\x15,K8\x90\x16\xce\t\xc6j\xe2D\xa8\xae\xcc\xc0\x1022qF\xabvW3\x8d\xee\xc9\x82*|\xe4\x02j\x19JG(u\x04n\xe0\x80*X\xd8>\x17 \xfe4\x92!\x03 \x02GbhO\xa1\x9avz\x9a\x96/h\xd6\xc5^\x142\x1c\xe0\x9e\xb4\xb3\xc1\xf2eG\xcb\xe8+:1\x85\x04\r\xa7\xda\xadG,\xee\xc0+\x120\x06\t\xaaR\xd2\xc8\xc9\xab;\xa6E\xe5\x88\xc6S\x86\xf4<S\xee\xadZ\xe4\xa4\x8aB\xe0\x00@>\xd5\x13\xcc\xdey\x0c\x08+\xc9\xf7\xa9\xd5\x9c\xae\xe5b\x01\xa1\xab\x83\xbd\xd3C.\x12FP\x11\x8a\xe0\x01\x91D6\xac\xb8gs\xf5\xa7\x86\x97v\x1c\xe4{\x9aIK\xed\xf9\\\x9fc\xd2\x9d\xba\x15\x08\xbb\xa4\t&\xd6%W88\xc9\x18\xa9d\x95\xa6P\xa7\x8c\x1c\x81\xe9U\xd4\xbe0O\x1e\x82\x9cK\x11\x85$\x1fZ/ft\xbaq\xbav,\xa5\xb3\x15\x04\x10O\xb9\xa8\xe4\x84gk\x90\x07\xb74\x81\xdd\x10\x12\xc4\x9aa\x93w$\xd2\xba\xb8F-;\x8b\xe5&0\x00\xc5Mo\x0f\xcc9\x18\xf4\xcdW\'=\rH\x12@\xa1\x97\'\xe8)\xa6\xb7*KK\\\xb8mH\xf9\xb7\x02=3U|\xa0% \xf4\xf4\xa7!\x9b\x1c3\x0f\xc2\x93\xc9\x99\x98d\xe7\'\x19\xcf4_[\xa2\x14\x92\xbd\xda&\xdb\x10A\xf2\x8c\xd3\x90\xa1\x04\xb0\x04\x01\x9cUo\xb3LX\x82x\xf5\xcd\x06\t\x97 \x9e=sO\xa0\x9b\x8b\xd2\xe4\xcc"#*\xa0\x1fjO%q\xb8c?Z\x80\xa3\xe3\x194\xe5.\xbc\x10q\xf4\xa3d5d\xb4f&\x9e\xb7\x04:H\xa4\x82H\xe7\xebRm\x96\xda\x02\xad\x11e$\x9c\xe0\x9e)\r\xec\xe8w\x06`}\xabJ\xdeYnmJ\xb4\xcc1\x93\x9a\xce\xec\xc6r\x94n\xdaVf]\xf43=\xb42\x85*\x14\x92G|c\xd2\xa7\x92\xd1\x8d\xa2\xce\x14\xe4\x8cp9\xe0Ts\\O=\xe9\x83\xce`\x80\x01\x9c\xd5\x91q,AQ\xa5%s\x8c\x83\x93C\xbab\xe6\x92Ko\xf8\x03m-\xe6\x11\x83\x85\xc9=\xce\rY{K\xa2\xa1\x80\x8c\x81\xc8\xcbc\x15\x9d9\x99$IE\xc3\x84\'\xa0\x00\x9f\xca\xac\xa5\xcb\xcbh\xe4;\x12\x01\x03<\x1a/qK\x99\xbb\xabk\xeaK\n\\\xb6L\x81\x15G\xa3S\xdc\xca\xab\xc6\xd6\x1fZ\xcec4\xca\x88\xac\xcb\x83\x92}jXc\x94+\x16f9\xe0f\x8b-\xd0\x9cl\xee\xda\xf4-B\x93\\\x0f\x95\x14\x1c\xe3\x93\x8a\xb8\xd6\xd20\xdaV5\xe3\x04\xee\xaa\x10\x17F\xc0\x90\x81\xe9\x9a\x1ef2\x10\xd9#\xdcSMZ\xcc\x89\')h\xd5\x8b?\xd9\xd29\xdaY@\x1d\x08"\xaajZ\x15\xd5\xc0U\x85\xd4\x03\xc1\xf9\x80\xedR\xf9\xf2\r\xa09\x00\x9c\x01M7RBw\x96,\x07j\x9b\x0e\x0eqi\xa6\x86A\xa5Kn\xc9\xb9\xd7+\x8c\x8c\x8cU\xb6\xb0\',eQ\xec\x18TMs\x1c\xf1\xe43\x16=\x88\xe2\x98aa\x131\xc9\x04q\xedN\xda\x8d\xf3=[\xb3\xf4\x13\xec\xce\xb2\x1f\xde\x82\xbe\x80\x83V\xad\xe0r7,\x9bNq\x9c\x81PZ\xc6\xb0m2\x00\xd9=\xeava\x93\x80\x02\xfaSZ1\xb5&\xed\xfa\x0fk"\xccK8$\xf5$\x8ei\xe2\xc9B\xe1\xa7 zdUc)\xe9\x96\x03\xd8SX\x13\xeb\xf5"\xa9\xb2\xe3JOw\xf8\x1a/\x04R\x93\xb6@\x00Q\xdcS#\x8a\x00\xf8v,\x07\xb5PE*\xd9\'\x83S\x07\x03\xa7\x14!\xb8r\xab\\\x97\xcb\x80\x1270\x19\xec*D\x82\xd9\xce<\xe6\x1e\xe4\n\xaaA\'9\xa3\x01\x86\x0f"\x93\xbd\xc6\xde\x9a6Yx\xad\x17\xe5\xf3\x9c\x91\xfe\xcf\x14\x9e]\xa69\xc9\xfa\x8a\xaa@\x1c\x0e\x05\x19#\xbd4\x89w{6Y\xdbh?\x84\xfeU \xba\x81\x06\x10\xb2\xe3\xd0U\x1d\xe3\xa5(\x00\x8e\xd4\x12\xd5\xf7m\x97\xfe\xdb\x11\x18,\xc7\xea)\xbfk@A\x03 t\xc8\xaax\x14q\x8a5\'\x92+b\xe0\xbf@~\xef\xe9M7\xa0\x9ePb\xaa\x85\x19\xe4\xd20P8$\x9fLP\xc5\xc9\x1b\x96\xfe\xd8\x9f\xdc\x14\x1b\xc5#\x05F=*\x8d/\x18\xebE\xc7\xc8\x91\x9b\x93(\x01UA$\x8c\x13\x80*\xdd\xa9(\x9b$!Fz\xa9\xcdPf\x11\xde\xb4[I\x0c\x06\x08\x1c\x03D\xa5\xadPF[$\x12\xd9\xcfc\xda\xa1\xb3\xa1\xc3\x99Y\x16\x9e(RWea\xb8\x8c\x02H\x06\x9e\xd1\xaa\x11\xb8\x02p\x0eMaE{\x03\xdd\xabM\xbb\n\xdc\x8cg5\xd4\xcf\x0470\xab\xc5\x80\x85@\x03\xa7jI\xeaeQ84\x9d\xf5\xeaf\xa2\xb3\xcf\x80I\x1d\xaa)\x9d\xad\x9f\x90H\'\x18\xc5iDR\x03\x82\xa0\xe3\xbdG9IO\xdc\x14\xdd\xae%7}V\x82C\x1c\x9eX\x94\xb1(z\n\xc7\xd5u\x1b\xd3{\xe4[\x16Q\x81\x8d\xb5\xad\x05\xf0\'\xca<(8\xc1\xe9R2F\x92y\xca\x80?\xf7\x87Z-f\t\xd9\xdeI6B\xb6\xb2\xc3h\x92J\xe5\xa4#\'\x9c\x9e\x94\xc8\xae$\x96?\x98`\x02G5jgg\nrK\x13\x8c\xd2y9\x8c\x00\x00>\xb4$J\xbd\xae\xf7\x18\x01hC\xe7\xa1#\x14\xc8\xd5\x88\xc1\x1b\x8eOZX\xa0w\x0cw\x10\x07j\xd4\xb7\xb6\x8a8\xc3\xbb\x9c\xfe\x14%}Q{&U\x87L\x91\xa7 \x9c\x0c\x03\xd7\x8ejy\x83D\x0c\x07\'\x8e\r,\x97\x0f\xbc\x85\x90\x91\x8cb\xa3-!m\xc5\xcej\xac\x9b\xd4q\x84\x9d\x9c\x88\xf6\x14\xdaO \x9f\xca\x9e\xf1\x9d\xb9\x06\x86$\x81\x9c\x93\xeah\xdcH\xc74\xcd6\xd4h\xde\x06\x03\x11K2\xba\x8eX\x9e3O\x03"\x9a\xf9\x03$\xe6\x8d:\x87:\xb8\xc5\xe4{\xd1\xb4\x83\x9c\xd1\x8c\x8c\x83\x8ar\xa9\'\xaeh\xb1\x0eW\x13$\x0ei7w\xa7\x15$\xe0\xe4R\x98\x88\x19\xcd;\n\xe8\x88\x92O\x06\x82\x8d\x8c\xe4\xd3\xb1\x83\xcd?p\xc7AJ\xdd\x87{lB\xa0\x93\x8eh \x83\xd4\xd4\xa0\x8c\xf0\x05#\xaf\x19\x14\xfc\x98\xb9\xb5#\x04\x9e3O\nO9\xa4\xc7\x14\xf0p\xb9\xc6iZ\xdb\t\xbe\xc0\xc8\xcc\xb8\x04\x83M\x00\x81\x82rjP\xe3\x1d9\xa60\xc9\xce(M\x897\xb3\x19\x8e)\xbbNz\xd3\x9b driTdr@\xa3\xccw\xb2*\xc1\x17\x96\xe4:\x16`I\xdcEV\xbd\xb3\x94N\\\x86 \x81\x8e+a\xae\xb1\x1aa\x01\xdcq\xedQ\\\xdd\\\xca\xca\x81T)\xe3\xefTX\xbau$\xa5{h\xfc\xce@G\xe4\\\xbb\xc9\tt#\xa6\xd2k\xa0\xb7\xb8\x9eK%h\xa1!r@\x18"\xac\x88\x8a\x06,\x15\x89\x1d\t\xa7\xfd\xa6X\xa2\x0b\x08\x00\x8e\xd9\xe2\x8b%\xa8\xaaM\xcd\xe8\x93\xf9\xe8U\x8c\xcd<\x1b\x82\x1d\xf9 \x8c\x1e\xd5v8X\xc47)\x07\xbf\x15V\xc1\xee\xad\xa7y&\x9c\xb0nBd\x109\xab\xed<\xaew\x078=\xa9Y\x18\xcd\xbb\xb4\xadc&{\x19\x9eB\x10\x15\x1e\xa2\xaf[\x82\xf1\x8br\ta\xd4\xe2\x9b$\xf3#\x12\x19\x81\xa4\x8aY<\xcd\xea\xc41\xef\xde\x84\xfa\r\xf38\xf4,\x0bIQ\xb2\xcaJ\x8e\x953\xc2\xc2 \xc0\x13\xf4\x14Cs<\x84\xa3J\xc7#\xbdN\xd3\xb2[\xec\x0cwd\x9c\xd5!EI\xb5{\\\xaabq\xb4m\n:\x93\xebH\xf1\xca\xe4"\xa9 \x9cs\xd2\x90\xcd3\xbe\x1aBG\xa1\xa9D\xb3l;e+\x81\x91N\xec\xeaW\x8d\xb6\x19mg*\xc9\xbf\x00\xf3\x8cf\x96X&,HP?\x1ar\xddH\x83!\xce\xee\xe6\x91\xaed\x94\xe1\x9c\x9f\xad>\xa2nnW\xd0z\xc13\x91\x92\xb8\xc0\xe3u\x06\xda\\\xe3\x0b\xf9\xd4e\x99W;\x8d&\xf7<\xee4\xacf\xd4\xb7M\x12\xfd\x92n\xdb\x7f\xef\xaa\x1a\xc9\x88\xc30\x07\xd8\x8a\x8b\xcep>\xf1\xa6\x99\\\xff\x00\x11\xa6\x91\tJ\xfb\xa2qe\x81\x82\xe0~"\x94Z2\x9c\xa4\x8b\x9f\xf7\x80\xaa\x81\x98\x9f\x98\x92)\xe1\x86q\x8a,\x87iw\xfc\t\xcd\xac\xc7\xefH\xb8\xf6`i\xc2\xc9\x87W\x1f\x98\xa80\xb8\xca\xb1\x07\xe9Ngr\xc0\x86 `\n}6%\xa6\xf6\x7f\x813Y.\xdf\x9a@>\x84R\x0b\x08\xf1\x931\xfd*\x06\x1b\x87#&\x94\x03\x8c\x13\xc7\xa5\x17\xea&\xa4\x96\xe4\xbff\x85O\xfa\xd2\x7f\x01CE\x161\xbd\xbf*\x85\x90\x0c\x05\xc0$\xe34\xf58\x1bI\x19\x1d\xe97}A\xdf{\x8e1E\xb7\x05\xf0?\x0c\xd0\x8bn\x87%\xd8\xfbc\x8a\x85\x90\x16\xc9\x19\xa5\x00/\xf0\x86\x1e\x86\x87`\xb5\xd6\xe5\x86\x8a\x13\x10\x93{\x00I\x1c\x0fJ\x88\xbc\x00\xed\xdc\xc7\x1e\xd4\x9b\xcb(\\`\x0e@\x15\x11\x03q\xc8\xa3\xd4\x12\xee\xd9a>\xccNps\xeb\x8a\x01\xb4\x0f\x86R~\xa2\x98\xb8\nF\x06H\xe2\xa4"\x19\xc8P\xbb[\x00d\n{\xab!4\x93\xdd\xd8\xc5K\x96\x8dD23\x15^G\x14%\xca\xcaz\x90\x01\xe0\xe2\xab\x19\xf7\x92\x0ey\x00})Q\xc1;\x00\xc1\xf5\xac\x93v\xd4\xe9qVm\xa2\xc1I\xd9\x89\x89\x8f\xb1<S\xe4\xf3V\x06\x01\x8f\x98F3\xdb\xf3\xa6\xc1;\t6\x12H\x15c~[\x0c\xc3\x1e\x84\xd3\xbe\x84I\xb5\xa3F\x15\x94\xb7Ot\xe5\xf9\x00\xe3\x93\xefZ\xdb\xee\x84\x9b@\xd80\x0e\xe0i%\x8a.v\xe1s\xdcsZ\xe9qjm\xc2\xb2\x02v\x81\x9csBi\xb3:\x95,\xee\x91\x99mw\xf6\x99\x19YI+\xc1$\x1ey\xc5Z\xf2\x19\x8eUq\xf5\xe0U\x8bkh<\x87#\x08\x18\x9c\x11\xd7\xaf\xa5H\xad\xbe=\x8a\xc4\x80q\x921V\x92j\xe0\x9d\xdb\xb2\xb1Ys\x11\xe4s\xed\xcd+\xb9#8?\x95XH\x826\xe6 \x8a\x8e@\x0b\x12\tQ\xec(f\xb1j\xfa\x152Cg\x9ayrW\x03\x83Oh\xf9\x1c\x93\x93\x8c\x9ac"\xafs\x9fLR6VcA8\xc7zpR\x0eG\xe9J\xa9\xc6iA \xe0\x1c\x1fZbn\xdb\x08\xe4\x90\xa3\x91\x83\x93Q\x92G956\x01?1\'\xdc\x0c\xd3\x84`\xf0\x0f\x1e\xf4>\xc6nH\x8fx\x11\x9e2H\xc0\xa6)%I\xe4\x00*p\x15\x0f \x11K\x1b\xc6"(\xca\t$\x9c\xd0\xb5!\xb4\xb6\x12(\xc4\x80\x00@\'\xde\xa3-\x82F:\x1ct\xab\x08"\x05HA\xc1\xe6\x94\xec\xdcHP\x05\x17D9k\xb1X\xb3\x01\x95\\\x9fz\x11\x89l\x11\x8a\xb6J\xed\xe1j\x1f\x979*\x08\xa7}\x01J\xeba\xbb\x9c7\x04\x01\xeb\x9a\x18>2pG\xaei[a\x18#\x03\xd8R\x92\xa5\x86\xde\x98\x1cR\xbf\x90_]\x88\x9cJ\x08\xc0\x07\x8c\x8ei0\xddI\xc1\xa9\xc3\x80rFi\xae\xc0\x9c\x81\xc5;\xbbZ\xc0\xa4\xf6\xb1$1\xca\xc4\x12\x17o\xaey\xa6\xec\x95\xa5*\xaa\x08\x1d\xf3M\x13\x900\t\x14\xd5\xb9u,\x00\xc1#\x82\x0f4z\t\xa7v\xecX\x92\ts\xb8*\xf4\xe9\x9a\x8c\xdb\xcb\x91\x95\x00\x13\x8c\x83RCrK\x00\xc7\'\xde\xae\x0b\x88\xf6\x90@\x04\x8e\t\xedN\xcb\xa9\x0eR\x8e\x96),\x0c\xa7\x93\x9ax\x8c\xff\x00\x0e3\xeejV*y\x0c\xb9\xf4\xc8\xaa\xed)\x0epiY\x02m\x98\x11\xa4&\x06\xf9\x81\x90\x93\xcf\xa5+\x04@\x17hb\xa3\'\x1c\xe6\x9b\xe5[\xc3\tb\xa4\x92I\xe0U\xcbymg`\xb1 W\xc0\x04\xe3\x06\xb1l\xe8\x93\xb6\xba\xb4A\x12\x8d\xc1\xb7\x90\x0fc\xc5>h\xc4\xab\xb5F\x0f\xadO\xa8\xdb\xc7\x17\x93\x90\xa4\x93\xc9\xcf\xb59&UR\x161\xc8\x00g4\xf5\xb9\x9f;v\x94J\xd1ZH\x00\x00\x82}\t\xab\x11\xc4\xcc\xdb\x08\xc1\x15<2\xa8`\xc1\x14\xb7\xa6j\xe0\x9a\x15\x1b\x8c\n[\xdf4\xed\xdcI\xc9\xcbTTd\xc3aK\x02\x07@8\xa9\x90\x90\x81@ \xfa\xe2\xadG*\xc9\x19s\n\xa8\x1e\x86\x93\xce\x8c\x1c\xed\x15\xa6\xe6\x9c\xcfklWr\xc1q\xc9\xfc)\x8aH9*O\xb6*\xcb\\.8@O\xbdFn\x98\x0f\x96%\x07\xebJ\xed\x94\x9c\xad\xb1\x1b9<\x85>\xdc\x1a\x85\xc1\'\xee\x9f\xca\xac\x99\xd8\xff\x00\x08S\xea\r;\xed\n\x17\xee\xf3\xebAJMl\x8a\xdc\x80\xa0\x03\xc9\xc61F\xc2N\n\x12>\x95!\xb8\x19\xc8\x1c\xfa\xd3\xfe\xd8\xc3\x9c\x9a6&R\x97DW}\xe1\xfeEe\x18\x03\x80iU$\'\'q?J\x9d\xae\x9d\x87\x04\xe2\x969&\'$\x9c}i\xf43r\x92["1\x03\xb1\xe7#\xf0\xa1\xad\x1c\x0c\x8c\x9f\xa5X\xf3\xc0\xceX\x92\x06pE*]\x97;S*}E\tv%\xca{\xa4@\xd6\xf2\xa8\x01A\'\x1d\xe9\xebo)\x19`\x07\xd0\xd2\x89\xe5\xc9Vs\x9c\xf55\x11\xb9\x981\x02R\x7f\x1aIt\x15\xe6\xf4\xd0\x94\xc3!\xe0\x80\x07\xaei\xbff\x98\x9e\x02\xe3\xdc\xd3\x05\xd4\xa4\xe1\x9d\x80\xf6\xa6\xbd\xd4\xa5\x86\x19\x88\x07\x9c\x8a\x12\xd6\xd6\x05\xcf{hJl\xe4\xc7\x05s\xe9\x9ao\xd8\xe4\x1c\x82\xb9\xf4\xcd*\xca\xc7\x9c\x91Q\xb4\xad\xb8\x80M\x17\xe9q\';\xda\xe8\x90\xda1\x1c\xb0\x07\xd8\xd0m_\x18\x05\x0f\xfc\x08T\r#\x81\x9d\xc6\x80\xe7\x19\x00\x83\xeb\x8a\x1f\x91V\x93\xeaL-\x1f9b\xa0{\x1aQh\xdd\xca\xe3\xd75\x14d\xbc\x81Y\xd9A8\xc8\x15j+\'\x9c6\xd9\x88\x03\xb9 Qk\x89\xb6\xb7\x7f\x81\x08\xb4\xc3dH\xa3\xf1\x15$\x96\x82B?z\xb8\xc7L\x8a`\xb2o4\xa99>\xb4\xbfa\x19\xe5\x88\x1e\xdc\xd3\xb09k\xbf\xe09\xacb\xf3\x03\x89\x15F\x00\xe0\x8a\x1e\xd8\x05\xc8p\x7f\x11R\xad\x84*\xc0\x16\x04\xe0\x1ep)\xd1\xe9\xcb&J\xc8\xa83\x80r\x05\x16\xbb#\x9d-n\xfe\xe3\x9d\x84\xab\xc9"2\xe4\x01\xc1\xed\xd6\x88\xa0\x8e9\xcb.A\xfaU(\xef\x1e\x07d \x92F2x\x15j[\xb6\x8a=\x85\x01.\x00\x04s\x8e\xf5\x95\x9e\xc7CR\xbd\x97P\xd4A\x9e$e\x90\xe5I\xe2\xa6\x9eR\xb6j\xe8\xa3 `\xfeUVc\xe5[\xa2\x85\x05\x98\x9eMY\x0e\xabd\xfb\xc6@\\\xf1\xcd;-\xc4\x96\xcbt\x99b\xd1C\xc6\x1c\xa8\x0cj\xf4i\xb8\xe0\xf4\xa8m\xd0\x1bu\xdax#5m\x99cP\xa4\xe0\xe39\x15QJ\xc5\xb5\xae\x83\x18\xec\x05A\xc0\xa8\xdc\x82\xf9\x1c\x0c\x01J\xcc\x18aN}\xea&9\x1bG_Z\xa6\xcb\x8cBC\x82\x07\xa9\xc5(_SQ\xb1\xc8\x00\xf5\x14\xf2\xd9 \x80@\xc0\xa4\xcaqv\x1d\xd0f\x94\x95+\xda\x98T\xb0\xebI\x94\xdb\xb4\x01\xbb\xd4S[\t$8&C\x1cp\x06i\xa41\xe3\x00\x0f\\\xd4\xa8T\xc6\xc0;d\x0c\x90G\x15\x16\x0e\xee\xb42$\xf5d\xa2@\x14)A\x81\xdf5*J\x87\x82\x08\x1e\xc2\xa9\xb1 \xe2\x967\xda\xd9"\x92\xb9\x8c\xa2\x9a\x1e\xcc\x0c\xa4.H\xfaS\x941l! \xfa\x8ab\xb0\x00\xf1\x93\x9c\xd4\x90>\xd6$\x8e\xa3\x02\x9d\xd0;\xd8r\x8d\xcf\xb5\xc1>\xe4Q\xb26r\xaa\xa0\x1fZY\xa6%p2\rF\x1c\xa8\xce\x0e}hLI6\xae=\x15U\xb2\xe0\x81\x9cd\n{\x10\xe3jD\xab\xfe\xd0<\xd1$\x84*\xa89\x03\x92\x0529B\xc9\x92\xa7\x1e\x98\xa7~\xa0\xd3z\xa41\xe3d\x93\x04\x93\xc09\xa9-\xe2\x0f.\t\x03\xeah\x95\x99\xfebH\x1e\x95\n\xb3+d\x1cT\xde\xfa\x85\x9bZ\xee:t\x02B\xbc`SF@\xc19\x1e\x943\xe4\xe4\xf2i\x81\x898\xc1\xa6\xd0\xd2\xd0qp\xa7 r)Vg\x04\x85b3M\xc0\x07-\x9c{\x0c\xd2`\x13\x90N=\xe8\x1aHy\x9a`x\x91\xb3\xedS\xa1\x9d#\x01\x8f\'\x9c\xe7\x9ej\xb2\x86C\x90MJ\xd7\x0e\xea\x14\xa8\xfa\xf7\xa5\xa5\xc4\xd3\xd9$6WrN\xe6&\x8d\xac\xe8\xa8I\nO~\x94\xc2}E8\xb9e\ny\x03\xb5=C],\x7f\xff\xd9', 'label_tif': b'\xff\xd8\xff\xe0\x00\x10JFIF\x00\x01\x01\x00\x00\x01\x00\x01\x00\x00\xff\xdb\x00C\x00\x08\x06\x06\x07\x06\x05\x08\x07\x07\x07\t\t\x08\n\x0c\x14\r\x0c\x0b\x0b\x0c\x19\x12\x13\x0f\x14\x1d\x1a\x1f\x1e\x1d\x1a\x1c\x1c $.\' ",#\x1c\x1c(7),01444\x1f\'9=82<.342\xff\xc0\x00\x0b\x08\x01\x00\x01\x00\x01\x01\x11\x00\xff\xc4\x00\x1f\x00\x00\x01\x05\x01\x01\x01\x01\x01\x01\x00\x00\x00\x00\x00\x00\x00\x00\x01\x02\x03\x04\x05\x06\x07\x08\t\n\x0b\xff\xc4\x00\xb5\x10\x00\x02\x01\x03\x03\x02\x04\x03\x05\x05\x04\x04\x00\x00\x01}\x01\x02\x03\x00\x04\x11\x05\x12!1A\x06\x13Qa\x07"q\x142\x81\x91\xa1\x08#B\xb1\xc1\x15R\xd1\xf0$3br\x82\t\n\x16\x17\x18\x19\x1a%&\'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz\x83\x84\x85\x86\x87\x88\x89\x8a\x92\x93\x94\x95\x96\x97\x98\x99\x9a\xa2\xa3\xa4\xa5\xa6\xa7\xa8\xa9\xaa\xb2\xb3\xb4\xb5\xb6\xb7\xb8\xb9\xba\xc2\xc3\xc4\xc5\xc6\xc7\xc8\xc9\xca\xd2\xd3\xd4\xd5\xd6\xd7\xd8\xd9\xda\xe1\xe2\xe3\xe4\xe5\xe6\xe7\xe8\xe9\xea\xf1\xf2\xf3\xf4\xf5\xf6\xf7\xf8\xf9\xfa\xff\xda\x00\x08\x01\x01\x00\x00?\x00\xf9\xfe\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xa2\x8a(\xaf\xff\xd9', 'label_tfw': b'1.0000000000\r\n0.0000000000\r\n0.0000000000\r\n-1.0000000000\r\n2579588.2550109820\r\n334042.4955805260\r\n'}
```