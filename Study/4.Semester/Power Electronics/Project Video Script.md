**Slide 1**
Hello. My name is Andreas. I will give a short presentation about my power electronics project. 

**Slide 2**
For my project i choose a paper titled "A Novel Topology of Nonisolated DC-DC High Step up Converters for Solar PV Power Plants".

The paper was written by these three gentemen, and was published i the Journal of Integrated Circuits and Systems in 2022. 

**Slide 3**
The circuit in question is shown high. The circuit is fairly simple and features a low number of components. 5 Capacitors, 3 Inductors, 3 Diodes and only 1 switching device which in this case is a N-type MOSFET.

The converter is nonisolated as the grounds of the input and output are coupled together. There are several advantages of a nonisolated design, mainly being the omittance of a transformer to boost the voltage. Transformers are bulky, expensive and introduce unavoidable losses due to leakage inductance. 

The converter features high voltage gain and due to there only being one switching device, the PWM control system can be made extremely simple. 

**Slide 4**
We will now shortly look a how the converter operates. For the sake of everyone we will skip the math as that is in the submitted paper anyway.

**Slide 5**
In switchmode #1 the Vgs of the MOSFET is high, turning it on. In this state all diodes are off and inductors are charged. Capacitors C3, C4 and Co are discharged while C1 and C2 are charged. 

**Slide 6**
In switchmode #2 the Vgs of the MOSFET is low, turning it off. In this state all diodes are on and conducting. The inductors are discharged. Capacitors C3, C4 and Co are charged while C1 and C2 are discharged. 

**Slide 7**
With the basic overview of the converter finished we now arrive to the simulation. Simulink was used to simulate the circuit. All circuit parameters are shown on the left. We used the exact same parameters as in the paper. 

**Slide 8**
To the left we see the output voltage waveforms from the simulation. We got 333V on the output with a low ripple of only about 0.1V. 

**Slide 9**
Our own results differ about 10% from the results in the paper. The output voltage waveform from the paper is shown on the left. We see they got a voltage of 370V and approximately the same ripple of 0.1V. 

In the paper an expression for the voltage gain capital M was derived with ideal component approximations. According to this approximations we should see 400V on the output. Due to losses we see less than that.

**Slide 10**
It can be hard to approximate output voltage in converter such as this as shown before. Even if a voltage gain expression was derived where diode voltage drops and MOSFET Rds-on was considered, parasitic capacitance and inductance would still introduce unexptected losses in the real world due to the switching nature of the converter. 

To fix this we went further than the original paper and implemented negative feedback and actively adjusted the duty cycle with a PID controller. This way output voltage is extraordinarely easy to adjust, and the output voltage should be stable even if load resistance is dynamically changing (to a certain degree).

To the right we see a simple block diagram of a PID controller. A reference input is subtracted with the output voltage from the converter which in this diagram is denoted Plant. The pid controller then consists of three blocks; a proportional, integral and derivative part, that are all summed together. 

**Slide 11**
On the right we see the circuit as implemented in Simulink. We input a reference voltage of 370V which is our desired output. The output voltage of the converters is subtracted from this and fed directly to the PID controller. The output of the PID controller is summed with a default duty cycle arbitrarily set to 0.3. This ensured the circuit starts at a reasonable duty cycle. A saturation block then ensures the duty cycle goes no lower than 0.2 and no higher than 0.8. The converter demonstrated unpredicable unstability if the duty cycle when higher or lower than that. 

The PID were hand tuned, and the values for Kp and Ki are shown on the left. The derivative term turned out to be quite finnicky, and a value of zero which effectily makes it only a PI controller worked best. 

**Slide 12**
From the results of the simulation we see that we got a very stable output voltage of exactly 370V. The voltage ripple were neither better nor worse. We see that it takes approxiamtely 0.6 seconds for the output voltage to stabilize at the reference voltage. For some applications  this could perhaps pose a problem, but we're quite satisfied with it and determined that its not a problem. 

The main disadvantage we see from using a control system such as this is the massive amount of overshoot of about 20%. Before the voltage starts to settle it reaches nearly 440V. This means that component voltage ratings need to be carefully considered if a real life implmentation is pursued. 

Further tuning of the PID controller and/or the feedback could maybe solve this problem, but we were unable to get better results than these.

**Slide 13**
From the simulation with the PID controller we also measured input current. We see that on average the voltage source inputs 34.6 amps of current.

From the input current we determined the efficiency of the circuit to be 79%. This is not too bad, but a LOT lower than expected and lower than the results from the reference paper. The lower efficiency is also reflected when we got a lower output voltage than expected. Where exactly these losses occur we're not sure.

**Slide 14**
The converter features high voltage gain as promised and was easy to implement. There are some clear advantages due to it being transformerless, having a low amount of components, only one switching element etc. We got reasonably good results from our simulations but they still differed from the resulsts in the reference paper. The implementation of the active control system was a succes and made the output easy to adjust, but also introduced considerable voltage overshoot. From our results we saw a low but still ok efficiency. 
