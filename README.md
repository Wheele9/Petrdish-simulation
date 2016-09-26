# Simulation of bacterias evolving resistance over time

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/mutant.png)

## Synopsis

I watched this video, where they put a weak bacteria at the edge of a giant petri dish,
after 11 days the bacteria evolved into something which was able to survive the conditions
of high antibiotics density.

## Code Example

petriD = petri(10,4,30)
eColi=bacteria(petriD, 0.2)

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

## Motivation

I created this project for fun, fork it, play with it.You can create your own petri dish, with different size, and a antibiotics dispersion, you can
tune the parameters of the virus, such as lifespan, mutability, starting resistance and see, that in your case it spreads the whole petri dish, or dies once.


