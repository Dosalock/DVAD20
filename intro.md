# Advanced Communcation Networks

## Staff

Jonathan Vestin: Lab assistant

Olga Nadeina: Course Administrator

Andreas Kassler: Examiner

## Course Literature

* No textbook
  No really good textbook about this topic.
* Slides
* Recommended Readings
  Linked on Canvas

## Course Structure

* 14 Lectures
* 2 Practical labs
  * Go through the software with Jonathan to aid with the assigments
  * seems to be about "mininet" pythong smth
* 2 Practical assigments**(Most Important for grade)**
* 1 Theoretical assigment
  * Picking a paper that relates to the course and on the basis of that try to
    summerize it and prepare a presentation with the rest of the class.*maybe check r/programming or some newsletter for something fun to talk about*
* 1 Written final exam
  * Not the big thing in the course more like a quiz, if you do the labs it should be easy.

## Course Grading

* The practical assignments (PA): u, 3, 4
* The theoretical assigntment (TA): u, 3
* The written final exam (FE): u, 3
*  | Grade | Pa #1 | Pa#2 | TA | FE |
  | ------- | ------- | ------ | ---- | ---- |
  | 5     | 4     | 4    | 3  | 3  |
  | 4     | >_ 3  | 4    | 3  | 3  |
  | 3     | 3     | 3    | 3  | 3  |

## Important Dates


| Submission Deadline | Task                                  |
| --------------------- | --------------------------------------- |
| September 29        | Practical assignment #1               |
| Oct 27              | Practical assignment #2               |
| Oct 27              | Theoretical assignment (Presentation) |
| Week 45             | Final Exam                            |

## Practical Assignment

* Execution

  * Individual or pairs
  * Use Ubuntu VM in 21E402 - (just use WSL) Ubuntu 20.2 is the newest possible
* Grading

  * Upload the assigment before the submission deadline
  * Demo assigment for lab assistant (use lab hours)

    * Both students need to attend if its in pairs
* Write a report on the results from the assigment, commentary on the graphs
  most focus on the implementation rather than the report

## Theoretical Assigment

2-3 weeks before you should start, need to read about some SDN (software designed networks)
Sept 23 ish to start then

* Execution

  * Each student selects a paper
    A Lot of topics to explore in datacenter related papers
    Nothing prohibits doing a presentation on the same paper as someone else
  * Email Karl-Johan a copy of the paper accept/declines it
  * Prepare an oral presentation (12-15 minutes **don't take too long**)
  * Template for the presentation on canvas but not necessary to follow
* Grading

  * Presentation of the paper at a seminar in week 44

## Final Exam

* Digital exam (Inspera)
* Three hours
* 30 points
  * 50% correct to pass
* Graded with 'U' or '3'

## Resit Examination

* Practical assigments are graded on exam week

  * need to book a time for a demo with the lab assistant
* Theoretical assigment

  * write a summer of the selected paper
  * send the paper summary to me on exam week
* Final exam

  * will be given three times/year, inc regular exam time

## What is the Course About?

* Data Center Networks
  * Not that much of a focus on this in the course
  * Most data center builders like to keep things secret
* Software-defined NetworksMost focus on this in the course, the practical assigments will revolve around this
  * Breaks out the OS from the router and centralizes it
  * Controller machine and programmable switches instead of every router deciding for themselves with their OS
  * split the networking business like PCs where the hardware is mostly the same but the software drives it in different ways.
* Network Functions Virtualization
  * No labs on this but will go through in the course
  * Lots of new NFV in the last 10-15 years brought up with vmware
  * A good way of running many "machines" on the same hardware
  * It was seen that the utilization of most machine was not more than 10%, virtualization helped up this usage
  * Instead of physical machines swapped for COTS (Commin of the Shelf) devices
    * Making things like hardware firewalls instead be a software implementation
    * Makes things more dynamic, you can relocate resources to places that need it. ex. many people @ football game
  * Usually in networks there are a mix of the traditional hardware solutions and these NFVs
  * You loose a tiny bit of performance with these NFVs so if you need performance above all else you go hardware
