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

E --> F1{"length >= 3 && width >= 1"}
G1[/"We would suggest you to choose Rectangle Shade with 12 seaters as the first choice."/]
F1 --> |"TRUE"|G1 --> H1["counter += 1"] --> F2
F1 --> |"FALSE"| --> F2
