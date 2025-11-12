# Analysis of P, PI and PID Controllers using MATLAB
## Aim:
To analyse the effect of P, PI and PID controllers for the system having open loop transfer function, G(S)=1/(S^2+10S+20) using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
	A controller is a device introduced in the system to modify the error signal and to produce a control signal. 
	The way the controller produces the control signal is called the control action.

Consider the following unity feedback system,
 <img width="823" height="281" alt="image" src="https://github.com/user-attachments/assets/36e49512-cf47-4fec-b00c-f79dc0af1c5f" />

### Proportional (P) Controller:
The proportional controller produces an output, which is proportional to error signal.<br>
u(t)∝e(t) <br>
⇒u(t)=Kpe(t) <br>
Apply Laplace transform on both the sides - <br>
U(s)=KpE(s) <br>
U(s)/E(s)=Kp <br>
Therefore, the transfer function of the proportional controller is Kp.

### Proportional Integral (PI) Controller:
The proportional integral controller produces an output, which is the combination of outputs of the proportional and integral controllers. <br>
u(t)=Kp e(t)+Ki ∫e(t)dt <br>
Apply Laplace transform on both sides - <br>
U(s)=(Kp+Ki/s)E(s) <br>
U(s)/E(s)=Kp+Ki/s <br>
Therefore, the transfer function of proportional integral controller is Kp+Kis. <br>

### Proportional Integral Derivative (PID) Controller:
The proportional integral derivative controller produces an output, which is the combination of the outputs of proportional, integral and derivative controllers. <br>
u(t)=Kp e(t)+Ki ∫e(t)dt+ Kd (de(t)/dt) <br>
Apply Laplace transform on both sides - <br>
U(s)=(Kp+Ki/s+Kds)E(s) <br>
U(s)/E(s)=Kp+Ki/s+Kd s <br>
Therefore, the transfer function of the proportional integral derivative controller is Kp+Ki/s+Kd s

### Characteristics of Kp, Ki and Kd terms:

Increasing the proportional gain ( ) has the effect of proportionally increasing the control signal for the same level of error. The fact that the controller will "push" harder for a given level of error tends to cause the closed-loop system to react more quickly, but also to overshoot more. Another effect of increasing   is that it tends to reduce, but not eliminate, the steady-state error.
The addition of a derivative term to the controller ( ) adds the ability of the controller to "anticipate" error. With derivative control, the control signal can become large if the error begins sloping upward, even while the magnitude of the error is still relatively small. This anticipation tends to add damping to the system, thereby decreasing overshoot. The addition of a derivative term, however, has no effect on the steady-state error.
The addition of an integral term to the controller ( ) tends to help reduce steady-state error. If there is a persistent, steady error, the integrator builds and builds, thereby increasing the control signal and driving the error down. 
 


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the steady state error and analyse the controllers.
## Program: 
### Without Controller (Open loop System)
num=[1]
den=[1 10 20]
sys=tf(num,den)
subplot(2,2,1)
step(sys)
title('open loop system')


### With P-Controller
Kp=300;
c1=pid(Kp)
G1=feedback(c1*sys,1)
subplot(2,2,2)
step(G1)
title('P-CONTROLLER')

### With PI Controller
Kp=30;
Ki=70;
c2=pid(Kp,Ki)
G2=feedback(c2*sys,1)
subplot(2,2,3)
step(G2)
title('Pi-CONTROLLER')

### With PID Controller
Kp=350;
Ki=300;
Kd=50;
c3=pid(Kp,Ki,Kd)
G3=feedback(c3*sys,1)
subplot(2,2,4)
step(G3)
title('Pid-CONTROLLER')

## Output: 
### Without Controller (Open loop System)

<img width="776" height="369" alt="Screenshot 2025-11-12 162404" src="https://github.com/user-attachments/assets/4a941df7-afbe-4b69-8e73-531481c66eeb" />





### With P-Controller

##<img width="775" height="380" alt="Screenshot 2025-11-12 162354" src="https://github.com/user-attachments/assets/f5d2e446-ff80-4049-ae33-e4297e5ec594" />

# With PI Controller

<img width="776" height="400" alt="Screenshot 2025-11-12 162339" src="https://github.com/user-attachments/assets/4f00dbe6-d323-41eb-a3e1-6cd160198f3c" />

### With PID Controller
## R<img width="1023" height="532" alt="Screenshot 2025-11-12 162313" src="https://github.com/user-attachments/assets/d61e0283-69f3-4fca-b715-86f07a3e75df" />

esult:
Thus the P, PI and PID controllers for the given system was analysed and the following conclusions were arrived using MATLAB. <br>
### With-out controller 
Delay time =         <br>
Rise time =             <br>
Peak time =           <br>
Settling time =            <br>
Steady State Error =        <br>
### With P Controller 
Delay time =         <br>
Rise time =             <br>
Peak time =           <br>
Settling time =            <br>
Steady State Error =        <br>
### With PI Controller 
Delay time =         <br>
Rise time =             <br>
Peak time =           <br>
Settling time =            <br>
Steady State Error =        <br>
### With PID Controller 
Delay time =         <br>
Rise time =             <br>
Peak time =           <br>
Settling time =            <br>
Steady State Error =        <br>




