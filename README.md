# Sniffer

Simple sniffer using scapy and PyQt5.

## Getting Started

Just download them all and run main.py

### Prerequisites

- Python 3.6
- Modified [scapy3k](https://github.com/phaethon/scapy) Used for multiprocessing purposes. Just use directly from here. 
- [ansi2html] (https://github.com/ralphbean/ansi2html)  Used to parse ANSI ESCAPE Sequence to html css.
- [psutil] (https://github.com/giampaolo/psutil)	Used to detect packet received amount in system level to calculate network speed. 
- [urllib3] (https://github.com/shazow/urllib3)  Used to parse HTTP Response
- [PyQt5] (https://riverbankcomputing.com/software/pyqt/download5)
- Need to install [Win10Pcap(Recommended)](http://www.win10pcap.org/), Npcap(might have slight issue of missing certain packets).
Only test and modify the lib concerning Windows users.


### Usage
```
pip install -r requirements.txt

python main.py
```

## Feature

Multiple features in this project.

### Filter on Network interfaces, Protocol, Src, Dst, Sport and Dport.

Choose the filter anytime you like and then click the start button twice to continue sniffing.(have to stop and start to take effect)

### Save selected packet(s) information to files, and even copy to clipboard.

Select one packet, or multiple packets. After using right clicks, you can save them into a txt file with readable format, or even copy
them into your clipboard(short-cut keys Ctrl-S,Ctrl-C). 

![Sample](/sample_pic/save_sample.gif "Sample")

### TCP/IP/HTTP reassembly and save them to files.

Select one packet, and it will automatically find related packets and reassemble them.
If the total fragments number is too big, it will give you the option to reassemble and decode it or not.
Remember that all the related fragments will be displayed immediately no matter what.
After that processing, you are welcome to click the `Reassembly` button below on the status to convert them into one entire file.
Only tested in FTP Transmission, HTML reassembly and ICMP(ping), and the file size can be up to 15MB (might take certain time processing to GUI).
New feature is added to show the whole size number after reassembly to have a quick peak of the whole process.

- sample of TCP/IP file saving Result:

![Sample](/sample_pic/reassemble_sample.gif "Sample")

- sample of HTTP(HTML) parsing Result:

![Sample](/sample_pic/html_sample.gif "HTML Sample")

### Search bar makes things easier

Using search bar wisely can actually save a lot of time.
Keywords are searched in whole packet's hex or decoded by UTF-8 and GB2312,which is very convenient to find http headers of filename.

### OC Mode

The default OC mode will never let you down when an additional dedicated process is used for listening and sniffing.
However, it is very CPU-consuming, but you can turn it off any time (have to stop and start to take effect)

### Network Speed

The ultimate style of Network Speed uses the API of psutil which is extremely accurate and responsive.


### Color Theme like WireShark

Every packet is sorted by the default color theme of wireshark. Default On. Using "Ctrl+F" to turn off/on.
ADD Mouse entering and leaving event for each row makes the UI more colorful and better.


## Overall quick look
- Sniffer v2.0: Colorful and powerful

![Sample](/sample_pic/overall_sample.gif "Sample")

