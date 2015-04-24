# project-pideban
A code for "Christmas" edition of school restaurant "Pideban"
<!doctype html>
<html>
<head>
             <meta charset="UTF-8">
            <title>ProjectPIDEBAN</title>    

            <script type="text/javascript">


  
  //Configure below to change URL path to the snow image
  var snowsrc="snow.gif"
  // Configure below to change number of snow to render
  var no = 10;
  // Configure whether snow should disappear after x seconds (0=never):
  var hidesnowtime = 0;
  // Configure how much snow should drop down before fading ("windowheight" or "pageheight")
  var snowdistance = "pageheight";

///////////Stop Config//////////////////////////////////

  var ie4up = (document.all) ? 1 : 0;
  var ns6up = (document.getElementById&&!document.all) ? 1 : 0;

  function iecompattest(){
  return (document.compatMode && document.compatMode!="BackCompat")? document.documentElement : document.body
  }

  var dx, xp, yp;    // coordinate and position variables
  var am, stx, sty;  // amplitude and step variables
  var i, doc_width = 800, doc_height = 600; 
  
  if (ns6up) {
    doc_width = self.innerWidth;
    doc_height = self.innerHeight;
  } else if (ie4up) {
    doc_width = iecompattest().clientWidth;
    doc_height = iecompattest().clientHeight;
  }

  dx = new Array();
  xp = new Array();
  yp = new Array();
  am = new Array();
  stx = new Array();
  sty = new Array();
  snowsrc=(snowsrc.indexOf("dynamicdrive.com")!=-1)? "snow.gif" : snowsrc
  for (i = 0; i < no; ++ i) {  
    dx[i] = 0;                        // set coordinate variables
    xp[i] = Math.random()*(doc_width-50);  // set position variables
    yp[i] = Math.random()*doc_height;
    am[i] = Math.random()*20;         // set amplitude variables
    stx[i] = 0.02 + Math.random()/10; // set step variables
    sty[i] = 0.7 + Math.random();     // set step variables
    if (ie4up||ns6up) {
      if (i == 0) {
        document.write("<div id=\"dot"+ i +"\" style=\"POSITION: absolute; Z-INDEX: "+ i +"; VISIBILITY: visible; TOP: 15px; LEFT: 15px;\"><a href=\"http://dynamicdrive.com\"><img src='"+snowsrc+"' border=\"0\"><\/a><\/div>");
      } else {
        document.write("<div id=\"dot"+ i +"\" style=\"POSITION: absolute; Z-INDEX: "+ i +"; VISIBILITY: visible; TOP: 15px; LEFT: 15px;\"><img src='"+snowsrc+"' border=\"0\"><\/div>");
      }
    }
  }

  function snowIE_NS6() {  // IE and NS6 main animation function
    doc_width = ns6up?window.innerWidth-10 : iecompattest().clientWidth-10;
    doc_height=(window.innerHeight && snowdistance=="windowheight")? window.innerHeight : (ie4up && snowdistance=="windowheight")?  iecompattest().clientHeight : (ie4up && !window.opera && snowdistance=="pageheight")? iecompattest().scrollHeight : iecompattest().offsetHeight;
    for (i = 0; i < no; ++ i) {  // iterate for every dot
      yp[i] += sty[i];
      if (yp[i] > doc_height-50) {
        xp[i] = Math.random()*(doc_width-am[i]-30);
        yp[i] = 0;
        stx[i] = 0.02 + Math.random()/10;
        sty[i] = 0.7 + Math.random();
      }
      dx[i] += stx[i];
      document.getElementById("dot"+i).style.top=yp[i]+"px";
      document.getElementById("dot"+i).style.left=xp[i] + am[i]*Math.sin(dx[i])+"px";  
    }
    snowtimer=setTimeout("snowIE_NS6()", 10);
  }

  function hidesnow(){
    if (window.snowtimer) clearTimeout(snowtimer)
    for (i=0; i<no; i++) document.getElementById("dot"+i).style.visibility="hidden"
  }
    

if (ie4up||ns6up){
    snowIE_NS6();
    if (hidesnowtime>0)
    setTimeout("hidesnow()", hidesnowtime*1000)
    }

