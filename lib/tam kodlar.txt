import 'package:flutter/material.dart';

void main() => runApp(ModaApp());

class ModaApp extends StatefulWidget {
  @override
  _ModaAppState createState() => _ModaAppState();
}

class _ModaAppState extends State<ModaApp> {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: AnaSayfa(),
    );
  }
}

class AnaSayfa extends StatefulWidget {
  @override
  _AnaSayfaState createState() => _AnaSayfaState();
}

class _AnaSayfaState extends State<AnaSayfa>
    with SingleTickerProviderStateMixin {
  TabController tabController;

  @override
  void initState() {
    // TODO: implement initState
    super.initState();
    tabController = TabController(length: 5, vsync: this);
  }

  @override
  void dispose() {
    tabController.dispose();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        bottomNavigationBar: Theme(
            data: Theme.of(context).copyWith(canvasColor: Colors.redAccent),
            child: BottomNavigationBar(
              type: BottomNavigationBarType.fixed,
              fixedColor: Colors.white,
              items: <BottomNavigationBarItem>[
                BottomNavigationBarItem(
                  icon: Icon(Icons.home),
                  title: Text(
                    'Anasayfa',
                    style: TextStyle(fontWeight: FontWeight.bold, fontSize: 16),
                  ),
                ),
                BottomNavigationBarItem(
                  icon: Icon(Icons.wifi_tethering),
                  title: Text(
                    'Podcastler',
                    style: TextStyle(fontWeight: FontWeight.bold, fontSize: 16),
                  ),
                ),
                BottomNavigationBarItem(
                  icon: Icon(Icons.account_balance),
                  title: Text(
                    'Yayın Akışı',
                    style: TextStyle(fontWeight: FontWeight.bold, fontSize: 16),
                  ),
                ),
                BottomNavigationBarItem(
                  icon: Icon(Icons.message),
                  title: Text(
                    'Blog',
                    style: TextStyle(fontWeight: FontWeight.bold, fontSize: 16),
                  ),
                ),
                BottomNavigationBarItem(
                  icon: Icon(Icons.accessibility),
                  title: Text(
                    'Hakkımızda',
                    style: TextStyle(fontWeight: FontWeight.bold, fontSize: 13),
                  ),
                ),
              ],
            )),
        appBar: AppBar(
          leading: Icon(
            Icons.favorite,
            color: Colors.red,
          ),
          backgroundColor: Colors.transparent,
          title: Text("        Ana Sayfa  ",
              style: TextStyle(
                fontWeight: FontWeight.bold,
                color: Colors.black,
                fontSize: 30,
              )),
          elevation: 0,
          actions: <Widget>[
            IconButton(
              icon: Icon(
                Icons.adjust,
              ),
              onPressed: () {},
              color: Colors.black,
            ),
          ],
        ),
        body: SingleChildScrollView(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.start,
            children: <Widget>[
            //üst Taraftaki Profil Listesi
            Container(
            height: 400,
            width: 400,
            child: ListView(
              padding: EdgeInsets.all(10),
              scrollDirection: Axis.horizontal, //soldan saga kaydırır
              children: <Widget>[
                Image.network(
                    'https://i1.sndcdn.com/artworks-000489322419-mup5cg-t500x500.jpg'),
                Image.network(
                  'https://lh3.googleusercontent.com/-p_SDzvHMjV-jpryKhz85pTV7ILd2giqkTPf0gtU2a39vLQXN7PJ8PVIMmPhRLsc-D0',

                ),
                Image.network(
                  'https://i1.sndcdn.com/avatars-000117360904-hl531r-t500x500.jpg',
                  fit: BoxFit.cover,
                ),
              ],
            ),
          ),
          Row(children: <Widget>[
            SizedBox(
              width: 10,
            ),
            Icon(
              Icons.ac_unit,
            ),
            SizedBox(
              width: 5,
            ),
            Text(
              "Popüler Podcastler",
              style: TextStyle(
                fontSize: 15,
                fontWeight: FontWeight.bold,
              ),
            ),
            SizedBox(
              width: 180,
            ),
            Text(
              "Tümü",
              style: TextStyle(color: Colors.green, fontSize: 15),
            )
          ]),
          Divider(),

          //Material Cardın bir üst sınfıdır O yüzden Card yerine kullablirsin

          Container(
            height: 165,
            width: 800,
            child: ListView(
              padding: EdgeInsets.symmetric(horizontal: 10),
              scrollDirection: Axis.horizontal, //soldan saga kaydırır
              children: <Widget>[
                Stack(
                  children: <Widget>[
                    Positioned(
                      child: Container(
                        decoration: BoxDecoration(
                          color: Colors.pink,
                          borderRadius: BorderRadius.circular(10.0),
                        ),
                        constraints:

                        /// Containerin içindeki widget container in boyutundan küçük ise container kenarlarda veya altta boşluk bırakır
                        BoxConstraints(maxWidth: 220, maxHeight: 165),
                      ),
                    ),
                    Positioned(
                      left: 15,
                      top: 15,
                      child: Text(
                        "EKO ANALİZ - Para\n politikası Türkiye\n ekonomisi için bir\nçıkış olablirmi\n 2020  ",
                        style: TextStyle(
                            color: Colors.white,
                            fontWeight: FontWeight.bold,
                            fontSize: 23),
                      ),
                    ),
                  ],
                ),
                SizedBox(
                  width: 10,
                ),
                Stack(
                  children: <Widget>[
                    Positioned(
                        child: Container(
                          decoration: BoxDecoration(
                            color: Colors.pink.shade900,
                            borderRadius: BorderRadius.circular(10.0),
                          ),
                          constraints:
                          BoxConstraints(maxWidth: 220, maxHeight: 160),
                        )),
                    Positioned(
                      left: 15,
                      top: 15,
                      child: Text(
                        "Hakan Milli ile\n Harikalar\n Diyarında \nGökten ekler\n 2020  ",
                        style: TextStyle(
                            color: Colors.white,
                            fontWeight: FontWeight.bold,
                            fontSize: 23),
                      ),
                    ),
                  ],
                ),
                SizedBox(
                  width: 10,
                ),
                Stack(
                  children: <Widget>[
                    Positioned(
                        child: Container(
                          decoration: BoxDecoration(
                            color: Colors.blue.shade900,
                            borderRadius: BorderRadius.circular(10.0),
                          ),
                          constraints:
                          BoxConstraints(maxWidth: 180, maxHeight: 160),
                        )),
                    Positioned(
                      left: 15,
                      top: 15,
                      child: Text(
                        "Dünyayı Bir\n Bilene Sor/\nGüney Afrika \n 2020",
                        style: TextStyle(
                            color: Colors.white,
                            fontWeight: FontWeight.bold,
                            fontSize: 23),
                      ),
                    ),
                  ],
                ),
                SizedBox(
                  width: 10,
                ),
                Stack(
                  children: <Widget>[
                    Positioned(
                        child: Container(
                          decoration: BoxDecoration(
                            color: Colors.green.shade900,
                            borderRadius: BorderRadius.circular(10.0),
                          ),
                          constraints:
                          BoxConstraints(maxWidth: 220, maxHeight: 160),
                        )),
                    Positioned(
                      left: 15,
                      top: 15,
                      child: Text(
                        "Gülay Günlerle\n Finans/\n Cumhuriyet \nBayramı özel\n 2020  ",
                        style: TextStyle(
                            color: Colors.white,
                            fontWeight: FontWeight.bold,
                            fontSize: 23),
                      ),
                    ),
                  ],
                ),
              ],
            ),
          ),
          Row(
            children: <Widget>[
              Icon(
                Icons.account_circle,
              ),
              SizedBox(
                width: 5,
              ),
              Text(
                "Programcılar ",
                style: TextStyle(
                  fontSize: 15,
                  fontWeight: FontWeight.bold,
                ),
              ),
              SizedBox(
                width: 180,
              ),
              Text(
                "Tümü",
                style: TextStyle(color: Colors.green, fontSize: 15),
              )
            ],
          ),
          Divider(),
          Container(
            height: 500,
            width: double.infinity,
            child: ListView(
                padding: EdgeInsets.only(top: 10),
                children: <Widget>[
                  Container(
                    height: 140,
                    width: double.infinity,
                    child: ListView(
                        padding: EdgeInsets.all(10),
                        scrollDirection: Axis.horizontal, //soldan saga kaydırır
                        children: <Widget>[
/*iki yöntem var yuvarlamak iççin clip oval veya cliprrect
                    yada CircleAvatar var*/


                          /// hadi görüşürüz

                          Column(
                            mainAxisAlignment: MainAxisAlignment.end,
                            children: <Widget>[

                              CircleAvatar(

                                  radius: 50,
                                  backgroundImage: NetworkImage(
                                      'https://radyogedik.com.tr/wp-content/uploads/2019/03/ahuParlar.jpg')),
                              Text("AHU PARLAR",
                                style: TextStyle(color: Colors.black),)
                            ],
                          ),
                          SizedBox(
                            width: 5,
                          ),

                          SizedBox(
                            width: 5,
                          ),
                          Column(
                            mainAxisAlignment: MainAxisAlignment.end,
                            children: <Widget>[

                              CircleAvatar(

                                  radius: 50,
                                  backgroundImage: NetworkImage(
                                      'https://radyogedik.com.tr/wp-content/uploads/2019/02/ahmetAmanvermez-2.jpg')),
                              Text("AHMET AMANVERMEZ",
                                style: TextStyle(color: Colors.black),)
                            ],
                          ),
                          SizedBox(
                            width: 5,
                          ),
                          Column(
                            mainAxisAlignment: MainAxisAlignment.end,
                            children: <Widget>[

                              CircleAvatar(

                                  radius: 50,
                                  backgroundImage: NetworkImage(
                                      'https://radyogedik.com.tr/wp-content/uploads/2019/10/berrinYigit.jpg')),
                              Text("BERRİN YİGİT",
                                style: TextStyle(color: Colors.black),)
                            ],
                          ),
                          SizedBox(
                            width: 10,
                          ),
                          Column(
                            mainAxisAlignment: MainAxisAlignment.end,
                            children: <Widget>[

                              CircleAvatar(

                                  radius: 50,
                                  backgroundImage: NetworkImage(
                                      'https://radyogedik.com.tr/wp-content/uploads/2019/02/boraErdin.jpg')),
                              Text("BORA ERDİN ",
                                style: TextStyle(color: Colors.black),)
                            ],
                          ),
                          SizedBox(
                            width: 15,
                          ),
                          Column(
                            mainAxisAlignment: MainAxisAlignment.end,
                            children: <Widget>[

                              CircleAvatar(

                                  radius: 50,
                                  backgroundImage: NetworkImage(
                                      'https://radyogedik.com.tr/wp-content/uploads/2019/02/canerAkgun-300x169.jpg')),
                              Text("CANER AKGÜN ",
                                style: TextStyle(color: Colors.black),)
                            ],
                          ),
                          SizedBox(
                            width: 15,
                          ),
                          Column(
                            mainAxisAlignment: MainAxisAlignment.end,
                            children: <Widget>[

                              CircleAvatar(

                                  radius: 50,
                                  backgroundImage: NetworkImage(
                                      'https://radyogedik.com.tr/wp-content/uploads/2019/03/DDD-300x169.jpg')),
                              Text("CEM ÇOLAKOGLU",
                                style: TextStyle(color: Colors.black),)
                            ],
                          ),
                          SizedBox(
                            width: 15,
                          ),
                          Column(
                            mainAxisAlignment: MainAxisAlignment.end,
                            children: <Widget>[

                              CircleAvatar(

                                  radius: 50,
                                  backgroundImage: NetworkImage(
                                      'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcS7SeyTIA0ElLdx9a-SiBfIdnUiAqmV9jZVrQ&usqp=CAU')),
                              Text("DENİZ KARADENİZ",
                                style: TextStyle(color: Colors.black),)
                            ],
                          ),
                          SizedBox(
                            width: 15,
                          ),
                          Column(
                            mainAxisAlignment: MainAxisAlignment.end,
                            children: <Widget>[

                              CircleAvatar(

                                  radius: 50,
                                  backgroundImage: NetworkImage(
                                      'https://radyogedik.com.tr/wp-content/uploads/2020/09/enginVerel-300x169.jpg')),
                              Text("ENGİN VEREL ",
                                style: TextStyle(color: Colors.black),)
                            ],
                          ),
                        ]),
                  ),
                  Row(
                    children: <Widget>[
                      Icon(
                        Icons.account_circle,
                      ),
                      SizedBox(
                        width: 5,
                      ),
                      Text(
                        "Son Podcastler ",
                        style: TextStyle(
                          fontSize: 15,
                          fontWeight: FontWeight.bold,
                        ),
                      ),
                      SizedBox(
                        width: 180,
                      ),
                      Text(
                        "Tümü",
                        style: TextStyle(color: Colors.green, fontSize: 15),
                      )
                    ],
                  ),

                  SizedBox(height: 20,),
                  Column(
                      children: <Widget>[

                        Row(
                            mainAxisAlignment: MainAxisAlignment.start,
                            children: <Widget>[
                              Icon(Icons.favorite,color: Colors.grey,size: 30,
                              ),
                              SizedBox(width: 20,),
                              Row(
                                mainAxisAlignment: MainAxisAlignment.center,
                                children: <Widget>[

                                  Text("FUTBOL AKADEMİSİ", style: TextStyle(
                                      fontWeight: FontWeight.bold,
                                      color: Colors.black,
                                      fontSize: 30),
                                  ),
                                  SizedBox(width: 30,),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.end,
                                    children: <Widget>[
                                      Icon(Icons.share,color: Colors.black,size: 30,
                                      ),
                                    ],
                                  ),
                                  SizedBox(height: 20,),


                                ],
                              ),
                            ]
                        ),
                        SizedBox(height: 30,),
                        Row(
                            mainAxisAlignment: MainAxisAlignment.start,
                            children: <Widget>[
                              Icon(Icons.favorite,color: Colors.grey,size: 30
                              ),
                              SizedBox(width: 30,),
                              Row(
                                mainAxisAlignment: MainAxisAlignment.center,
                                children: <Widget>[

                                  Text("EKO ANALİZ-Para\npolitikası Türk\n ekonomosine yarar mı", style: TextStyle(
                                      fontWeight: FontWeight.bold,
                                      color: Colors.black,
                                      fontSize: 25),
                                  ),
                                  SizedBox(height: 16,),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.end,
                                    children: <Widget>[
                                      SizedBox(width: 40,),
                                      Icon(Icons.share,color: Colors.black,size: 30,
                                      ),
                                    ],
                                  ),
                                  SizedBox(height: 20,),


                                ],
                              ),
                            ]
                        ),
                        SizedBox(height: 30,),
                        Row(
                            mainAxisAlignment: MainAxisAlignment.start,
                            children: <Widget>[
                              Icon(Icons.favorite,color: Colors.grey,size: 30
                              ),
                              SizedBox(width: 20,),
                              Row(
                                mainAxisAlignment: MainAxisAlignment.center,
                                children: <Widget>[

                                  Text("HAKAN MİLLİ İLE\n HARİKALAR DİYARINDA-\nGÖKTEN EKLER", style: TextStyle(
                                      fontWeight: FontWeight.bold,
                                      color: Colors.black,
                                      fontSize: 25),
                                  ),
                                  SizedBox(width: 25,),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.end,
                                    children: <Widget>[
                                      Icon(Icons.share,color: Colors.black,size: 30,
                                      ),
                                    ],
                                  ),
                                  SizedBox(height: 20,),


                                ],
                              ),
                            ]
                        ),

                      ])
                ]))],
          ),
        ),
    ) ;
  }
}
