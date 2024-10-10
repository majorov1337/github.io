
# Обходим блокировОчку

Самое главное - покупаем зарубежный сервер. Где? Я покупаю на ishosting

Список подходящих [хостингов](https://poiskvps.ru/index.php?search_country%5B%5D=29&search_country%5B%5D=55&search_country%5B%5D=70&search_country%5B%5D=73&search_country%5B%5D=53&search_country%5B%5D=72&search_country%5B%5D=39&search_country%5B%5D=87&search_country%5B%5D=58&search_country%5B%5D=1&search_country%5B%5D=18&search_country%5B%5D=78&search_country%5B%5D=2&search_country%5B%5D=32&search_country%5B%5D=74&search_country%5B%5D=65&search_country%5B%5D=63&search_country%5B%5D=51&search_country%5B%5D=44&search_country%5B%5D=88&search_country%5B%5D=64&search_country%5B%5D=86&search_country%5B%5D=56&search_country%5B%5D=4&search_country%5B%5D=36&search_country%5B%5D=5&search_country%5B%5D=50&search_country%5B%5D=76&search_country%5B%5D=71&search_country%5B%5D=93&search_country%5B%5D=35&search_country%5B%5D=43&search_country%5B%5D=57&search_country%5B%5D=79&search_country%5B%5D=91&search_country%5B%5D=85&search_country%5B%5D=62&search_country%5B%5D=47&search_country%5B%5D=80&search_country%5B%5D=7&search_country%5B%5D=54&search_country%5B%5D=66&search_country%5B%5D=68&search_country%5B%5D=8&search_country%5B%5D=67&search_country%5B%5D=81&search_country%5B%5D=17&search_country%5B%5D=90&search_country%5B%5D=69&search_country%5B%5D=37&search_country%5B%5D=42&search_country%5B%5D=89&search_country%5B%5D=10&search_country%5B%5D=82&search_country%5B%5D=60&search_country%5B%5D=48&search_country%5B%5D=12&search_country%5B%5D=92&search_country%5B%5D=13&search_country%5B%5D=75&search_country%5B%5D=14&search_country%5B%5D=15&search_country%5B%5D=77&search_country%5B%5D=16&search_country%5B%5D=61&search_country%5B%5D=59&search_country%5B%5D=40&search_os%5B%5D=1&search_payment_method%5B%5D=2&search_payment_method%5B%5D=5&search_payment_method%5B%5D=9&search_traffic_min=2)

Копипаста с Хабра

**"Критерии выбора VPS:**

1. **1 процессор, минимум 1 GB оперативной памяти, минимум 5 GB диск.**
    
2. **Трафик: безлимитный или очень большой (например, 32 ТБ в месяц). Многим хватает 3 ТБ, но безлимитные варианты лучше.**
    
3. **Ширина канала: 100 Мбит (можно рассмотреть 1 Гбит).**
    
4. **Статичный IPv4 (сервер с IPv6, но без IPv4 не подходит).**
    
5. **Локация: Европа.**
    
6. **Поддержка установки Debian 12. Все шаги инструкции гарантированно работают на Debian 12.**
    
7. **Бекап не обязателен.**
    
8. **Рыночная цена: $5 / 500 ₽ в месяц, но можно найти дешевле (например, $0.99)."**
    

**Купили мы сервер, что дальше?**

На компуктере открываем командную строку через

```
Win+r 
```

```
cmd
```

```
ssh root@123.123.123.123
```

Вместо 123.123.123.123 - айпи нашего купленного сервера

![](HTML%20import/Attachments/image(3).png)

Вписываем yes

Вводим(копируем пароль и вставляем через ПКМ) пароль Мы на сервере. Объяснять как все обезопасить анально не буду, объяснено, например. вот тут - [https://www.youtube.com/watch?v=SaVi8Mw4Ci8](https://www.youtube.com/watch?v=SaVi8Mw4Ci8)

Вписываем

```
apt update && apt full-upgrade -y
```

Ждем, пока обновится и то се.

Как только обновилось - релоадаем

```
reboot
```

И снова подключаемся через минуту-полторы.

После того как подключились копируем и вставляем в консоль/терминал/цмд/как угодно

```
apt install docker.io docker-compose git curl bash openssl nano -y
```

```
git clone https://github.com/alireza0/x-ui.git
cd x-ui
docker-compose up -d
openssl req -x509 -newkey rsa:4096 -nodes -sha256 -keyout private.key -out public.key -days 3650 -subj "/CN=APP"
docker cp private.key x-ui:private.key
docker cp public.key x-ui:public.key
```

**ВНИМАНИЕ!!! Дальше я буду использовать IP_SERV как пример вашего айпи сервера, пожалуйста, учтите это.**

Дальше открываем наш браузер и вписываем http://IP_SERV:54321

Логин и пароль- admin

![](HTML%20import/Attachments/image(4).png)

Логинимся

Идем в http://IP_SERV:54321/xui/settings

![](HTML%20import/Attachments/image(5).png)

**- Panel Certificate** **Public** Key Path :

```
/public.key
```

**- Panel Certificate** **Private** Key Path :

```
/private.key
```

Жмакаем Save -> Restart Panel

![](HTML%20import/Attachments/image(6).png)

Заходим по http://IP_SERV:PORT/URI_Path/xui/settings -> Authentication и создаем нового юзера

![](HTML%20import/Attachments/image(7).png)

Нажимаем конфирм и заходим уже под новым юзером

**ОБЗАТЕЛЬНО!! сохраните где-нибудь URL доступа к панели, логин и пароль**.

Дальше переходим в http://IP_SERV:PORT/URI_Path/xui/xray и врубаем **Routes traffic to Google via IPv4**

![](HTML%20import/Attachments/image(8).png)

Наконец идем в http://IP_SERV:PORT/URI_Path/xui/inbounds

Жмакаем **Add inbound**

**Remark** - похуй что писать -> **Protocol** - vless -> **Listen IP** - Айпи нашего сервера/можно оставить пустыстым -> **Port** - 443 Client -> **Email** -> похуй, рандом(или YA_PC) ![](./Варим%20борщ%20правильно%20_%20how-to-varit-borsch_files/image(9))

![](HTML%20import/Attachments/image(10).png)

**Transmission** - TCP -> **Security** - REALITY -> **uTLS** - chrome -> **Dest** - google.com:443 -> **SNI** - google.com,www.google.com -> Get New Cert -> Create

![](HTML%20import/Attachments/image(11).png)

Когда мы генерили Email/вводили свое название - мы создавали клиента

Раскрываем "клиентов"

![](HTML%20import/Attachments/image(12).png)

Жмакаем Edit Client

![](HTML%20import/Attachments/image(13).png)

Flow - **xtls-rprx-vision ->** жмакаем **Save Changes**

![](HTML%20import/Attachments/image(14).png)

1 **клиент - 1 устройство**

То есть если мы хотим не только с ПК сидеть, а еще и с телефона и маму и тетю и дядю и прочее и прочее - на каждое устройство свой "клиент"

Чтобы не запутаться в клиентах - в поле **Email** при добавлении клиента как-то обозначайте эти устройства

![](HTML%20import/Attachments/image(15).png)

**Например у меня это выглядит так**

![](HTML%20import/Attachments/image(16).png)

**ВИДЕВАГАЙД**

[https://kinescope.io/i3jmygrazoaXR8hxCvs8zo](https://kinescope.io/i3jmygrazoaXR8hxCvs8zo) видева там

в видео забыл врубить **Routes traffic to Google via IPv4** ...

Соре, 4 утра

![](HTML%20import/Attachments/image(17).png)

Ну так вот, мы добавили клиента, че дальше делать?

Для ПК - [**Nekoray**](https://github.com/MatsuriDayo/nekoray/releases/download/4.0-beta3/nekoray-4.0-beta3-2024-07-13-windows64.zip)

Для [Android](https://github.com/MatsuriDayo/NekoBoxForAndroid/releases/tag/1.2.9)

Для [IOS](https://apps.apple.com/us/app/streisand/id6450534064?platform=iphone)

Создали клиента в панели-> копируем ключ Либо через QR-код ![](HTML%20import/Attachments/image(18).png) Либо через More information ![](HTML%20import/Attachments/image(19).png)

## 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#nastroika-dlya-pk)

**Настройка для ПК**

Копируем ключ -> пкм по окну софта и "Добавить профиль из буфера обмена" ![](HTML%20import/Attachments/image(20).png)

Дальше тыкаем на Режим системного прокси и Режим TUN ![](./Варим%20борщ%20правильно%20_%20how-to-varit-borsch_files/image(21))

Идем проверять наш айпи https://2ip.ru/ Если все сменено - все, чиллим

## 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#nastroika-na-ios)

**Настройка на IOS**

**(я точно не уверен, не богатый)**

Заходим в Streisand и импортируем конфигурацию или как-то так это называется ![](HTML%20import/Attachments/image(22).png)

## 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#nastroika-dlya-android)

**Настройка для Android**

Копируем ключ -> ![](HTML%20import/Attachments/image(23).png) ![](HTML%20import/Attachments/image(24).png)

ЖМЕМ на наш профиль и летим ![](HTML%20import/Attachments/image(25).png)

## 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#kak-nastroit-tolko-dlya-diskorda-i-yutuba)

**Как настроить ТОЛЬКО для дискорда и ютуба?**

![](HTML%20import/Attachments/image(26).png)

![](HTML%20import/Attachments/image(27).png)

![](HTML%20import/Attachments/image(28).png)

![](HTML%20import/Attachments/image(29).png)

Домены, которые вписывать

```
domain:nhacmp3youtube.com
domain:ytimg.com
domain:studio.youtube.com
domain:youtube.com
domain:googlevideo.com
domain:youtu.be
domain:googleusercontent.com
domain:gvt1.com
domain:video.google.com
domain:video.l.google.com
domain:youtubeembeddedplayer.googleapis.com
domain:youtube.googleapis.com
domain:youtubei.googleapis.com
domain:youtube-nocookie.com
domain:youtube-ui.l.google.com
domain:ggpht.com
domain:yt.be
domain:ytimg.l.google.com
domain:ytkids.app.goo.gl
domain:yt-video-upload.l.google.com
domain:withyoutube.com
domain:wide-youtube.l.google.com
```

Настройка туннелирования на андроид клиенте

(был бы у меня айфон-был бы и для него гуиде, но сори)

## 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#a-kak-zapustit-a-kak-otklyuchit-a-kak-dobavit-v-avtozagruzku)

А как запустить? А как отключить? А как добавить в автозагрузку?

### 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#avtozapusk-s-vklyuchennym-maionezom)

Автозапуск с включенным прокси

![](HTML%20import/Attachments/image(30).png)

## 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#kak-otklyuchit)

Как отключить?

Убрать галочки с режимов

![](./Варим%20борщ%20правильно%20_%20how-to-varit-borsch_files/image(31))

### 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#kak-vklyuchit)

Как включить?

![](HTML%20import/Attachments/image(32).png)

![](HTML%20import/Attachments/image(33).png)

## 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#khotim-glubzhe)

Хотим глубже?

Захотите разобраться чуть больше - [https://www.youtube.com/watch?v=gJNkZKRrKnk](https://www.youtube.com/watch?v=gJNkZKRrKnk)

[https://www.youtube.com/watch?v=SaVi8Mw4Ci8](https://www.youtube.com/watch?v=SaVi8Mw4Ci8)

[https://www.youtube.com/watch?v=4BcK_2-0grQ](https://www.youtube.com/watch?v=4BcK_2-0grQ)

[https://habr.com/ru/articles/785186/](https://habr.com/ru/articles/785186/)

[https://habr.com/ru/articles/834290/](https://habr.com/ru/articles/834290/)

[https://habr.com/ru/articles/828598/](https://habr.com/ru/articles/828598/)

[https://habr.com/ru/articles/799751/](https://habr.com/ru/articles/799751/)

## 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#besplatnye-sposoby)

**Бесплатные способы**

ЭТО БЕСПЛАТНЫЙ СПОСОБ = НЕ ГАРАНТИРОВАННО, ЧТО ОНО БУДЕТ РАБОТАТЬ И НАСКОЛЬКО ДОЛГО

## 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#amneziawg--warp)

AmneziaWG + WARP

Ставим вг клиент амнезии

(ПК)[https://github.com/amnezia-vpn/amneziawg-windows-client/releases/tag/1.0.0](https://github.com/amnezia-vpn/amneziawg-windows-client/releases/tag/1.0.0)

(ВЕДРО)[https://github.com/amnezia-vpn/amneziawg-android](https://github.com/amnezia-vpn/amneziawg-android)

(MAC/IOS)[https://apps.apple.com/pl/app/amneziawg/id6478942365](https://apps.apple.com/pl/app/amneziawg/id6478942365)

Следуем инструции на гитхабе [https://github.com/ImMALWARE/bash-warp-generator](https://github.com/ImMALWARE/bash-warp-generator) (НЕ ПОЛУЧАЕТСЯ? ПОПРОБУЙТЕ

[https://hub.ovh2.mybinder.org/user/tuftsdatalab-terminal-6pteh27y/terminals/1hub.ovh2.mybinder.org](https://hub.ovh2.mybinder.org/user/tuftsdatalab-terminal-6pteh27y/terminals/1)

ИЛИ

[https://terminator.aeza.net/ru/](https://terminator.aeza.net/ru/)

выбираем debain

```
apt install curl
```

```
curl -sSL https://raw.githubusercontent.com/ImMALWARE/bash-warp-generator/main/warp_generator.sh | bash
```

)

После того как скачали конфиг идем в софт (НА ВСЕХ УСТРОЙСТВАХ +- ОД~~НОХ~~ИНАКОВО)

![](HTML%20import/Attachments/image(34).png)

![](HTML%20import/Attachments/image(35).png)

Подключаемся ![](./Варим%20борщ%20правильно%20_%20how-to-varit-borsch_files/image(36))

Дурка снова стабильна

![](HTML%20import/Attachments/image(37).png)

### 

[](https://kekwaaait.gitbook.io/how-to-varit-borsch#ispolzuem-zapret-discord-youtube)

Используем zapret-discord-youtube

1. Заходим на гитхаб проекта [https://github.com/Flowseal/zapret-discord-youtube](https://github.com/Flowseal/zapret-discord-youtube)
    
2. Скачиваем последний релиз [https://github.com/Flowseal/zapret-discord-youtube/releases](https://github.com/Flowseal/zapret-discord-youtube/releases)
    
3. Разархивируем на рабочий стол
    
4. Запускаем от отмени админа `**service_discord.bat**`**/**`**service_discord_youtube.bat**` смотря что вам нужно. (прим. `**service_goodbye_discord.bat**` - запустить, если вы используете **СЕРВИС goodbyedpi**, и хотите, чтобы zapret **обходил только discord**. ВНИМАНИЕ: Запускать ПОСЛЕ создания сервиса goodbyedpi. Первый раз goodbyedpi может вылететь - просто перезапустите устройство!)
    
5. Все, дискорд работает (а если не работает - [читаем](https://github.com/Flowseal/zapret-discord-youtube?tab=readme-ov-file#%D0%BD%D0%B5-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82))
    

Видева -> [https://kinescope.io/bnqVDMey6SbpoLgx6oWVtw](https://kinescope.io/bnqVDMey6SbpoLgx6oWVtw)