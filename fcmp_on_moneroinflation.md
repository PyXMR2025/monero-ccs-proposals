---
layout: wip
title: Integrate FCMP++ into monero-inflation-checker
author: DangerousFreedom
date: February 25, 2026
amount: 26.25 
milestones:
  - name: Delivery FCMP++ Python tools  
    funds: 26.25 
    done:
    status:
payouts:
  - date:
    amount:
---

## What and Why ?
The core of the work consists in creating Python tools (independent from the C++ or Rust code) to perform the generation and verification of the FCMP++ membership proofs. Once that is done, an explanation of the meaning and/or origin of each character of the membership proof in the new FCMP++ model will follow. Very much like it was done for the legacy membership proofs available at: https://www.moneroinflation.com/ring_signatures_mlsag (For MLSAG for example). To illustrate, given the transaction below, I will explain what exactly is in the alphabet soup `fcmp_pp`:
```
{
  "version": 2, 
  "unlock_time": 0, 
  "vin": [ {
      "key": {
        "amount": 0, 
        "key_offsets": [ ], 
        "k_image": "729b9867ed2760f237107fb31f0489306f4c897b42f814cedee28738ae4a8ba9"
      }
    }], 
  "vout": [ {
      "amount": 0, 
      "target": {
        "carrot_v1": {
          "key": "46d7ab6cbb4aefcf9202ace04883e75d046df420242353fdc035009619758cd5", 
          "view_tag": "60f54f", 
          "encrypted_janus_anchor": "2a9b5f886fc9982fda8a746eb4e4634a"
        }
      }
    }, {
      "amount": 0, 
      "target": {
        "carrot_v1": {
          "key": "6206c274a0bbb377405fbdfbd81d6131044c37dc3c5757bc15fce763ab637d7a", 
          "view_tag": "5ea23b", 
          "encrypted_janus_anchor": "5da958642162daeb4b7881f58f433099"
        }
      }
    }
  ], 
  "extra": [ 1, 8, 40, 61, 95, 171, 109, 147, 160, 243, 163, 185, 191, 4, 237, 36, 35, 24, 196, 98, 205, 152, 159, 215, 133, 56, 170, 126, 176, 243, 45, 11, 70, 2, 9, 1, 121, 161, 1, 141, 237, 85, 233, 108
  ], 
  "rct_signatures": {
    "type": 7, 
    "txnFee": 500346000, 
    "ecdhInfo": [ {
        "amount": "693d583458665def"
      }, {
        "amount": "7484b23f54be2d56"
      }], 
    "outPk": [ "b5b3abfa711c67dae61cae0466552f103d748f96bd95748048f40018d458fbf7", "d586a17994dfa814859ddc412947086cb04b2cb86d297ba21cadef8d12e6efb1"]
  }, 
  "rctsig_prunable": {
    "nbp": 1, 
    "bpp": [ {
        "A": "ca1a180d9afef7aa64e2849fa6917f41f04fd0fdd32575cfc45660317d6a795e", 
        "A1": "f87820006ce792107b0ed6694996ca4c3b662db8c3558bbab2194daa66599ff9", 
        "B": "50e9a6b4133dd967ba5bbb2c1392e2c0dd1f0fe483b26b6d32745daeff77d97b", 
        "r1": "79cbaf115e1fcc1526058f6ef09a08f8814cdd830583e56e8feafdc56271e50b", 
        "s1": "7d41ea53f80d785d8337be15170841879df3aababc544fc7e48e33aca0c4b002", 
        "d1": "8d6afbc8400656ad550c0b5d3e1c954e50492bc27249a2117dcd0448f243df07", 
        "L": [ "37fbaff1b13f19cffc61e7d540c07ea5254121ffce2c23167f87e90c22bb10ac", "69e15c64431d038cc14677ce5135bf05601a9ab1ec232bb66316bbc674c28b10", "0123515ccbd9196a343b61dfbe704e1dd21da33fbfaec82439364c561a5a55d6", "2b13b338a563c84f068e4bf6d5f1e301ef0ef93627bed759f09282e850c136b8", "1203c87a0985198d36398b6e1e4101e2134959e3741ce0fb041b34ca605d244d", "1f50ea02eb9cb62f1274be3f902520de21ce8908b0f379d3e2fda93ee516b3a3", "38a2d6152103bf0383daead8341d0428ce7d9deecd622f8e0c6f1eabba20dd30"
        ], 
        "R": [ "9425e0cd679332099ac0820ece1c45eaeacaf46f3a5dc0cebdfbfb411a62baf5", "3347a1ce66d82609cb06752c12d90e1f1be225a8c67a28e48a6ad05533869c55", "d4c481f82eee2f5102adf3c49b2010fc56a17bf57c639155f4999c61400e6ba6", "c3aa503c3282589796e778b7f86284efbf183c0fce30c33ed4dbd0f360af0a38", "2adaac770cf0286e53e47e21b1bb6ebcb2538e95d4e17972d4d363ae690ef5de", "431b64ad11f415297897e4e71713f26d9f2896d0ad4a89f5e26c46347aa0819a", "e9a529ab9469f1293d1457f02a1148c38a2986c71204ec8550af404b4f5f6698"
        ]
      }
    ], 
    "reference_block": 2904506, 
    "n_tree_layers": 6, 
    "fcmp_pp": "2c73919efe1d1fe30bb451b7a17edf28270d322eec55bb615c13f0f14957269599c30120ea8d7a9e837b3f4ca75112d35fd9ba9f814f8f1bdd7e915df88cf866e120322c07309c171133fac2f3348dc542ebd9855ffb8a88e20b343d3e8086f664ffe1f0548c4b3f6ddcb58ef5499e1a219e8595bd7ca6df6264faa0e81b9c1dac9b35e93b2d2afb25fdce0825668ce59ff08aadbc0b9edb9db6721ede5e7a10e0a10bac26d921461066ea4e8898a0b69c5f119b1ce38e24c6f6873b094f36cff95f18aeb651942ef65aa0fbd28fb75bf882a0bce42345339fc2ec9ffaf11bade4be79a22226aa9a5f6774326ce806bdbdaf0465d4c788b58da26236d007460ef8462a470c9cfe1100ecf4179e127093982a82cb057d6587b994766b44e075bc538052b876a9b8436f9786c1d2f61617aa51b48f5bd630b630e6628718830e095a039328509063ccbaf6041ed0bd727223bce160bd7bb310bfc7357bbc0b1c0289ce9a179599be92bbf1524134d7228efbafee6f1a93818d0d5ca84da630290722ad18c319358681ee66605592aa0c72c5820fca7d32387184474d0d0b5436065e1fef25c97bd012d2a048798f4a5c526e2c9a06a3f1bcb8882ca74c6d166f0046464b1e71451f5a6de9e8ea9f327fb71f50b791a3500eb7c37c7bc181788b05889d54bd3e0a6c90d7c0923f85b50591bf1b37b1345f0b6f037b39b6d0b8ecd0d4b178bb0572a39054385fafd0f927e7fa035a1cba969c0dc56d58b0847798ee30bdec1365bd021999899a33c74f1ed7c8f1dab182b33739023797d52635d6b39713fe2144d34b164cd320f332b86f9d96faa1369ac06e20533c6b257fbcd60d910a1369c1950b098defd54315e89a04c6fedd219be9a8d0d554ea0d2592d6957caaaf4616e85bcf7ca6388835800fb08aac4f51bec08713c00922e502fe1acb8dc43f72cd9d55ccf2039257d9547ede0eb358fad5732dbe77b5fed849fed1d5ca3f4f213acbf0ffcf487bd3936662f2e0abe12dae21dee1ba1c46382c18375d14782ca7a433b3f6fc850639aefb55b154a30da5d4f8bb1d2e5adc0bc8b6678f26e767fc536d2681fdd748153fbc4370979960724aab316090a5850885326ddce86377b3bb3e5bdda7b29d0bc03661cd002a5670a42a67717087927100840533fecbe52701ce9757f489c544ad95b10e4f5a1091e9e093567c22d179e990c209b1f8a88afa9244c7c3470184d39cd9021a398b33ee340d7a5df0936a8d4c1fcf3ce2bb89f27abf2fa8233a8c8a29340b9a0eaec5b366348a2d6db315f0e87f669120d423dc938ac2c03ad6d7730b53f13a60ee6f3a039e0139c76c18c83fff1c7a3ecd55ff0b998b69a16123159118e5285cb5dcf6a21e6d663741169a8696f921fca41be5ed6354e09f85da38cad04c121e10406089bf70237f795bd8b7a74cef65bd72166a1f06019af0f7cb8df19d21bab7cfe3d67975894b080fa2e7de53189bda872b3ffbbc32a8e6bbd76c16d2b4e86acef62128f6de88c839c5624907508ade3d62bb127cb3566bc10834a37faa67ad2eca712c7983cb0483e072a2000c3a9a317ce2ab926f1eeabefd1dd252fa2444286c52beeb182382d17914c95536e0f5ba30c5c889a937d327d20300728bab9aae850c9d3f540217ba22d23aadcd203d4892d58ed83254d0a351865acd436907962f0acea94699b2874a131b39b17c3fc748f1de0d86ec2d374ec0f33ced2802110564dc43e21ed96be55b932aa07bd9b1d50da03c60f0edb15ab06a7d7f8b608a0cd44ad68100bd0c9c67f0ad1d01bc12e5b7196884e8f46202ecd9f2dd4fd55653b37b5c037826bad88fdd4f46968d6eb6bb19c27a96f0ba0ff86a75f650e6f930500e946c4d05a8e447e0eea7b4737410a4435ff70ff9d9a7ebb4764c08ebc346ca0ca2cdfbd52b43b4798382405c229444e71404b7c7bf773747c57caea24d49fadccf1e8fdbc47db6e5ef052a4de310c3176abba7e02e13ae96b6c1046d2c01f40db1e9c4e35f6ccbbff25a6e90bc47ba277b37de731533fbf3e8496ff7d53b9bfd98de063d5ae6e24a6b31634cd4ca334b487a077d5037fdfd959011dfd1b51de336ab5f2d81a9ddf9a406b771ba159640c9ad2bde64cf97282191e011ef7ed35c8737786c915cd17710d38701dccc788569e185c04a5549fece431931089d8082818b7b553ef4f49327715e8c8ce4fd3da272632cb9a1ed8d4f68b7457e79927b298efeb762c07a5655d0ea0dd464018e92eb5ae1eb03d23b0bc12b087a2074db00b8ec0d8aa7fc75b92cb59737a0d8d57629d2a8c335351ca4ef4122c3b1d6642bd2b73e41cc6aafe316ac62f142a1b9d0284f406347dea4b9b68ccf566d6fa25a7515e133501d4ca1bed9601b8b24b442792f38c24498fa727a7dac3272a3895a02a2d598f761a0f81fe60f0e633e8abae6ab60c74fb9a714b3cd14a98822dc766264a8e357f65b3923d5f121ddf826155e69c76525d09269437beb99dc880200c7496972191630c995e6839bb0c58505bfc250d835125d55b1a867bf1038ef914a877f76c2b83d08cfac71445b123a3e739ed0e2ce14be581df949e78efd88c603d7ed1efcc241ae6fc1e35be8dc2950d0aa5cab04b975aee46ad7195b22caaeb649bd5c44805d9f6f61ed37c607100b3e7c9c5e15503e1ea22902b4c88fe8a86aa947292f4641662bc0071abf05e58205e180e6ecf411d81023f5bd8b8c5f8bbc6978e817d02b05743a55676e755b8250a41fb75033eaa38faa52ce8111be3ed57cc76b2b30a26bb5e929824f9bc193905326ac5b5e2522f7e0a6a909a5e8b6ee68851aaa0618a714033491f9183e4491ba13425371d1ce19889ce35e544a1ccbde48c12cf96d1581fb585433fdd969708c886e813f9570aab33a5b7ffd5f67960e028313d4018c2f2a9b17196709f747a0e2be58cc3a5816141a927267c407364c2471e1be5975e9552814a9c8ffe7cbe899bc2866d0d4c0d42dc690d3ef8ed4a8e6da40924d635b1039ac13e5183a87eff119cf18d8a0e6ed16e0b701497e90a40dae5c6fb3e5e0d0859266f12ea4fd00b47d1d6949a645726939ec000a14bdd4ecbdb13d570d4b6c0684de658e033bf90a67709181f0156d947d0f7e018bbd39e1619ddc02b95f5a3d3c39da46357b0ef0614d1bc5c790f85ad38b550a1884e0405f86f44bab85a53e0bd178013bdb51f168a527f9bb48d3ebb3376220f6e4f37d241b4bdecd2466289fa5859905bcc71967aa1d37bb2deeb2d85844bd5e7982afd415f3c23f5322880d43ff06e050e080a56b4cc992f3d0988d4f3f42f97a1d66ba44cca04c6ce35e777830abb81b75f95a018cd55a908be0c4b269e74d48b52b159abc9e7ce5506c6dba8ef9690939357f9d0a2a145d81d6fbabcc08055f17c66ee1fb8d50e6110c08c345713df960f403a00e381c916c1ce685403b297cbc2ca41a9c6df6974ad5c83c62df45514ee8fd599870787274a0d0bb36d28301d7f8024613bf4555384f394e614926f45ccb6c22a0234f8cdf5748ed8b731098fc066cfef7e64ceb325563f13bff08e624ac9ede586483865a2646fa830a3138eba0e111d67bb368aa4f54e24fab4ed471788aad565e10e9ca9298c5d3bf08246a018aab4019e0a8c8106c918c8d512f7d76092932a8ad90d2a8c86b56ed83aba4da8466f9e99714decbad0913943fa8668e0f56320cee0cd05726b63f3e42a5bf2f06893e451583261ba8da1f84c8960d51d1eb3e5272e2cfa979dcfe5bd14c401ba336d2f4c6ebbe3699504f8062217cc5c98fd26fcfaf3cf2586ace22000a0fdf5d325f423ae2568a620a60c90892bd248dc9764d61eb41703ac5db28705153c657c32e82e1ed557a00bb6fad923d0d0510d34bc3afca068ded775ce60f5b055060550b5db6ae35423307de4e050533a76c4e6386c266f4bd3ccb4cb6d68aeff81db7db9b5910a3254aeda3b94ed9376a08f17009b1d7d6f879ab8fd87ea66030a2562921512a33e9e52494501ea5ae09816563ae5bb4027cbdd2dabd387a271f7b754a2111e81001bb16a564ba7d88a0adbd79c3c4945294a4400087d3331c70c9c8a46e8f28de41b9b7da52e62f30302ce749fd55b156eb4d360ebe304c6c2fb842f9aeaf9efd37b8110e79912bab200f984e1c7107fab432a7b7a3637105b5784797ec7ad19d0ff48dcd9a672e4f23a737729d2cfd9b6fce84554b2e245cbab25bd3a8b790fa7bbf66a9fd07feb883f78334b334377320517c37f0b72826bee092bd60d0b1a06c1054af2d02c012a09944a3319dbe4299f048a95ac8650dab22f830426f5b0aa638fc801d8634927e209c5955f4182b6835d24ac21e4542d4ac8fad053b43d6ff81f524402ad2c45c7b7b893e873c8a77986de1156cc5fc9059d5e2f82d7908632b02315493c09901708f3655bde3735711f5f4869f51a806a38d4f8c63f6a2e7fb4ab9e4ce1f91223c5debe7f7cac6a877e003274ed5fa7c72e74b49a9d4d75e75234147377c6fa8513be1290455c49132e9494f5e5c0943ac5ba01f62012702a15c729f96fc5a02f341402fd9caf854aaf7066a4263367d215a2fa9fe8b176d586d8b318c0be35e46ab443603c81d3de55d185ed25b33109798d7fab1f306e789dcf2541d2b18f5c9d1b608b13cff22a5a81b8294774592085f01ee56f39eaeadb685415999c057bba146fb9c325cb6f10b50a7452db0bd2bd76667cb67e75233d913a72517e1692cb0f987a0dc0328eab1a3373c7bf47d886d31d98acef2c13f9b96264d58594869ffd3d744220d2ff31982aa34d3a4387eec3cab3aeb76f8e35ee597c6ac44a34fb72ea89aaa1cb79fca3233b767e245011428491e601d68b30b33b9d4bdecca8d180a7545a386ffb0d6b3f5ccb163cdcf0701e278f7912f9900b95180ff44039344782b2f31274990be23223bb21b0093ebc87b5632b277097de6d9714397f3e50081f279add955e2b20f2119ef98e43c422ffab4fff45471de8e1dabca558f71516b07ca2f2ae10c498ca8673a0422bca9b06e60b331902c0551f6689e3e7753ab26b830f776044a8390e9bdfd41de70ca42d328e59b03f9aacade73100769e0ecc04265009167bebda381f028d5fd0162440de948933a091d67feea86b65b29493d36445ea014997e84e5c7b44bb6850b8e23728285931cb0bbc1c587f8ea432d82caf65083dd73355bc597142cff37652b119e14d2817b145fd88e8361cd70f0b625c742b323073e42fe332520cd68690e4d3e63ef5c40773ad1ea3a68bf52b923ebfba5a88ec2d8a7adb716d2dc72aa5a174564f3d000ece7e872a10db5d83dcd6a058ae377d1144934e6c9228625943e82642b5406022e4cebb534ae4f4b9e7b7fec27452ac9c05d95228805994f8725d1f06c78c5e90d81715bea5daffda07db449acaf87544a98c858fbc30634585a567607f2e86b1c7eb7643e3f700a59b57c134692481f478d8ff2a85c8df28e5aa1fb882b47a63cd3362952867dd6ea367374523a915dbd0bdee0e6b8dcb35306122294b55d8964c0336da299f4c788ad851cce701d6b8ea718ec95704c357d2f962e6a57f36674f2b9cced841cb6e6697606cbfd035dcf39c5363e441746b95c800483440f8d85f45ac1691f3f2767b7d733bf1442ee54c34bc7991ef4b322bffc96d5576eeb4d67343c3050f196578e06285aa8ff6f45d37232d99c2695d61cb484219fa42fa30c23c2b728c6eb09e1d4a7602101de39b92c1ecef4e6d84a7e46f2bdc2e8811fb2c5305df50a9a7a1e1b7ef75a2ae74f0c0597e93b4a9b00d7e0881181615b5af6a0053b2d6e168d0b45bc4350006daf66b85c3f796d2e50a8ad51513865a21aaec01817ce5705001d3b50054406fb529ea2ea65e0a4a7798afd0ea7c2631b786cab4a95c835a53cb804602d4b69f71c63f9fa06436fd2f91df46b2632c2a2a26aa1d367201164253b7c8ba22997b7492a622257592ae6f17a8ea28c7aa2a43dde80e450b62e9e43b9a126c597363e9142323850d176f2e59d7eb424570bb19794445d76b7fa5cb04f1fb86c3bfa9edfeaed2741f73daa467937543db502839393503357a693c97f9c1a51cdbc541b56bc1cd5812363d7b7a205291309740328606b86ecf095056e653bad1e45d5127b89f52cea7c717404a235af6b7ea3ba7ef48290c13cd43cf9d258785dc23603bdb44cca5501c9f556bee63d7041eae06e71937f01a14956b7f35c78af4a9a5821eea391918d429d69fa93e85406575908470919210ddbff326c54985a1fc95c86c2cf652a3d60915a2ea6436e805f1b9a036e937000a1aa4b1e6d1f5807b2bd83e199a7fa123ab925eac65cc1e7042269ac7ca7821c78b89e7f990a6477c25764aeba49a26373afaba78f1f504055c63f5aee1947d7b210ddbf060d192b854710f9f7b80da0f85950a633217bdbe1a4fd07210246b7fb075ca2db80be283d84e8de73ff7d2680f15286b3fbd02851b0a721ceaa30c096194861e1330bf9303f01aeed71291634d60600984324197d19f22771b931adb8ce8e299e735131f673a7af4ed13089d30f07919352022b39fd930ab01bcfc98e2b841259fa1e1b49ae17fe505e2736ab2bd577360ab13a91c36d539e4be846a6b071a2af551da8fa0062912d43b632de9f52b0d33dbff97eac9c0c9219a5325b9a93bfc9981f72ff58eca46e922f0ccf368eff603d8d999c23e28826f85aa7539951e93331d57358db207c5d7d3ad010e8a06ca0fc02ce76c1418cfcd4739a087d4eebd6579055f12569913964914467e6e6db292ba97aee1973728df671cae4b3535ad212f246eb5a7eeb42b3beb91a1d13bf1387ede0359bf47a36efd7a528ee4d6190a1211f87d9ba3299454d166a70e3fa0afa16ce5f42cba492c4d3e37e846ab31be25c704fa5a3a220b69ed70a6b4f149f3234ef0d6f27c7f151b2013e848a45fe7f1918f69a2102b2e72d95a23cf59a5265b0de522566e56c4f3cc30e419b9da1995673e8c1ab02d743ab717c00936f5a4737e5b8266a34a557fc996fbd12ba42cec9149612d074ad5779cd0c9f6874750ed86c27b1a405fda09c1527fbf6851e6172affcbe86a7e48282c98a5729495e46c916334121ee1b238dafb609607135e9385ac2540fae5fd8f56bb196dc5f37e1c8a55f91e5baae5a2d3218987c2a11e37b79aad5b4b4ea37f61a4b0b9c424a819596d1dcc9a91699717497fe0e6ada01446c7b9ce7d737693c0c532b213616df6eb99faa899c5707f728a10e1fd5d0ac7c6f91ee4b5129047e583cb20e205cae253ca9e681fa88efba30a89cc447878fcd65b9cd225c59a3ab08a23638df1645585a151445fa743f96744f8691184d6ffc3c9a144642a71ddd73867ba4f57f42309af2e443ce972687f47ece407988f42a2b573094a129d79281114f886b9c6730ac2386c972a2003f032b3228d5347c6d94a221bfb61d75074f3391d3ceda6a", 
    "pseudoOuts": [ "abc5ca05c1ffd8ae1176c6d43dde9078f162341d0c43b7c734f71b9ffe7682a5"]
  }
}
```
So far, it is possible to use the monero-inflation-checker Python library to scan all transactions in a block in real time as the main crypto operations are done via a Python binding to a standard C++ crypto library (LibSodium). The idea here is to keep about the same performance as FCMP++ but the main priority is to provide correct codes to reliably verify/generate the FCMP++ proofs.


