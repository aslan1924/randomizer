<html> 
<head>
<title>Генерация случайных чисел</title>
<script language="JavaScript"> 
<!-- //
function randnumbers(object)
{
var x = 1;
var y = object.b.value;
var n = object.m.value;
 
var k = 0;
var str = "";
 
while (k < n)
{
  // 1-ый вариант генерации случайного числа:
  var number = Math.floor(x + (y-x+1)*Math.random());
  
  //2-ой вариант генерации случайного числа:
//var c = y - x;
//var number = Math.floor(Math.random()*c) + x;
  
  str += number;
  if (k < n-1) str += " ; "
  else         str += " . ";
  k++; 
}
alert(str);
}
//--> 
</script> 
</head> 
<body bgcolor="#CCFFCC">
    <form name="f1" style="margin: 5px; text-align: left; font-size: 20px">
    <h3>Программа генерации n случайных чисел из заданного отрезка</h3>
     
            Сколько участников? <input type="text" name="b" size="10" style="margin: 5px 0 0 37px; font-size: 17px"><br>
            Сколько победителей? <input type="text" name="m" size="10" style="margin: 5px; font-size: 17px"><br>
            <input type="button" value="Показать" style="margin: 5px 0 0 319px; font-size: 17px" onClick="randnumbers(f1)"> <br>
       <input type="button" value="Пока" style="margin: 5px 0 0 319px; font-size: 17px" onClick="randnumbers(f1)"> <br>
        <input type="button" value="зать" style="margin: 5px 0 0 319px; font-size: 17px" onClick="randnumbers(f1)"> <br>
            <input type="reset" value="Сбросить" style="margin: 5px 0 0 319px; font-size: 17px">            
    </form>
</body> 
</html>
