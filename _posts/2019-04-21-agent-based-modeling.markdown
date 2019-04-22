---
published: false
---
## Agent based model

A complex system unlike physical systems can't be represented using equations. Natural phenomena such as in biomedical or social interactions each consist of enormous numbers of entities that interact nonlinearly with each other and with the surrounding environment. This interaction forms an emergent behavior of the system, also each entity capable to adapt its individual behavior which consequently affects the whole behavior of the system.


## Example

Bellow is a NetLogo model to simulate ants searching for food. Ants move either right and left in a predefined angle, then move forward in predefined step size. We can specify the size of the population. Ants move on a world colored as brown(ground) and the food colored as green(grass). Ants return to the nest once they get food, the next is located at the center of the world and colored orange. Ants communicate by pheromone trail to guide each other into the food sources. The amount of pheromone gets reduced according to a predefined probability each Monte Carlo step (tick).

![](http://g.recordit.co/HK4tmfS8I3.gif)

```
;; this model shows the behavior of ants while eatiing grass, while eating ants produce phermone
;; to guide other ants to the food
;; ants return to the nest after picking up the food
;; phermone evaporates within time
;; user can specify the following:
;; population size

turtles-own [food-eaten return-to-nest?]  ;; variables of turtles
patches-own [nest? phermone]              ;; variables of patches

to setup
;; prepare the world and reset ticks
clear-all
reset-ticks
;; the population is a group of ants placed on the world at the center by default
create-turtles population
ask patches [
   set pcolor brown  ;; by default the patches are black
  ]
ask turtles[
  set color black ;;
  set shape "bug" ;; the agent of bug shape to represent an ant
  set size 1.5
  set food-eaten 0  ;; each ant has food variable
  ]
  ;; set up the food by setting green patches
  set-food
  set-nest
end

to go
if not any? patches with [pcolor = green] [stop] ;; stop the simulation when no food ends
ask turtles[ ;; ants either eat or return to the nest after eating
 ifelse return-to-nest? = true
  [return-to-nest]
  [food-search]
 ]
  evaporate-phermone ;; permone get reduced based on a user-defined probability
  tick
end

to food-search
  let phermone-ahead? scent-at-angle 0
  let phermone-right? scent-at-angle 45
  let phermone-left? scent-at-angle -45
  ifelse phermone-right? > phermone-ahead? or phermone-left? > phermone-ahead?
  [ifelse phermone-right? > phermone-left?
    [rt 45]
    [lt 45]
  ]
  [fd 1 ]
  ifelse flip-coin? = true [rt random max-turn-angle] [lt random max-turn-angle]
  fd random max-step-size
  if pcolor = green
   [
    set food-eaten (food-eaten + 1)
    set pcolor brown
    ;; ant should return to nest after launch
    set return-to-nest? true
    ]
end

;; ants should resturn to the nest after they get their food, this process is controlled using 
;; the variable return-to-nest? 
to return-to-nest
  face patch 0 0 fd 1
  set phermone (phermone + 1)
  set plabel phermone
  ;; when ants reach the nest, they can start searching for food again
  if pcolor = orange[ 
    set return-to-nest? false]
end

;; phermone gets down each tick, this reduction depends on a probability defined by the user
to evaporate-phermone
 let x random-float 1 ;; random between 0,1
  ask patches with [phermone > 0]
  [
   if x > probability-to-vaporate
    [set phermone (phermone - 1)]
    set plabel phermone
  ]
end

;; setup the nest, in the position 0 0, an orange square of size <2
to set-nest
  ask patches[
  set nest? distancexy 0 0 < 2 ;; variable nest? will be true in patches that closed to the center
  if nest? = true [set pcolor orange]
  ]
end

;; food is distributed in to three green chunks (grass) 
to set-food
  ask patches
  [
  if distancexy (0.6 * max-pxcor) 0 < 5
    [set pcolor green]

  if distancexy (-0.6 * max-pxcor)(-0.6 * max-pycor) < 5
    [set pcolor green]

  if distancexy (-0.6 * max-pxcor)(0.6 * max-pycor) < 5
    [set pcolor green]
  ]
end

;; report flip-coin?, a random variable to determine the direction of ant move (right/left)
to-report flip-coin?
  report random 2 = 0
end

;; report scent-at-angle, ants smell phermone in front, right, or left. this report returns the amont of phermone
;; in the given angle
to-report scent-at-angle [angle]
let p patch-right-and-ahead angle 1  ;; look at angle with a 1 patch from the current patch of the agent
if p = nobody
  [report 0]
  report [phermone] of p
end
```
