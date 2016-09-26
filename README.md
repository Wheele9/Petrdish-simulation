# Simulation of bacterias evolving resistance over time

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/mutant.png)

## Synopsis

I watched this video, where they put a weak bacteria at the edge of a giant petri dish,
after 11 days the bacteria evolved into something which was able to survive the conditions
of high antibiotics density.

## API usage
```python
petriD = petri(10,4,30)
eColi=bacteria(petriD, 0.2)
```
You can create a petri dish, by giving its sectorlength, sectornumber, and width, the total 
length will be sectorlength*length.
You instantiate a virus, by giving him a petri dish, and a starting resistance.

```python
simulStep=500

for i in range(simulStep):
   
    eColi.evolve()
    eColi.spread()
    eColi.age()
```

You run the simulation, by calling evolve(), spread(), and age() methods, after each step you can watch the current state of the simulation
```python
eColi.showBacMap()
```

You can see the resistance values in the petriDish
```python
eColi.showAgeMap(pretty=False)
```

You can see the age distribution between the cells
```python
eColi.saveVideo()
```

You can save a video about your experiment.

## Example
```python
petriD = petri(10,4,30)
eColi=bacteria(petriD, 0.2)
```

I created a petri dish and a bacteria. After 3 simulation steps, the bacteria started to spread

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/startstospread.png)

After 50 steps, a new mutant apperad, which was strong enough to spread in the new, hader environment.

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/mutant2.png)

After couple of hundred steps, the bacteria reached the 4th sector.

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/blu4sec.png)

After about 1000 steps, the simulation finished, all the bacteria died, they were unable to break
into the final cell with theese starting conditions this time.

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/4secdeath.png)

Other times the virus spreads totally

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/fullresistance.png)

You can see the ageMap, which indicates the routes of spreading

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/full
.png)

## Motivation

I created this project for fun, fork it, play with it.You can create your own petri dish, with different size, and a antibiotics dispersion, you can
tune the parameters of the virus, such as lifespan, mutability, starting resistance and see, that in your case it spreads the whole petri dish, or dies once.


