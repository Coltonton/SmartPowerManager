# SmartPowerManager 

Yesss... I knowwwww... It's broken and crude but with some moderations it works, I'll prolly fix everything but it works for me and no one will see this so eh... hahah 

 
 

A design of mine as I didn't find anything that fits my use to my.. desire? This is a power switching module that allows a system to have absolutely no power draw when off. Perfect for automotive applications, exactly my use!  

 
 

It will be easy to explain my use case to help describe this project. I needed a way to have access to constant power from the battery when it was needed following the following requirements: 

 
 

- On whenever the vehicle is on. 

- Turn on on approach & get systems booted. 

- Stay on when the vehicle turns off until all applicable systems are safely shut down 

- Ability for multiple systems to have isolated control 

- Ideally incorporate "ON" detection 

 
 

Admittedly some of these requirements are fulfilled by my specific vehicle but I still needed to incorporate.  

 
 

## The Juicy Details 

### About the Relay 

The relay is controlled on the low side the 3 inputs or the trigger provide 5V constant to one side of the relay coil. The coil can only be grounded through one of the 4 transistors; 1 transistor per controller I/O and one transistor for the trigger this allows for isolated control and acts as one big OR-Gate, as long as the Trigger, or any of the 3 I/Os are "on" the module stays on. It only shuts off when all circuits are off.  

 
 

### Controler I/O 

 
 

### The Trigger 

This is a trigger for the module to... trigger... (obviously) the module to power on and close the relay, it is designed to take a 12V signal (thus the 5V REG) You will need to find a reliable On/Off signal in your car to run this. I have found in my 2015 Subaru legacy the signal to light up the push button start is just that and turns on with the approach lighting and is basically always on unless the car goes to sleep. You will have to be careful. most vehicle ambience lighting is PWM controlled (as the lights usually dim up and down) and will drive the relay crazy... Thats no good... I was lucky to find this binary signal. alternately you can also just bridge the solder points of the ACC connector to this to have basic trigger with accessory power. Feel free if you want to trigger with a 5V signal to remove the 5V regulator and jump a wire between pin 1 & 3 you certainly may! 

 
 

### ACC Input: 

Are you dense? Must I really explain this one?? K... fine... The ACC input on this module receives power from your vehicles accessory signal and powers some opto-isolators giving your controllers an isolated from 12V accessory signal! Wow! There are 2 Optos you can install for if you have like me a 3.3V tolerant system and 5V tolerant systems. Yeah you could just use the 3.3 on the 5 just fine, but what's the fun in that?! OP1 connects to CON1(ESP) and CON2 while OP2 is just for CON3(SBC). You could of course if needed just bridge the Optos pin 4 from OP1 to the OP2 pin 4 hole to drive all 3 off one Opto! 

 [![](https://i.imgur.com/qkrK4sllll.png[/img])](#) 