## Tasks
### Task 1 (C++):
Implement C++ functions to add, double, multiply by scalar, check if on curve and all the necessary elliptic curve tools for Helios/Selene to be able to prove and verify a FCMP++ proof.

#### Deliverable:
- Non performant Python code using not optimized but accurate elliptic curve operations to make sure the Helios/Selene operations are accurate. I will start here to make sure that we have the same results since there is no standard available library for that.
- C++ tools to perform the task with a comparable performance as the RUST code
- Bindings to be used in Python for the sequence of the project
- Unittests for Rust, C++ and my non performant Python library with basic operations that will serve as ground-truth.


### Task 2 (Python):
Provide my own implementation for each functional block (GBP, arithmetic circuits, merkle tree proof generation/verification) in Python.

#### Deliverable:
- Intermediate implementations like GBP and arithmetic circuits.
- Improve and update the website moneroinflation.com
- Web page explaining the code, all the blocks and how they interact with each other. Both for beginner and advanced levels. Hopefully making FCMP++ more approachable and popular.
- The final goal is to provide a function to generate and verify a fcmp++ proof completely independent from the current Rust code.

When I finish this work, I believe I would give a satisfying answer to myself (and hopefully others) regarding the question why there is no inflation happening in Monero? As I would have checked the accuracy of all basic operations of the new curves (Helios/Selene), the basic functional blocks (GBP, arithmetic circuits and merkle tree) and my verifier would be validating proofs generated with the original code and the proofs generated with my code would be validated by the original verifier. If this is not achieved, then this project failed.

## Potential of this work
- Find bugs or strange things in the FCMP++ implementation (not likely)
- Provide an easy way to generate/verify FCMP++ proofs when it is live via an independent Python implementation
- Provide tools to be used for educational purposes or rapid prototyping of new ideas

## Who
- I created the website [www.moneroinflation.com](www.moneroinflation.com) where you can find some information about how monero works and tools to understand/explain why inflation is not happening in Monero.
- I have spotted a [fungibility issue](https://github.com/monero-project/monero/issues/8351) (Monero allows the storage of non-canonical points which harms the fungibility of transactions). 
- I have spotted a [malleability issue](https://github.com/monero-project/monero/issues/8438) (Monero has wrong signatures that don't match the data stored in the blockchain according to the canonical standards, which came from a wrong operation of a function when certain conditions are not met). 

Total: 26.25 XMR.
