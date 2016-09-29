# clamav_tools
ClamAV related scripts and tools

--

*clamav_to_yara.py
Download the latest ClamAV signature database:
wget http://database.clamav.net/main.cvd

Use sigtool to unpack:
sigtool --unpack main.cvd

Then convert ClamAV signatures to Yara format:
python clamav_to_yara.py -f main.ndb -o main.yara

main.yara is now ready for use with yara:
yara -r main.yara /home/user
