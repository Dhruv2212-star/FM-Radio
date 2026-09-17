*While going through instagram reels, i came across a really cool project in which the guy used just some copper wires and an crystal  
and some earphones to make a DIY radio that you can listen to and i remembered that there was an YSWS where you can make a Radio and get it for yourself  
so i stopped doomscrolling and sat on my PCB and started the initial research.*

- **What was the initial research?**
  well my initial research included watching some examples of DIY radios and i saw the kit and the parts with which i was supposed to
  build it so i started to go through the data sheets and made the final connections roughly and started making the connections on Kicad
  after downloading the resources available on the static website (footprints & symbols)
  
# PCB in kicad | 2 hours  
the main reason why it took so long is because i had to debugg footprint issues again and again and work around with the resistors.  
while making the schematic i realized that the 2 10K resistors that were in the tutorial were pointless for my build so  
i had to remove them as the potentiometers were already connected to the ground and the other thing being the DRC list which kept flagging, and i resized my silkscreen art which took me quite some time to figure out because i later realised that you cannot resize your art so in the end i just remade it again and i kinda had to arrange the components again and again so that was one annoying thing tho.
issues related to footprint so that had to be fixed. also after doing all that i realised that the Gerber files came out incomplete and corrupted so i had to fix that later  
<img width="806" height="551" alt="14 09 2026_14 18 17_REC" src="https://github.com/user-attachments/assets/5372f0da-806d-4273-b12e-9b1b41ba6dcb" />


Lapse: https://lapse.hackclub.com/timelapse/lmbW12xKm2o3  

# Making the Firmware! | 40 mins 
**AI ussage declaration: Ai has been used for writing the skeleton of this firmware because it was hard to start from zero hence i had to learn how the main frimware will work and later i spet time on making my final code**  
i started with the basics which is i searched for the required libs and i got to know that for our build we need 2 main libs- Included Arduino + I²C libraries, so after adding these i started with defining the GPIO pins that i used.  
created the functions to communicate with RDA5807 which includes- write, read and check registers and also check weather the radio is connected or not. i had quite some difficulties trying to figure out the correct funtions for it so i went and looked up some tutorials on YouTube of people doing this and i found the correct required function and loop.  
after that i set the range for our FM radio and the spacings in between the frequency which is 100Khz.  
then i added the radio functions such as- setfrequency, seekstation, set mute, etc. this was quite easy as i had to just google it and i found this part very easy.  
then i set the controls for the radio as give in the README file. this sums up the Firmware process 

# CAD | 1 hour 23 mins
I had to figure out a LOT of things here because i had to take count of the tolerances and the distance for the each opening such as the usb c in which i had to take around 10 measurements from the PCB model just for it to fit properly at it's place and i had to also look up the correct dimensions for the speaker holes because many 1W speakers had different shapes but i set one in the in which were 35mm 1W 8 ohms speakers which were fitting the best for my use so i cut out the holes for fitting them in between the case.  
Final thing was the Top case, it was easy but i messed up twice making it. I made it the same size as the bottom case and the second time i forgot to account for the tolerance making it time taking  
In the end i finished the project with making the assembly file where i fit the PCB, bottom case, and the top case together  
bottom case and assembly took most of the time as setting the correct distance for antenna, potentiometers and the C port for Xiao  

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/17189bdc-cb01-4642-aafc-7112e4ededb1" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c96fd66b-0ca9-469a-89f3-bd009788ab7b" />

<img width="557" height="479" alt="Image of proj" src="https://github.com/user-attachments/assets/d4f9a909-03b6-4fd2-b93c-800f7bf7b74e" />

Lapse: https://lapse.hackclub.com/timelapse/YyshfXtkXlj3
