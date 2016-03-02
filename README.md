# MQTT Adapter
Allows ITX maps to write to a MQTT server or listen for MQTT events in Launcher

## Minimum Requirements : 

ITX v9.0.0.x

## Command Alias : 

Adapter commands can be specified by using a command string on the command line or creating a command file that contains adapter commands. The execution command syntax is:

-IM[alias] card_num <br>
-OM[alias] card_num


where -IM is the Input Source Override execution command and -OM is the Output Target Override execution command, alias is the adapter alias, and card_num is the number of the input or output card. 


The following table shows the adapter alias and its execution command.

Adapter 	      :  MQTT <br>
Alias 	        :  MQTT <br>
As Input        :  -**IMMQTT**card_num <br>
As Output       :  -**OMMQTT**card_num <br>    	  


## MQTT Adapter commands

The following table lists valid commands for the MQTT Adapter, the command syntax

HOSTNAME (-H)     : Hostname

PORT (-P)	  : Port

PASSWORD (-PASS )  : Connection Password. (optional argument)


USERNAME (-U )  : Connection Username (optional argument)

TOPIC (-T) : Topic Name

ID (-ID) : Client ID

QOS (-QOS) : Quality of Services (0, 1, 2) (optional argument)


CTIMOUT (-CTIMOUT) : Connection time out


## MQTT Adapter Command Line Examples
###Inbound Adapter : 


SUPPORTED only in LISTEN mode (i.e Launcher).  Not Supported in GET or INPUT mode. 

Input Card : -H localhost -P  1883 -TOPIC MQTT.Examples -ID mymqtt.message.1


###Outbound Adapter : 

OutPut Card : -H localhost -P  1883 -TOPIC MQTT.Examples -ID mymqtt.message

PUT RULE : PUT("MQTT", "-H localhost -P  1883 -TOPIC MQTT.Examples -ID mymqtt.message -T", Input))



## MQTT Adapter Installation Instructions 


### Runtime

a) Create com.ibm.itx.dtx.mqtt under jars directory in  "WTX INSTALL" on windows and on UNIX. Drop m4mqtt.jar in the mqtt directory


b) Edit adapters.xml and add the following line (UNIX, the file is present under config folder)

M4Adapter name="MQTT" alias="MQTT" id="178" type="app" class="com/ibm/itx/dtx/mqtt"


c) Download PAHO MQTT Java client library from [PAHO](https://www.eclipse.org/paho/clients/java/) version 0.4.xx. Copy mqtt-client-xx.jar to com.ibm.itx.dtx.mqtt directory


####Note : For any defects or usage concerns, Open an issue ticket  in GITHUB and shall be addressed. 