</script>

          <style>
          .ass
          {
            
            padding: 10px;
            background-color: green;
            font-family: Verdana;
            border: 10px;
            border-style: solid;
            border-color: black;
          }
          h1.b
          {
            padding: 15px;
            background-color: mintcream;
            font-family: Arial;
            border: 10px;
            border-style: solid;
            border-color: black;
          }
          img.logo
          {
            width: 300px;
            height: auto;
            border: 5px;
            padding: 10px;
            border: 10px;
            border-style: solid;
            border-color: midnightblue;
            background-color: white;
          }
          
          iframe:focus{
            outline: none;
          }
          iframe[seamless]
          {
            display: block;
          }
          </style>


          <script>
          function order()
          {
            var mesaj = "";
            var radios = document.getElementsByName("pide");
            var found = 1;
            for (var i = 0; i < radios.length; i++) 
            {       
              if (radios[i].checked) 
              {
                  mesaj += "Pide tipi : " + radios[i].value + "\n";
                  //alert(radios[i].value);
                  found = 0;
                  break;
              }
            }
             if(found == 1)            {
                mesaj += "Lütfen pide tipini seçin." + "\n";
                //alert("Lütfen pide tipini seçin.");
             }

             var radios = document.getElementsByName("soganlik");
            var found = 1;
            for (var i = 0; i < radios.length; i++) 
            {       
              if (radios[i].checked) 
              {
                  mesaj += "Soganli mi ? : " + radios[i].value + "\n";
                  //alert(radios[i].value);
                  found = 0;
                  break;
              }
            }
             if(found == 1)
             {
                mesaj += "Lütfen soganlı/sogansız seçiniz." + "\n";
               //alert("Lütfen soganlı/sogansız seçiniz.");
             }    


             var radios = document.getElementsByName("boy");
            var found = 1;
            for (var i = 0; i < radios.length; i++) 
            {       
              if (radios[i].checked) 
              {
                  mesaj += "Boyutu : " + radios[i].value + "\n";
                  //alert(radios[i].value);
                  found = 0;
                  break;
              }
            }
             if(found == 1)
             {
                mesaj += "Lütfen boyu seçiniz." + "\n";
                //alert("Lütfen boyu seçiniz.");
             }    

             alert(mesaj);

          }
          </script>
</head>

<body bgcolor="red">
          <center><h1 class="ass">Christmas 2014</h1></center>
          <center><h1 class="b">Koç University Life</h1></center>
          <center><img src="kooc.jpg" class="logo"></img></center>
          <center><h1 class="ass"><a href="#resim">Work hard, play hard</a></h1></center>

            <center><audio controls loop src="abc.mp3" autoplay id="myses">
          <p>If you are reading this, it is because your browser does not support the audio element.     </p>
          <embed src="abc.mp3" width="180" height="90" hidden="true" />
          </audio> </center>

          <center><object width="420" height="315"
data="http://www.youtube.com/watch?v=LDZX4ooRsWs">
</object></center>
            <p>
            <q>Pide Sever Kardesler</q>

          </p>
<h1<strong>Merhaba Pidebanners</strong></h1>
<h2>Pide yiyelim mutlu olalim</h2>
<h3>Sariyer'in incisi</h3>    



           <ul>
                
                   <li><a href ="http://www.pideban.com.tr/"> Anasayfa</a></li>
                   <a href="http://www.pideban.com.tr/hakkimizda.asp"><li> Biz kimiz? </li></a>
                   <li> Cok da onemli degil</li>
                   <details> Tatava yapma, pide ban</details>

           </ul>

              <ol>
              <img src="http://www.rehberalem.com/firmalar/40957/urun/pide.jpg" id="resim" class="resim"></img>
 
                    <li>Sarıyer</li>
                    <li>Koc Universitesi</li>
                    <li>Etiler</li>
               </ol>
<p> Sizin icin 7/24 acigiz</p>
<br>  Maalesef <sup>Omerde</sup> kapaliyiz! </br> 
            </div>                

            <table bgcolor= "mintcream" border=”1”>
              
                               <tr>
                                        <th>cesit-secenek</th>
                                         <th>sogan-secenek</th>
                                          <th>boy-secenek</th>
                              
                              <tr>
                                       <td><input type="radio" name="pide" value="kasarli">Kaşarlı<input type="radio" name="pide" value="kiymali">Kıymali<input type="radio" name="pide" value="karisik">Karışık</td>
                                        <td><input type="radio" name="soganlik" value="soganli">Soganli<input type="radio" name="soganlik" value="sogansiz">Sogansiz  </td>
                                        <td><input type="radio" name="boy" value="kucuk">Kucuk<input type="radio" name="boy" value="orta">Orta<input type="radio" name="boy" value="buyuk">Buyuk </td>
                               
                               </tr> </table>

                               <input type="button" name="siparisver" value="Sipariş Ver" onClick="order()">

                               <form action="action_page.php">
<fieldset>


<legend>Kisisel Bilgiler</legend>
Adınız:<br>
<input type="text" name="adınız" value="">
<br>
Soyadınız:<br>
<input type="text" name="soyadınız" value="">
<br><br>
<input type="submit" value="Submit"></fieldset>
</form>

                  <p>
<br>Berkeren Büyükeren/PideBanners</br><br>Zafer Çavdar/PideBanners</br></address>
                 <small>Koc University</small>
                  </p> 
                  <p>
                 <time>December 2014</time>
                  </p>
</body> 

