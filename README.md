# os-malloc Homework Lab for Thomas George

myAllocator.c has been modified. It now contains: 
## New methods
* void *nextFitAllocRegion(size_t s)  Searches from the last found usable region. Very similar to firstFitAllocRegion, but this calls findNextFit.
* BlockPrefix_t *findNextFit(size_t s) Searches for block with enough space. Starts at arenaFrame. Once it hits the end of the current arena, it continues from arenaBegin. It finishes when it reaches the address stored in the stopPoint. The first time it finds a useable region, it stores a new stopPoint and returns the prefix pointer.
## Global Variables
* arenaFrame:  Stores address of last checked block. 
* stopPoint:  Stores address of last used block. Substitute stopping point for findNextFit if no suitable block is found.
## Other Changes
resizeRegion checks to see if the region needs to be expanded. It then checks the next region to see if it can grow in place. If so, it adjusts the size of the original region. If necessary, resizeRegion finds a new block and copies the data to the new region using memcpy. 
myAllocatorTest1.c was modified to successfully run testing of this program.

## Special Thanks to:
* Chris Tarango
* Jesus Padilla
* Geoni Griffin
* Ricardo Alvarez and 
* Adrian Veliz

...for their aide with concept clarification, code review, and in general, their help!

