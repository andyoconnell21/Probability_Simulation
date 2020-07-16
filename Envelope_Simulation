###############################################################################
## Semester:         CS 540 Spring 202
##
## This File:        envelope_sim.py
## Author:           Andy O'Connell
## Email:            ajoconnell2@wisc.edu
## CS Login:         o-connell
##
###############################################################################
##                   fully acknowledge and credit all sources of help,
##                   other than Instructors and TAs.
##
## Persons:          N/A
##
## Online sources:   Lecture Notes and Piazza
##
###############################################################################

import math
from random import randint

def pick_envelope(switch, verbose):
    envelope_picked = 0
    ball_picked = 0
    #Envelopes are assigned with a random color of balls
    var = randint(0,1)
    if var == 0:
        envelope0 = 'b,b'
        envelope1 = 'r,b'
        if verbose:
            print("Envelope 0:", envelope0[0], envelope0[2])
            print("Envelope 1:", envelope1[0], envelope1[2])
    else:
        envelope0 = 'r,b'
        envelope1 = 'b,b'
        if verbose:
            print("Envelope 0:", envelope0[0], envelope0[2])
            print("Envelope 1:", envelope1[0], envelope1[2])

    #Randomly selects on envelope
    var = randint(0,1)
    if var == 0:
        envelope_picked = envelope0
        if verbose:
            print("I picked envelope 0")
    else:
        envelope_picked = envelope1
        if verbose:
            print("I picked envelope 1")

    #Randomly selects one ball from the envelope
    var = randint(0,1)
    if var == 0:
        ball_picked = envelope_picked[0]
    else:
        ball_picked = envelope_picked[2]
    
    #If red, the right envelope is picked and TrueSpecify OOV @ end is returned
    #If black, switch or don't switch according to value
    if ball_picked == 'r':
        if verbose:
            print("and drew a", ball_picked)
        return True
    if ball_picked == 'b':
        if verbose:
            print("and drew a", ball_picked)
        #This will switch the envelopes if switch is True
        if switch == True:
            if(envelope_picked == envelope0):
                envelope_picked = envelope1
                if envelope_picked[0] == 'r' or envelope_picked[2] == 'r':
                    return True
                else:
                    return False
            else:
                envelope_picked = envelope0
                if envelope_picked[0] == 'r' or envelope_picked[2] == 'r':
                    return True
                else:
                    return False
        else:
            if envelope_picked[0] == 'r' or envelope_picked[2] == 'r':
                    return True
            else:
                return False
                

def run_simulation(n):
    #Counter variables
    count_true_switch = 0
    count_true_no_switch = 0
    switch_succ = 0
    no_switch_succ = 0

    #Simulation for switching envelopes
    for x in range(n):
        val = pick_envelope(True, verbose=False)
        if val == True:
            count_true_switch += 1

    #Simulation for not switching envelopes
    for x in range(n):
        val = pick_envelope(False, verbose=False)
        if val == True:
            count_true_no_switch += 1

    #Computes a percentage from the total n
    switch_succ = count_true_switch / n
    no_switch_succ = count_true_no_switch / n

    print("After", n , "simulations:")
    print("  Switch successful:",'{:.2%}'.format(switch_succ))
    print("  No-switch successful:",'{:.2%}'.format(no_switch_succ))


