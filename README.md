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
vagrant@vagrant:~$ traceroute -I 8.8.8.8

traceroute to 8.8.8.8 (8.8.8.8), 30 hops max, 60 byte packets

 1  _gateway (10.0.2.2)  0.360 ms  0.311 ms  0.507 ms
 
 2  192.168.60.1 (192.168.60.1)  5.220 ms  4.846 ms  5.070 ms
 
 3  * * *
 
 4  77.37.250.192 (77.37.250.192)  4.207 ms  5.085 ms  4.866 ms
 
 5  77.37.250.249 (77.37.250.249)  4.663 ms  5.379 ms  5.948 ms
 
 6  72.14.209.81 (72.14.209.81)  5.737 ms  5.276 ms  4.578 ms
 
 7  209.85.250.231 (209.85.250.231)  5.131 ms  11.504 ms  10.565 ms
 
 8  108.170.250.99 (108.170.250.99)  9.656 ms  10.495 ms  9.425 ms
 
 9  142.251.49.24 (142.251.49.24)  22.798 ms  22.213 ms  21.936 ms
 
10  172.253.65.82 (172.253.65.82)  21.338 ms  20.392 ms  17.317 ms

11  172.253.70.49 (172.253.70.49)  26.758 ms  25.712 ms  24.678 ms

12  * * *

13  * * *

14  * * *

15  * * *

16  * * *

17  * * *

18  * * *

19  * * *

20  * * *

21  dns.google (8.8.8.8)  20.643 ms *  18.717 ms


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
