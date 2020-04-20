# Assignment-1
Penetration Testing Framework with Python
import masscan import os import string import sys from masscan import * import pcap from scapy.all import rdpcap ---- to read pcap file from scapy.all import wrpcap ----- to write pcap file import sys from socket import * from socket import AF_INET, SOCK_STREAM from datetime import datetime

print ("1. IP/Port scanning") print ("2. Network sniffer") print ("3. Password cracking using john") print ("4. Display number of running services") i=input("Enter a number to choose a service: ") if i==1 : try: mas = masscan.PortScanner() except masscan.PortScannerError: print("masscan binary not found", sys.exc_info()[0]) sys.exit(1) except: print("unexppected error:", sys.exc_info()[0]) sys.exit(1) print ("masscan version:",mas.masscan_version) mas.scan('192.168.0.17/24', ports='21,22,80') print("masscan command line:", mas.command_line) print mas.scan_result

if i==2 :

try: s = socket.socket(socket.AF_INET, socket.SOCK_RAW, socket.IPPROTO_TCP) except socket.error , msg: print 'Socket could not be created. Error Code : ' + str(msg[0]) + ' Message ' + msg[1] sys.exit()
