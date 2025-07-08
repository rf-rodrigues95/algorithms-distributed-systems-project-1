# Project Phase 1: Algorithms and Distributed Systems
**NOVA School of Science and Technology (NOVA FCT)** – 2024–2025    
**Final Grade:** 18.30  
**Group:** 
  - Ricardo Rodrigues (rf-rodrigues95)
  - Gonçalo Virgínia (goncalovirginia)
    
This project implements a decentralized peer-to-peer point-to-point communication system using a DHT for routing messages between uniquely identified peers. It ensures message delivery even when peers are offline by leveraging helper nodes, with mechanisms to handle redundancy and failure.

## Project description

[See the PDF](./docs/Project-Phase1.pdf)

## Final report

[See the PDF](./report/ASD_Project_1.pdf)

## Instructions

### Compile

```.../asd2024-proj1-main> mvn clean compile package```

### Run

- `babel_config.properties`:
  - `n_peers`: maximum amount of peers the DHT will operate with (Default value is 100)
  - `id_bits`: number of bits used for peer ID's, either 256 or 512 (Default value is 256)

1. **First process:** `.../asd2024-proj1-main> java -cp target/asdProj.jar Main port=10101 processSequence=1`  
2. **Second and subsequent processes:** `.../asd2024-proj1-main> java -cp target/asdProj.jar Main port=10102
     contact=127.0.0.1:10101 processSequence=2`
     - Use a different port and processSequence for each new process
     - Every new process should point to an existing process via the `contact=ip:port` parameter
