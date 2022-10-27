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

D1 & D2 --> E["length = round(length * 1000.00) / 1000.0 <br>
               width = round(width * 1000.00) / 1000.0 </br>"]
               
E --> F1{"length >= 3 && width >= 1"}

G1[/"We would suggest you to choose Rectangle Shade with 12 seaters as the first choice."/]
H1["counter += 1"]

F1 --> |"TRUE"|G1 --> H1
F1 --> |"FALSE"|G2

H1 & G2 --> F2{"length >= 3 && width >= 1.3"}
