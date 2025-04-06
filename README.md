# tuesFest2025
Даденият проект демонстрира архитектурата на съвременните центрове за данни, която често се базира на използването на EVPN-VXLAN технологии, при които за underlay мрежата се използва eBGP, а за overlay – iBGP. Тази комбинация осигурява висока гъвкавост и поддръжка на мултитенантна среда, като същевременно предлага ясно разделение между физическата и виртуалната мрежова инфраструктура. Underlay мрежата представлява IP базиран транспортен слой, реализиран чрез eBGP peer-ване между leaf и spine устройствата в leaf-spine топология. В този модел всяко устройство се намира в собствена автономна система, което позволява по-добра изолация и по-проста маршрутизация. Чрез eBGP се рекламират адресите на loopback интерфейсите. Това изграждане на underlay позволява надеждно пренасяне на трафик и предоставя стабилна основа за overlay услугите. Overlay мрежата, от своя страна, използва iBGP с активирана EVPN address family и служи за обмен на информация за reachability на MAC и IP адреси между leaf устройствата, които действат като VTEP-и (VXLAN Tunnel Endpoints). Всяко leaf устройство използва своя loopback адрес като източник на VXLAN тунелите и чрез EVPN се рекламират съответните MAC и IP маршрути, включително тип 2 маршрути (MAC/IP advertisement) и тип 5 маршрути (IP prefix advertisement). За да се избегне необходимостта от пълна mesh топология между leaf switch-овете, spine устройствата се конфигурират като route reflectors в iBGP overlay сесията. Това улеснява управлението на overlay мрежата и я прави по-лесна за разширяване. EVPN-VXLAN overlay предлага и редица допълнителни възможности като ARP suppression, distributed default gateway и оптимизирано flooding поведение, което значително подобрява ефективността на мрежата. Комбинацията от eBGP за underlay и iBGP с EVPN за overlay позволява изграждането на мащабируема, модулна и надеждна мрежова архитектура, която премахва необходимостта от класически протоколи като STP и предоставя поддръжка за Layer 2 и Layer 3 услуги над IP транспортна инфраструктура. Това прави архитектурата изключително подходяща за модерни облачни и виртуализирани среди, като същевременно опростява операциите и улеснява автоматизацията на мрежата.
