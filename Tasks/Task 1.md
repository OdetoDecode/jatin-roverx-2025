# Relays | I2C vs CAN

## Relays
There are a variety of electrical and electronic devices which are classed as Output devices used to control or operate some external physical process. These output devices including the electrical relay are commonly classed as: **Actuators**.
Actuators convert an electrical signal into a corresponding physical quantity such as movement, force, sound etc. An actuator is also classed as a transducer because it changes one type of physical quantity into another and is usually activated or operated by a low voltage command signal. Actuators can be classed as either binary or continuous devices based upon the number of stable states their output has.
For example, a relay is a binary actuator as it has two stable states, either energised and latched or de-energised and unlatched, while a motor is a continuous actuator because it can rotate through a full 360° motion.
![alt text](image.png)

A relay is an electrical switch that allows a low-power signal to control a high-power circuit. It acts like a remote-controlled switch, where a small input (such as from a sensor or microcontroller) can turn on or off a much larger electrical load (like a motor or light bulb).
Relays are used in many applications, including:
- Home automation (smart lights, HVAC systems).
- Automotive systems (starter relays, power windows).
- Industrial machinery (motor controls, safety switches).
- Electronics (protecting circuits, logic operations).

### Basic Principle
A relay has two main parts:
1.	Control Circuit (Primary Side) – A low-power input (e.g., from a switch or sensor) activates the relay.
2.	Load Circuit (Secondary Side) – The relay switches a high-power device (e.g., a motor or lamp).

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


2. Based on Functionality

Type|Description|Example Use
---|---|---
Latching Relay|Stays in its last state even after power is removed.|Elevator buttons, memory circuits.
Time-Delay Relay|Switches after a set delay (e.g., 5 seconds).|Staircase lighting, motor sequencing.
Overload Relay|Protects motors from overheating by cutting power.|Industrial motor controls.


### Why Use Relays?
- Electrical Isolation – Protects sensitive electronics from high voltages.
- Low-Power Control – A small signal (e.g., from an Arduino) can switch a large load (e.g., a 240V AC motor).
- Safety – Reduces risk of electric shock in control circuits.
- Multiple Circuit Control – One relay can switch several devices.
- Digital Compatibility – Works well with microcontrollers (e.g., Raspberry Pi, Arduino).


## Solid-State Relay (SSR)
Instead of mechanical parts, solid-state relays (SSRs) use electronic components (like transistors or TRIACs) to switch the load.

### Basic Principle
- An LED (on the input side) emits light when power is applied.
- A light-sensitive component (like a phototransistor or TRIAC) detects the light and switches the output.
- Since there are no moving parts, SSRs last longer and switch faster than EMRs.
##### Advantages:
- No mechanical wear (longer lifespan).
- Silent operation (no clicking sound).
- Faster switching (good for high-speed applications).
##### Disadvantages:
- Can overheat if not properly cooled.
- More expensive than EMRs for some applications.


## Common Problems & Solutions
1. Back EMF (Voltage Spike)
When a relay turns off, the collapsing magnetic field creates a sudden voltage spike (back EMF), which can damage circuits.
Use a flyback diode (also called a freewheeling diode) across the coil to absorb the spike.
2.  Contact Wear (in EMRs)
Mechanical relays wear out over time due to sparking when contacts open/close.
- Use SSRs for high-speed or long-life applications.
- Choose relays rated for the correct current/voltage.
