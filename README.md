jQuery().ready(function () {
 function getRandomInt(min, max) { // Функция для получения случайного целого числа в заданном промежутке
 return Math.floor(Math.random() * (max - min + 1)) + min;
 }
 function getpwd(symb, len) { // Функция для генерации пароля. symb - строка символов для генерации, len - длина пароля
 var pwd = '';
 for (var i = 0; i < len; i++) {
 pwd = pwd + symb[getRandomInt(0, (symb.length - 1))];
 }
 return pwd;
 }
 function escapeHtml(text) { //Функция для экранирования спецсимволов
 return text
 .replace(/&/g, "&")
 .replace(//g, ">")
 .replace(/"/g, """)
 .replace(/'/g, "'");
 }
 var chars = ["abcdefghijklmnopqrstuvwxyz", "ABCDEFGHIJKLMNOPQRSTUVWXYZ", "0123456789", "!@#$%^&*()_-<>,.[]{};:№?"]; //Коллекция символов
 jQuery("#generate").click(function () { //Генерация паролей ко плику
 if (jQuery("input.innerVars:checked").length > 0 && jQuery("#countpwd").val() > 0 && jQuery("#countsymb").val() > 0) {
 var genspwd = '', symb = '', obj = jQuery("input.innerVars:checked");
 for (var j = 0; j < obj.length; j++) {
 symb = symb + chars[obj[j].value];
 }
 for (var j = 0; j < (jQuery("#countpwd").val()); j++) {
 genspwd = genspwd + '
' + escapeHtml(getpwd(symb, parseFloat(jQuery("#countsymb").val()))) + '

';
 }

 jQuery("#result").html(genspwd);
 } else {
 jQuery("#result").html('
Выберите значения для генерации пароля

');
 }
 })
 })



<input type="checkbox" value="0" id="chars" class="innerVars"><span>Строчные латинские буквы</span>

<input type="checkbox" value="1" id="bigChars" class="innerVars"><span>Заглавные латинские буквы</span>

<input type="checkbox" value="2" id="numChars" class="innerVars">Цифры (0-9)

<input type="checkbox" value="3" id="specChars" class="innerVars"><span>Спец символы (!@#$%^&amp;*()_-&lt;&gt;,.[]{};:№?)</span>

<input type="text" id="countsymb"><span>Количество символов</span>

<input type="text" id="countpwd"><span>Количество паролей</span>

<input type="button" id="generate" value="Сгенерировать">
