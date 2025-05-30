# Relays | I2C vs CAN

## Relays
There are a variety of electrical and electronic devices which are classed as output devices used to control or operate some external physical process. These output devices including the electrical relay are commonly classed as **Actuators**.\
Actuators convert an electrical signal into a corresponding physical quantity such as movement, force, sound etc. An actuator is also classed as a transducer because it changes one type of physical quantity into another and is usually activated or operated by a low voltage command signal.\
Actuators can be classed as either binary or continuous devices based upon the number of stable states their output has. For example, a relay is a binary actuator as it has two stable states, either energised and latched or de-energised and unlatched, while a motor is a continuous actuator because it can rotate through a full 360° motion.\


A relay is an electrical switch that allows a low-power signal to control a high-power circuit. It acts like a remote-controlled switch, where a small input (such as from a sensor or microcontroller) can turn on or off a much larger electrical load (like a motor or light bulb).
Relays are used in many applications, including:
- Home automation (smart lights, AC systems).
- Automotive systems (starter relays, power windows).
- Industrial machinery (motor controls, safety switches).
- Electronics (protecting circuits, logic operations).

\
![Electromagnetic Relay](https://github.com/user-attachments/assets/a64e5fbc-0f8d-40ab-9667-3761a839633f)\

### Basic Principle
A relay has two main parts:
1.	Control Circuit (Primary Side) – A low-power input (e.g., from a switch or sensor) activates the relay.
2.	Load Circuit (Secondary Side) – The relay switches a high-power device (e.g., a motor or lamp).

![image](https://github.com/user-attachments/assets/dddebe4c-8cff-4b25-9c72-4d005bad0e42)

The key feature of a relay is electrical isolation — the control and load circuits are separate, preventing high voltage from damaging sensitive electronics.

#### Electromechanical Relay (EMR) Components
Most traditional relays are electromechanical, meaning they use a physical switch operated by an electromagnet. The main parts are:

Component |	Function
--- | ---
Coil |	Creates a magnetic field when electricity flows through it.
Armature | A metal lever pulled by the magnetic field, moving the switch.
Contacts | Metal pieces that connect or disconnect the load circuit.
Spring | Returns the armature to its original position when power is off.


#### How It Operates
1.	When the control signal is ON:
    - Current flows through the coil, creating a magnetic field.
    - The armature is pulled toward the coil, closing (or opening) the contacts.
    - The load circuit is now connected (or disconnected).
2.	When the control signal is OFF:
    - The magnetic field disappears.
    - The spring pushes the armature back.
    - The contacts return to their original state.

### Types of Relays
1. Based on Contact Configuration

Type|Description|Example Use
---|---|---
Normally Open (NO)|Contacts are open by default and close when energized.|Turning on a light when a sensor is triggered.
Normally Closed (NC)|Contacts are closed by default and open when energized.|Emergency shutdown systems.
Changeover (SPDT)|Switches between two circuits (one NO, one NC).|Alternating between two devices.
Double Pole Double Throw (DPDT)|Controls two separate circuits at once.	|Reversing motor direction.

![Relay Symbols](https://github.com/user-attachments/assets/b618a570-0cee-42e8-b149-a88fc2c5b1ea)
![SPST- Single Pole Single Throw](https://github.com/user-attachments/assets/87d626ed-16ca-4ab8-bc3f-6678a271cf86)
![SPDT- Single Pole Double Throw](https://github.com/user-attachments/assets/ace9f84b-2a4f-4281-8e9c-f601314e962c)
![DPDT- Double Pole Double Throw](https://github.com/user-attachments/assets/3f26d5e7-d1e3-4e47-8fa9-409ee784c84a)



2. Based on Functionality

Type|Description|Example Use
---|---|---
Latching Relay|Stays in its last state even after power is removed.|Elevator buttons, memory circuits.
Time-Delay Relay|Switches after a set delay (e.g., 5 seconds).|Staircase lighting, motor sequencing.
Overload Relay|Protects motors from overheating by cutting power.|Industrial motor controls.

> #### Latching relay
> Also called impulse, bistable, or stay relay, or simply latch, maintains either contact position indefinitely without power applied to the coil. The advantage is that one coil consumes power only for an instant while the relay is being switched, and the relay contacts retain this setting across a power outage. A latching relay allows remote control of building lighting without the hum that may be produced from a continuously (AC) energized coil.  
> In one mechanism, two opposing coils with an over-center spring or permanent magnet hold the contacts in position after the coil is de-energized. A pulse to one coil turns the relay on, and a pulse to the opposite coil turns the relay off. This type is widely used where control is from simple switches or single-ended outputs of a control system, and such relays are found in avionics and numerous industrial applications.
> 
> ![image](https://github.com/user-attachments/assets/23b40ac4-2286-4d74-a5ba-40d6afc8c0ff)
> ![image](https://github.com/user-attachments/assets/8c6ba789-6735-43cb-9f41-a3d93f1ac2a0)

>#### Overload Relay
>Electric motors need overcurrent protection to prevent damage from over-loading the motor, or to protect against short circuits in connecting cables or internal faults in the motor windings. The overload sensing devices are a form of heat operated relay where a coil heats a bimetallic strip to operate auxiliary contacts. These auxiliary contacts are in series with the motor's contactor coil, so they turn off the motor when it overheats.
>
>![image](https://github.com/user-attachments/assets/af27df80-a046-488f-ad00-264048387dd1)
>![image](https://github.com/user-attachments/assets/2d39991a-6014-442b-a10e-a7d466b798f0)






### Arcing/Sparking

When the contacts are closed the contact resistance should be zero, a short circuit, but this is not always the case. All relay contacts have a certain amount of “contact resistance” when they are closed and this is called the “On-Resistance”. With a new relay and contacts this ON-resistance will be very small, generally less than 0.2Ω because the tips are new and clean, but over time the tip resistance will increase.

For example. If the contacts are passing a load current of say 10A, then the voltage drop across the contacts using Ohms Law is 0.2 x 10 = 2 volts, which if the supply voltage is say 12 volts then the load voltage will be only 10 volts. As the contact tips begin to wear, and if they are not properly protected from high inductive or capacitive loads, they will start to show signs of arcing damage as the circuit current still wants to flow as the contacts begin to open when the relay coil is de-energized.

This arcing or sparking across the contacts will cause the contact resistance of the tips to increase further as the contact tips become damaged. If allowed to continue the contact tips may become so burnt and damaged to the point were they are physically closed but do not pass any or very little current.

If this arcing damage becomes too severe the contacts will eventually “weld” together producing a short circuit condition and possible damage to the circuit they are controlling. This high voltage drop across the contacts may be unacceptable for the load circuit especially if operating at 12 or even 24 volts, then the faulty relay will have to be replaced.

To reduce the effects of contact arcing and high “On-resistances”, modern contact tips are made/coated with a variety of silver based alloys to extend their life span as given:

#### Electrical Relay Contact Tip Materials

1. Ag (fine silver)
    - Electrical and thermal conductivity are the highest of all the metals.
    - Exhibits low contact resistance, is inexpensive and widely used.
    - Contacts tarnish easily through sulphurisation influence.
      
2. AgCu (silver copper)
    - Known as “Hard silver” contacts and have better wear resistance and less tendency to arc and weld, but slightly higher contact resistance.
      
3. AgCdO (silver cadmium oxide)
    - Very little tendency to arc and weld, good wear resistance and arc extinguishing properties.
      
4. AgW (silver tungsten)
    - Hardness and melting point are high, arc resistance is excellent.
    - Not a precious metal.
    - High contact pressure is required to reduce resistance.
    - Contact resistance is relatively high, and resistance to corrosion is poor.
      
5. AgNi (silver nickel)
    - Equals the electrical conductivity of silver, excellent arc resistance.
      
6. AgPd (silver palladium)
    - Low contact wear, greater hardness.

7. Platinum, Gold and Silver Alloys (expensive)
   - Excellent corrosion resistance, used mainly for low-current circuits.
  
Extending the life of relay tips by reducing the amount of arcing generated as they open is achieved by connecting a Resistor-Capacitor network called an RC Snubber Network electrically in parallel with an electrical relay contact tips. The voltage peak, which occurs at the instant the contacts open, will be safely short circuited by the RC network, thus suppressing any arc generated at the contact tips.

![RC snubber](https://github.com/user-attachments/assets/b24997b9-8afa-4c30-bbf8-700061083535)


### Why Use Relays?
- Electrical Isolation – Protects sensitive electronics from high voltages.
- Low-Power Control – A small signal (e.g., from an Arduino) can switch a large load (e.g., a 240V AC motor).
- Safety – Reduces risk of electric shock in control circuits.
- Multiple Circuit Control – One relay can switch several devices.
- Digital Compatibility – Works well with microcontrollers (e.g., Raspberry Pi, Arduino).


## Solid-State Relay (SSR)
Instead of mechanical parts, solid-state relays (SSRs) use electronic components (like transistors or TRIACs) to switch the load.\
The solid state relay being a purely electronic device has no moving parts within its design as the mechanical contacts have been replaced by power transistors or triac’s. The electrical separation between the input control signal and the output load voltage is accomplished with the aid of an opto-coupler type Light Sensor.\

![SSR](https://github.com/user-attachments/assets/8f45752b-5f34-407b-9c41-98874c4c6999)

Resistor-Capacitor (RC) snubber network is generally required across the output terminals of the SSR to protect the semiconductor output switching device from noise and voltage transient spikes when used to switch highly inductive or capacitive loads. In most modern SSR’s this RC snubber network is built as standard into the relay itself reducing the need for additional external components.

The Solid State Relay provides a high degree of reliability, long life and reduced electromagnetic interference (EMI), (no arcing contacts or magnetic fields), together with a much faster almost instant response time, as compared to the conventional electromechanical relay.

### Basic Principle
- An LED (on the input side) emits light when power is applied.
- A light-sensitive component (like a phototransistor or TRIAC) detects the light and switches the output.
- Since there are no moving parts, SSRs last longer and switch faster than EMRs.
#### Advantages:
- No mechanical wear (longer lifespan).
- Silent operation (no clicking sound).
- Faster switching (good for high-speed applications).
#### Disadvantages:
- Can overheat if not properly cooled.
- More expensive than EMRs for some applications.

> #### TRIACs [triode for alternating currents]
> Three-terminal bi-directional switch that conducts in both directions. It is made from the combination of two SCRs in anti-parallel with their gates joined together. TRIAC can be triggered into conduction by either positive or negative gate current in both directions and it switches off when the main current falls below the holding current limit. The symbol of TRIAC represents two thyristors connected in antiparallel having a common gate.
> 
> ![TRIAC](https://github.com/user-attachments/assets/5160916a-e3c5-49c7-86cc-97e0da263b2b)
> 

> #### OPTOCOUPLER
> An optocoupler, also known as an optoisolator or photocoupler, uses light to electrically isolate two circuits while transferring signals between them. It consists of a light-emitting diode (LED) and a photosensitive device, typically a phototransistor or photodiode, that converts the light into a current. This allows for signal transmission without direct electrical contact between the circuits.
> 
> ![Optocoupler](https://github.com/user-attachments/assets/243040ae-56d0-4d71-8cd5-232ef7ce0ba3)
>
> Optocouplers come in four configurations. Each configuration shares the same infrared LED with a different photosensitive device. These include:
> - Photo-Transistor and Photo-Darlington, used in DC circuits
> - Photo-SCR and Photo-TRIAC, used in AC circuits
>   
>![image](https://github.com/user-attachments/assets/963d862e-8c8d-4d4c-aaac-d4a89975e9e5)
> 
> An Optocoupler can effectively:
> - Remove electrical noise from signals
> - Isolate low-voltage devices from high-voltage circuits
> - Allow you to use small digital signals to control larger AC voltages  
> 
>They can either be used on their own as a switching device or with other electronic devices to provide isolation between low and high-voltage circuits. For e.g.:
> - Microprocessor input/output switching
> - DC and AC power control
> - Communications equipment protection
> - Power supply regulation



## Common Problems
1. Back EMF (Voltage Spike):
When a relay turns off, the collapsing magnetic field creates a sudden voltage spike (back EMF), which can damage circuits.
Use a flyback diode (also called a freewheeling diode) across the coil to absorb the spike.

![Flywheel diode](https://upload.wikimedia.org/wikipedia/commons/3/3a/Relay_animation_with_flyback_diode.gif)

3.  Contact Wear (in EMRs):
Mechanical relays wear out over time due to sparking when contacts open/close.

4. It is not advisable at all to connect relay contacts in parallel to handle higher load currents. For example, never attempt to supply a 10A load with two relay contacts in parallel that have 5A contact ratings each, as the mechanically operated relay contacts never close or open at exactly the same instant of time. The result is that one of the contacts will always be overloaded even for a brief instant resulting in premature failure of the relay over time.
    - Use SSRs for high-speed or long-life applications.
    - Choose relays rated for the correct current/voltage.

## References
[Wikipedia](https://en.wikipedia.org/wiki/Relay)  
[Electronic Tutorials](https://www.electronics-tutorials.ws/io/io_5.html)  
[The Engineering Mindset-YT](https://www.youtube.com/watch?v=n594CkrP6xE)  
[Electrical Technology](https://www.electricaltechnology.org/2021/08/triac.html)
[Optocoupler](https://www.autodesk.com/products/fusion-360/blog/how-an-optocoupler-works/)
