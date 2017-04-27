# teacher_apple
The message is composed using a web application that is stored and executed on a HTTP server and then sent through the internet ("the cloud") as an email message.
The email is received by a Short Message Service Gateway (SMS Gateway), which converts the message from an email message to a SMS message.
The SMS message is then handed to a Short Message Service Center (SMSC), which is a server that routes data to specific mobile devices.
The message is finally transmitted over the wireless network to the recipient.
I used textMagic from gitHub along with python to run my program. You have to have Python 2.6 or higher in order to run the program. 
# sms.py
# Sends sms message to any cell phone using gmail smtp gateway
# Written by Alex Le

import smtplib

# Use sms gateway provided by mobile carrier:
# at&t:     number@mms.att.net
# t-mobile: number@tmomail.net
# verizon:  number@vtext.com
# sprint:   number@page.nextel.com

# Establish a secure session with gmail's outgoing SMTP server using your gmail account
server = smtplib.SMTP( "smtp.gmail.com", 587 )

server.starttls()

server.login( '<gmail_address>', '<gmail_password>' )

# Send text message through SMS gateway of destination number
server.sendmail( '<from>', '<number>@tmomail.net', '<msg>' )
