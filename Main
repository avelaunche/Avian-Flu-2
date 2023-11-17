#required packages
import random
import matplotlib.pyplot as mpl

#variables

#time unit
dt = 0.1
#population to exposed odds
beta1 = 0.5
#exposed to infected odds
gamma1 = 0.5
#infected to recovered odds
sigma1 = 0.5
#population to exposed odds
beta2 = 0.5
#exposed to infected odds
gamma2 = 0.5
#infected to recovered odds
sigma2 = 0.5
#population number
population = 1000
#number of time units passed
time = 100

#lists to record organism status
population_list = []
exposed_list1 = []
infected_list1 = []
recovered_list1 = []

#lists to record number of organisms in each container
population_number = []
exposed_number1 = []
infected_number1 = []
recovered_number1 = []

#lists to record organism status
exposed_list2 = []
infected_list2 = []
recovered_list2 = []

#lists to record number of organisms in each container
exposed_number2 = []
infected_number2 = []
recovered_number2 = []

#fills each container with the numbers they start with. All animals start uninfected
for x in range(population):
  population_list.append(1)
  exposed_list1.append(0)
  infected_list1.append(0)
  recovered_list1.append(0)
  exposed_list2.append(0)
  infected_list2.append(0)
  recovered_list2.append(0)

#runs the code for length(time)
for x in range(time):

  #runs through all of organisms in uninfected population
  for y in range(len(population_list)):
    #if they meet the following condition they are moved into exposed 
    if random.random() < beta1*dt and population_list[y] == 1:
      population_list[y] = 0
      exposed_list1[y] = 1
    #if they meet the following condition they are moved into exposed 
    if random.random() < beta2*dt and population_list[y] == 1:
      population_list[y] = 0
      exposed_list2[y] = 1

  #runs through all of organisms in uninfected population
  for y in range(len(exposed_list1)):
    #if they meet the following condition they are moved into exposed 
    if random.random() < gamma1*dt and exposed_list1[y] == 1:
      exposed_list1[y] = 0
      infected_list1[y] = 1
    #if they meet the following condition they are moved into exposed 
    if random.random() < gamma2*dt and exposed_list2[y] == 1:
      exposed_list2[y] = 0
      infected_list2[y] = 1
    

  #runs through all of organisms in uninfected population
  for y in range(len(infected_list1)):
    #if they meet the following condition they are moved into exposed 
    if random.random() < sigma1*dt and infected_list1[y] == 1:
      infected_list1[y] = 0
      recovered_list1[y] = 1
    #if they meet the following condition they are moved into exposed 
    if random.random() < sigma1*dt and infected_list1[y] == 1:
      infected_list1[y] = 0
      recovered_list1[y] = 1
  
  #records number of organisms in each container
  population_number.append(sum(population_list))
  exposed_number1.append(sum(exposed_list1))
  infected_number1.append(sum(infected_list1))
  recovered_number1.append(sum(recovered_list1))
  exposed_number2.append(sum(exposed_list2))
  infected_number2.append(sum(infected_list2))
  recovered_number2.append(sum(recovered_list2))

#creates a list of length time from 0-time
time_passed = range(time)


mpl.plot(time_passed, population_number, label = "susceptible")
mpl.plot(time_passed, exposed_number1, label = "exposed")
mpl.plot(time_passed, infected_number1, label = "infected")
mpl.plot(time_passed, recovered_number1, label = "recovered")
mpl.plot(time_passed, exposed_number2, label = "exposed")
mpl.plot(time_passed, infected_number2, label = "infected")
mpl.plot(time_passed, recovered_number2, label = "recovered")

mpl.legend()
mpl.show()
