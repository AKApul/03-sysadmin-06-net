# 03-sysadmin-06-net
1. HTTP/1.1 301 Moved Permanently
Данный код означает, что ресурс был перемещен в новое местоположение, далее можно увидеть куда идет перенаправление - https://stackoverflow.com/questions.

2. Status Code: 307 Internal Redirect
Дольше всего обрабатывался запрос GET https://stackoverflow.com/questions (240 ms)

https://disk.yandex.ru/i/MFfl2UIZdPbOfg

https://disk.yandex.ru/i/9pCBe3JiNjoaJg


3.
vagrant@vagrant:~$ curl ifconfig.me/ip
77.37.192.117

4.Провайдер NCNET (Национальные кабельные системы, т.е. РосТелеКом), AS 42610


vagrant@vagrant:~$ whois 77.37.192.117

% This is the RIPE Database query service.

% The objects are in RPSL format.
%
% The RIPE Database is subject to Terms and Conditions.

% See http://www.ripe.net/db/support/db-terms-conditions.pdf

% Note: this output has been filtered.

%       To receive output for a database update, use the "-B" flag.

% Information related to '77.37.168.0 - 77.37.247.255'

% Abuse contact for '77.37.168.0 - 77.37.247.255' is 'abuse@rt.ru'

inetnum:        77.37.168.0 - 77.37.247.255

netname:        NCN-BBCUST

descr:          NKS broadband customers

country:        RU

admin-c:        NCN7-RIPE

tech-c:         NCN7-RIPE

status:         ASSIGNED PA

mnt-by:         NCNET-MNT

mnt-lower:      NCNET-MNT

created:        2008-12-10T15:27:23Z

last-modified:  2010-01-20T13:01:19Z

source:         RIPE

role:           NCNET NCC Operations

address:        National Cable Networks

address:        Nagatinskaya str., 1, bldn. 26

address:        117105 Moscow, Russia

org:            ORG-NCN1-RIPE

admin-c:        RVP-RIPE

tech-c:         RVP-RIPE

phone:          +7 495 6859542

fax-no:         +7 495 6859530

mnt-by:         NCNET-MNT

nic-hdl:        NCN7-RIPE

created:        2007-03-26T07:46:58Z

last-modified:  2015-10-12T11:53:05Z

source:         RIPE # Filtered

abuse-mailbox:  abuse@moscow.rt.ru


% Information related to '77.37.192.0/18AS42610'

route:          77.37.192.0/18

descr:          NCNET

origin:         AS42610

mnt-by:         NCNET-MNT

mnt-lower:      NCNET-MNT

created:        2009-12-30T09:46:07Z

last-modified:  2009-12-30T09:46:07Z

source:         RIPE

% This query was served by the RIPE Database Query Service version 1.101 (HEREFORD)

5.
vagrant@vagrant:~$ traceroute -IA 8.8.8.8

traceroute to 8.8.8.8 (8.8.8.8), 30 hops max, 60 byte packets

 1  _gateway (10.0.2.2) [*]  0.747 ms  0.199 ms  0.249 ms
 
 2  192.168.60.1 (192.168.60.1) [*]  1.647 ms  2.439 ms  2.243 ms
 
 3  * * *
 
 4  77.37.250.192 (77.37.250.192) [AS42610]  4.863 ms  4.467 ms  4.261 ms
 
 5  77.37.250.249 (77.37.250.249) [AS42610]  7.730 ms  7.180 ms  6.955 ms
 
 6  72.14.209.81 (72.14.209.81) [AS15169]  6.710 ms  7.271 ms  7.045 ms
 
 7  209.85.250.231 (209.85.250.231) [AS15169]  9.809 ms  9.590 ms  9.371 ms
 
 8  108.170.250.99 (108.170.250.99) [AS15169]  9.159 ms  9.254 ms  8.232 ms
 
 9  172.253.66.116 (172.253.66.116) [AS15169]  23.175 ms  35.651 ms  34.967 ms
 
10  172.253.66.108 (172.253.66.108) [AS15169]  29.861 ms  28.279 ms  26.786 ms

11  142.250.56.125 (142.250.56.125) [AS15169]  28.454 ms  28.164 ms  29.043 ms

12  * * *

13  * * *

14  * * *

15  * * *

16  * * *

17  * * *

18  * * *

19  * * *

20  * * *

21  * dns.google (8.8.8.8) [AS15169]  21.920 ms  19.691 ms


6.
наибольшая задержка на узле 172.253.65.82

https://disk.yandex.ru/i/nrnV68IpQ1Zgug

7. 
DNS-сервера:

dns.google.             7181    IN      NS      ns4.zdns.google.

dns.google.             7181    IN      NS      ns3.zdns.google.

dns.google.             7181    IN      NS      ns2.zdns.google.

dns.google.             7181    IN      NS      ns1.zdns.google.

A-записи:

dns.google.             504     IN      A       8.8.4.4

dns.google.             504     IN      A       8.8.8.8

vagrant@vagrant:~$ dig dns.google A +noall +answer

dns.google.             442     IN      A       8.8.4.4

dns.google.             442     IN      A       8.8.8.8

vagrant@vagrant:~$ dig dns.google ns +noall +answer

dns.google.             7032    IN      NS      ns4.zdns.google.

dns.google.             7032    IN      NS      ns3.zdns.google.

dns.google.             7032    IN      NS      ns2.zdns.google.

dns.google.             7032    IN      NS      ns1.zdns.google.

8.
vagrant@vagrant:~$ dig -x 8.8.8.8 +short

dns.google.

vagrant@vagrant:~$ dig -x 8.8.4.4 +short

dns.google.
