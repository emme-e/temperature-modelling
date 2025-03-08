follow up:
- what has happened until now is we made models for different occasions now we are going to do it so we can input values
- another aspect is too think about the maths that is actually going on.
- we are going to use newtons law of cooling here:
- Newton's law of cooling is a physical law which states that the rate of heat loss of a body is directly proportional to the difference in the temperature
- formula: $\frac{dQ}{dt} = k(T_s -T)$
- where $T_s$ refers to the temperature of the surrouding enviorment (kelvin, K)
- exspanded formula: $T(t) = (T_0 - T_s)e^{-kt}$ 

to take into consideration for later:
- we could also invlove the volume of the cylinder
- do we want to input a bunch of data and then use that to plot a graph? or have a pre-found cooling constant for a bunch of cylinders that is avaliable? and have a choosing system?
- do we want to have a system where we can change the values so can input a value in a certain: farenheight/ celcuis/ kelvin?

now about actually coding:
- need to input different values
- put values into the formula
- graph this
- output time it takes to reach a specfic temperature

- could have it so that input data for a cup in certain condtions and have a bunch of data for this, then it calculates the cooling constant and then can graph this for other scenarios.
- And can also calculate the time it takes for it too reach a specfic scenario. can have it so the code also flows with if statements.
- eg. they input an invalid value (so less than the temp of the enviorment) and it asks for them to input another value in it, rarther than just terminating the program
- could also have it for different liquids... so another factor affectting everything

consideration:
- should it be done such that the first question asked is: choose a temperature scale
- then second question ask:
- enviorment temperature, cooling rate (or have options... can pre-calculate), starting temperature of liquid
- it graphs this
- asks them to input a temperature to find out how long this took
- calcualtes this
- if statement if they input incorrect values


```python
"""
below the code creates a button so the user
can choose which temperature scale they want to work in

i tried inputing different things: a library
for a button and a library for choosing different options.
But i could simply ask them to input.
"""
temp_scale = input("enter the temperature scale you would like to use (K, F or C): ")
```

    enter the temperature scale you would like to use (K, F or C):  K
    




    'K'



so the button i made earlier actually worked it just appeared on my screen instead. thats why my code above wasn't doing anything as it was waiting


```python
"""
Now i need to ask them to input the envrioment temp, 
cooling rate and starting temperature of water
"""
enviorment_temp = float(input("enter the temperature of the enviorment: "))
cooling_rate = float(input("enter the cooling rate: "))
starting_temp = float(input("enter the starting temperature of the water: "))
```

    enter the temperature of the enviorment:  2
    enter the cooling rate:  -0.5
    enter the starting temperature of the water:  90
    


```python
"""
Now i need to create newtons law of cooling formula
- formula: dQ/dt = -k(T_s - T)
- where T_s refers to the temperature of the surrouding enviorment (kelvin, K)
"""
```




    '\nNow i need to create newtons law of cooling formula\n- formula: dQ/dt = -k(T_s - T)\n- where T_s refers to the temperature of the surrouding enviorment (kelvin, K)\n'




```python
below shows the newtons rate of cooling... apparently theres just a function that does this automatically
```


      Cell In[38], line 1
        below shows the newtons rate of cooling... apparently theres just a function that does this automatically
              ^
    SyntaxError: invalid syntax
    



```python
import math

def newtons_law_of_cooling(T0, T_ambient, k, t):
    """
    Calculates the temperature of an object at time t using Newton's Law of Cooling.
    
    Parameters:
    T0 (float): Initial temperature of the object
    T_ambient (float): Ambient temperature (surroundings)
    k (float): Cooling constant
    t (float): Time elapsed
    
    Returns:
    float: Temperature of the object at time t
    """
    return T_ambient + (T0 - T_ambient) * math.exp(-k * t)

# Example usage
initial_temp = 100  # Initial temperature of the object (e.g., degrees Celsius)
ambient_temp = 25   # Surrounding temperature (e.g., degrees Celsius)
cooling_constant = 0.1  # Cooling rate constant
time_elapsed = 10  # Time in minutes

temp_at_t = newtons_law_of_cooling(initial_temp, ambient_temp, cooling_constant, time_elapsed)
print(f"Temperature after {time_elapsed} minutes: {temp_at_t:.2f}°C")
```

    Temperature after 10 minutes: 52.59°C
    


```python

```
