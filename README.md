"# DeciConn" 

This software is free for use, please use this with your own judgment, this can break your device - I'm not assuming any responsibility if it happens to damage your device. 
The original work for the library behind this repo was done by Quentin and Stuart under unix based operating systems. I have only ported some code for a library (pylibftdi) to be available on windows using a different ftdi library.

After you launch the application, a webserver will run on port 8080. You can access it either via your "localhost" or via local ip (or public ip after you setup your portforwarding) using a web browser or you can fire http get commands via POSTMAN or any other software ( Companion for ex.)

Make sure you are making GET requests instead of POST, otherwise these won't work.

http://localhost:8080/list - will list your device serial number. The API is using serial number to identify between multiple devices. ( Yes you can use multiple devices ) 

http://localhost:8080/status/your-serial - will give you a status read of the FTDI chip showing what model of the device it is and other bits (i.e http://localhost:8080/status/MDA01705)

http://localhost:8080/set/your-serial/NumWindows/tilesNo - this function sets the multiview Windows number. !Warning - the numbering starts from 0 rather than 1 so if you want a 4 way multiview you need to type "3" not "4" 

http://localhost:8080/set/your-serial/MVLayout/layoutNo - This function sets the MVLayout that you have previously setup using UCP software. Unfortunately, you're not going to be able to position the tiles and create custom layouts using this software but you can change the Layouts that you have previously setup using the UCP software.


Thanks to: 
Quentin Smith (https://github.com/quentinmit/decimctl) for doing the reverse engineering work and the original work.
Stuart Burton (https://github.com/Stuart-Burton/DeciMate) for doing the web-server work.
