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

G11[/"We would suggest you to choose Rectangle Shade with 12 seaters as the first choice."/]
COUNT1["counter += 1"]

F1 --> |"TRUE"|G11 --> COUNT1
F1 --> |"FALSE"|G12

COUNT1 & G12 --> F2{"length >= 3 && width >= 1.3"}

H11{"counter == 0"}
H12{"counter == 1"}
H13{"counter == 2"}
G21[/"We would suggest you to choose Oval Stefan with 10 seaters as the first choice."/]
G22[/"We would suggest you to choose Oval Stefan with 10 seaters as the second choice."/]
COUNT2["counter += 1"]


F2 --> |"TRUE"|H11
H11 --> |"TRUE"|G21 --> COUNT2
H11 --> |"FALSE"|H12

H12 --> |"TRUE"|G22 --> COUNT2
H12 --> |"FALSE"|H13
