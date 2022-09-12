Welcome to my GitHub

Digirig - APRS
  as found on youtube.com Baofeng APRS Digipeater
  
Install direwolf
Gather information:
    arecord -l      Looking for Card# and Device# ie. 3,0
    ls -l /dev/serial/by-id   ie. ttyUSB0
Edit direwolf.conf in the home directory
    ADEVICE     plughw:3,0
    MYCALL      KE7UIA-4    (see www.aprs.org/aprsll/ssids.txt)
    MODEM       1200
    PTT         /dev/ttyUSB0 RTS
    PBEACON     delay = 1
                every = 30
                overlay = S
                Symbol = "digi"
                lat = 40^19.94N
                log = 111^53.52W
                power = 5
                height = 20
                gain =1
                comment = "Pizza Box digi"
                via = WIDE1-1, WIDE2-1
    DIGIPEAT 0 0 ^WIDE[3-7]-[1-7]$|^TEST$ ^WIDE[12]-[12] ^TRACE
    IGSERVER noam.nprs2.net
    IGLOGIN KE7UIA-4 18099 #See (apps.magicbug.co.uk/passcode)
    PBEACON     send to = IG
                delay = 0:30
                every = 60:00
                symbol = "igate"
                overlay = R
                lat = 40^19.94N
                long = 111^53.52W 
    IGTXVIA 1 WIDE -1
    IGLIMIT 6 10
    
start the program with direwolf -p
