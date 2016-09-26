# Simulation of bacterias evolving resistance over time

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/2mutant.png)

## Summary

I watched this video, where they put a weak bacteria at the edge of a giant petri dish,
after 11 days the bacteria evolved into something which was able to survive the conditions
of high antibiotics density.

## API
```python
petriDish = makePetriDish(10,4,30)
eColi=bacteria(petriDish, 0.2)
```
You can create a petri dish, by giving its sectorlength, sectornumber, and width, the total 
length will be sectorlength*length. In this case there will be 4 sectors, each of them 10 cells wide. The first sector's drug density will be 0, the i-th sector's 10**i. In this case the densitys in order will be: 0,1,10,100.The width of the dish will be 30 cells. 
The eColi instantiation will live in this pool, and its starting resistance will be 0.2 . So it will spread easily in the first sector, but it has to evolve quiet a bit of resistance to break into the next one!


```python
simulStep=500

for i in range(simulStep):
   
    eColi.evolve()
    eColi.spread()
    eColi.age()
```

You run the simulation, by calling evolve(), spread(), and age() methods, after each step you can watch the current state of the simulation.
```python
eColi.showBacMap()
```

You can see the resistance values in the petriDish.
```python
eColi.showAgeMap(pretty=False)
```

You can see the age distribution between the cells.
```python
eColi.saveVideo()
```

You can save a video about your experiment if you have ffmpeg installed.

## Example
```python
petriD = petri(10,4,30)
eColi=bacteria(petriD, 0.2)
```

I created a petri dish and a bacteria. After 3 simulation steps, the bacteria started to spread

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/resol.png)

After 50 steps, a new mutant apperad, which was strong enough to spread in the new, harder environment.

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/mutant2.png)

After couple of hundred steps, the bacteria reached the 4th sector.

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/blu4sec.png)

After about 1000 steps, the simulation finished, all the bacteria died, they were unable to break
into the final cell with theese starting conditions this time.

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/4secdeath.png)

Other times the virus spreads totally

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/fullresistance.png)

You can see the ageMap, which indicates the routes of spreading

![alt tag](https://github.com/Wheele9/Petrdish-simulation/blob/master/images/full.png)

## Usage

You can download this simulation, and open it in ipython. click through the  steps, and see the results. If you dont know have python, or ipython installed the easiest way to get it through
https://www.continuum.io/downloads . I suggest python3.
Navigate to the repostiory folder, open a comand window/shell and type:


```
ipython notebook
```

Select the petrydish.ipynb and you are ready to go. If you have any question, feel free to contact me.


## Motivation

I created this project for fun, fork it, play with it.You can create your own petri dish, with different size, and a antibiotics dispersion, you can
tune the parameters of the virus, such as lifespan, mutability, starting resistance and see, that in your case it spreads the whole petri dish, or dies once.


