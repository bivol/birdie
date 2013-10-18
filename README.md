The Birdie Project
======
Affordable secure calls over any carrier

Available solutions:

Existing secure voice is implemented over data links, IP or CSD, requiring a data plan subscription.
Devices using data cryptocalls can be tracked by IMEI/IMSI or the service subscription.
App solutions might be not secure if phone OS is compromised.
There is a limited choice of generally expensive devices (cryptophones) and apps.

The Birdie goal: Secure voice for the masses

Implementing scrambled voice over any carrier: GSM/UMTS/LTE (2G to 4G), PSTN (landlines), VoIP (Skype, Viber, etc.);
Uses the voice channel, no data plan required;
The (de)scrambling device looks like a classic hands-free (box with mic/earphones and 3.5 mm TRRS phone connector or a bluetooth headset) ;
Phone/SIM card independent - less trackable; 
Cheap: 30 - 50 $ hardware for the device;
Тransparеnt to the mobile voice codecs;
Open source software:
	- no NSA backdoors;
	- community-supported;

The Birdie concept:

1. Data link over voice channel: Establish a low baud modem link between the devices over the voice channel;

2. Keys
2.A. Key generation: Generate 20 keys - 64 bits numbers (short keys, hardware random number generator https://en.wikipedia.org/wiki/Hardware_random_number_generator);
OR
2.B. Key generation: Generate 1 key 4096 bits (long key, deterministic PRNG)

3. Key exchange: Exchange the key(s) with Diffle-Hellman via the modem link;

4. Wave Scrambling: ADC + digital filter + wave inversion formula + digital filter + DAC

Example wave invert formula: (wave (time) + elliptical function (time + key)) / 2

A. The key changes every 30 sec (short key).
OR
B. The key is not changing during the session (long key)

Clocks drifting must not exceed 1/8000 sec. If clocks desync, the modem link or a GPS can be used to keep them synced.

The Birdie project stages (early preliminary estimations):

1. Mathematical concept and first code - Q4 2013;
2. Data link & key exchanges between linux boxes Q4 2013 - Q1 2014;
3. Scrambling with fixed keys between linux boxes (direct audio link) Q4 2013 - Q1 2014;
4. Data link, key exchanges, scrambling between linux boxes over GSM voice channel Q1 2014 - Q2 2014;
4. Hardware spec & design Q1 2014 - Q2 2014;
5. HW prototype Q2 2014 - Q3 - 2014;
