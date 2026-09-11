
Scientific-technical revolution (1940-1970)

## The Computer Revolution

Computers are pervaisive
###### Novel Applications
- Computer in auto
- UAV
- Human genome project
- ML/AI
- Quantam Computing

## Four Classes of Computers

##### Personal Computers
-

#### Embedded Computers
- Hidden as components of systems
- run single applications integrated with hardware
- Think IOT

#### Supercomputers
- High-end scientific and engineering calculations

## The Art of Managing Complexity

- Microarch links the logic and arch levels of abstraction
- The architecture level describes computer from the programmers perspective
- focused on registers, instructions, datapaths, controllers


We are mostly focused on digital circuits -> (AND GATES, OR GATES, XOR GATES, etc)
Logic (Adders, Memory)
Microarch (Datapaths, controllers)

## Seven Great Ideas

- Use abstraction to simplify design
- Make common case fast
- Performance via parallelism
	- Could mean multiple computation/exec units or even out of order or speculative computation

- Specultive computation is probability on which branch to take to say in an if statement based on some sort of prob with context

- Performance via pipelining
	- Once pipeline is full completes n step ops once per clock cycle instead of once per n clock cycles
- Perf via prediction
	- if future instructions not known because of branch in code make best guess and start in advance

- Hiearchy of memories
	- fastest mem can be expensive and power and space hungry
	- conflict addr by heiarchy where fastest,smallest and most expensive at top and largest slowest cheapest at bottom
- Dependability