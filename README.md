```mermaid
flowchart TB
BEGIN(["Start"])
BEGIN --> B[/"Input templength, width"/]
B --> C["counter = 0"]

C --> D{"width > length"}

D1["length = width - (1.6*2) <br> width = templength - (1.6*2) </br>"]
D2["length = templength - (1.6*2) <br> width = width - (1.6*2) </br>"]

D --> |"TRUE"|D1

D --> |"FALSE"|D2

|"TRUE"|D1 --> E["length = round(length * 1000.00) / 1000.0 <br>
   width = round(width * 1000.00) / 1000.0 </br>"]
|"FALSE"|D2 --> E["length = round(length * 1000.00) / 1000.0 <br>
   width = round(width * 1000.00) / 1000.0 </br>"]

