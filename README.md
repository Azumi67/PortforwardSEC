

<p align="center">
  <img src="https://github.com/Azumi67/PortforwardSec/assets/119934376/8993e9dc-6b78-4543-850c-6c5e6dcc9843" alt="OIP">
</p>
<div align="center">

Hello Azumi Desu !!

</div>

- این برنامه برای یادگیری بیشتر و ipsec نوشته شده است و این برنامه در طی زمان، بهبود میابد. اگر دوست داشتید استفاده کنید
- در حال حاضر من از این برنامه برای گیم آنلاین هم استفاده میکنم.
- اسکریپت هم برایش میسازم.
- هم چنین udp با استفاده از سوکت و buffer size و codereedsolomon اضافه شده است.
- در udp از reedsolomon برای کاهش پکت لاس استفاده شده که به عبارتی از two data shards and two parity shards استفاده شده است
- از هدر استفاده نکنید چون شاید مشکل دار شوید. در هر صورت برای گیم به هدر نیازی ندارم. بعدا به این پروژه xray core را در صورت امکان اضافه میکنم .
- این پورت فوروارد با لوکال و ipsec استفاده خواهد شد(برای امنیت بیشتر) و‌فعلا این پروژه در حالت on hold خواهد بود تا نخست پنج سرور ایران و 10 سرور خارج را کامل کنم و سپس رادار‌ برای اسکریپت 6to4.( کم کم اپدیت میشود)
- این پورت فوروارد بعدا با تانل داخلی هم ترکیب خواهد شد
- بعدا tcp no delay هم اضافه میکنم
- بعدا این پروژه اپدیت خواهد شد و برای ترکیب با پروژه های دیگر،‌ feature های جدید در صورت نیاز اضافه خواهد شد.
- اگر‌ از این پروژه استفاده کردید و مشکلی دیدید میتوانید در قسمت issues یا ایمیل به اطلاع من برسانید
- مرسی از engboy که در تست به من کمک بسیاری کردند
.

Simple portforward IPV4 | IPV6 - TCP | UDP [needs working] . there will be more updates. i will use this port forward in cojunction with IPsec encrypion methods. this project will be updated in time. this will be combined with systemd service for multiple ports.

 **برای استفاده از گو پکیج گو را اول نصب کنید.(میتونید از اسکریپت پروژه های گو من برای نصب استفاده نمایید)**
- install go package
- run : sudo apt-get install git-all
- download: git clone https://github.com/Azumi67/PortforwardSec
- Go to dir : cd PortforwardSec
- go clean -modcache
- go mod tidy
- go get github.com/Azumi67/PortforwardSEC/tcp
- go get github.com/Azumi67/PortforwardSEC/udp4
- go get github.com/Azumi67/PortforwardSEC/udp6
- go get github.com/klauspost/reedsolomon
- Now run With Go [TCP] : go run azumi.go ip-iran port-iran ip-kharej port-kharej tcp
- Now run With Go [UDP4] : go run azumi4.go --iranPort portiran --remoteIP ipkharej --remotePort portkharej --bufferSize 65535
- Now run With Go [UDP6] : go run azumi4.go --iranPort portiran --remoteIP ipkharej --remotePort portkharej --bufferSize 65535

=======

**Note** : example for upgrade : go get -u github.com/Azumi67/PortforwardSEC/udp4

=======

TCP Example :

example IPV4 : go run azumi.go 1.1.1.1 5050 1.1.1.2 5050 tcp

example IPV6 : go run azumi.go :: 5050 2002::db8:1 5050 tcp

UDP Example 

example IPV4 : go run azumi4.go --iranPort 5051 --remoteIP 200.100.20.100 --remotePort 5051 --bufferSize 65535

example IPV6 : go run azumi6.go --iranPort 5051 --remoteIP 2002::db8:1 --remotePort 5051 --bufferSize 65535
