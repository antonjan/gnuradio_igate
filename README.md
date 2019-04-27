# gnuradio_igate
This repository will have the code of a gnuradio igate resever with direwolf<br>
This application can demodulate two fm signals at the same time from one rtl_tcp source.
I wanted to igate local aprs on 144.700Mhz and 145.825 Satelite signal with one sdr_dongle.<br>
I then wanted to send the audio to direwolf as two chanels sothat direwolf can igate the decoded data to the aprs network<br>
rtl_tcp  >>> gnuradio fm demod >>>>> direwolf afsk decoding and igate<br>
The rtl_sdr dongle has a 2m band with so if I select a center frequency between 144.700 and 145.825 and use the two offset frequency input boxsess to tune the fm demodulators to the two frequencies.<br>
EG center frequency of 145.34M will need to tune to 144.700M by adding a shift of -640.0khz to get my 144.700<br>
to get the 145.825<hz I will have to add 485.0khz to get to 145:825Mhz<br>
The Audio will be send to ALSA device and I was using the Local loopback device to send the two adio chanels to direwolf to decode<br>
Then configure direwolf to read the two aduio chanels and demodulate the afsk and igate it to the internet.<br>
The waterfall on the screen is two fft signals combined so to see both carriors<br>
# How to use
Get an rtl -sdr dongle<br>
install rtl_sdr<br>
run the command rtl_tcp<br>
start your gnuradio-companion<br>
open the application igate_for_zr6aic_145_825_v1.grc<br>
Adjust center frequency and the two ofsents for your use.<br>
Then configure alsa loopback and direwolf to decode the audio signals.
# Project status
Gnuradio fm demodulator work but alsaconfig and direwolf details still need to be added.





