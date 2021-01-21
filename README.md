![](imgs/Banner.svg)

-------------------------------------------------------
### Viewing the virtual lab
To view the virtual lab connect to the Swansea University VPN and navigate in your favourite browser to 
```
http://cs-s-fleming-pc.swan.ac.uk:4000
```
Any issues accessing the virtual lab display contact please post a query in the ```raise-your-hand``` channel in the lab Discord.

-------------------------------------------------------
### Communicating with your device
Commands are sent to your dotDevice from your ESP32 via WebSockets to the central EmSys Lab server. The address of the EmSys Lab server is ```ws://192.168.1.3``` Please refer to the [Lab1 handout](https://github.com/STFleming/EmSys_Lab1) for how to establish the websocket connection.

The command format is a JSON formatted string with the following format:
```
{
        "device": "<YOUR DEVICE NAME>",
        "cmd": "<COMMAND YOU WISH TO EXECUTE>",
        <AUXILLARY COMMAND SPECIFIC ARGUMENTS>
}
```

Where ```<YOUR DEVICE NAME>``` is a unique name for your device that has been assigned to your device. If you do not know the name of your device please post a query in the ```raise-your-hand``` lab Discord channel.

The Table below contains a list of commands that you can send to your device in the ```<COMMAND YOU WISH TO EXECUTE>``` field. It also contains details on the ```<AUXILLARY COMMAND SPEFIC ARGUMENTS>``` for each command.
In all the examples we shall use the example device ```C0FFEE```.

| __Command__                |  __Auxillary Command Specific Arguments__ |    __Example__ |
|----------------------------|---------------------------|--------------------------------|
| __SAY__     |    ```"text" : "<TEXT YOU WANT TO WRITE>"``` | ```{"device":"C0FFEE", "cmd":"SAY", "text": "Hello!"} ```                                |
| __COLOUR__  |    ```"colour" : "<HEX COLOUR CODE>"``` | ```{"device":"C0FFEE", "cmd":"COLOUR", "colour": "#FFFFFF"} ```                                |
| __SIZE__    |    ```"size" : <SIZE VALUE BETWEEN 0 - 20>``` | ```{"device":"C0FFEE", "cmd":"SIZE", "size": 10} ```                                |
| __ADJUST_XPOS__ |    ```"dx" : <CHANGE IN X POSITION>``` | ```{"device":"C0FFEE", "cmd":"ADJUST_XPOS", "dx": 2} ```                                |
| __ADJUST_YPOS__ |    ```"dy" : <CHANGE IN Y POSITION>``` | ```{"device":"C0FFEE", "cmd":"ADJUST_YPOS", "dy": 2} ```                                |
| __LOAD__ |    -  | _See the Programming your dotDevice section_        |
| __TIMER_CFG__ |    -  | _See the Programming your dotDevice section_        |
| __TIMER_VAL__ |    -  | _See the Programming your dotDevice section_        |
| __RUN__ |    -  | _See the Programming your dotDevice section_        |
| __HALT__ |    -  | _See the Programming your dotDevice section_        |

-------------------------------------------------
### Programming your dotDevice
![](imgs/programmable_architecture.svg)
