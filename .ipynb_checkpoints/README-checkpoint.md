# Cheating Codenames
## Idea:
Having spoken English for only 5 years, I have had some struggles playing the Codenames board game (aka 99% of all the games were lost). Since we are in the global pandemic and board game nights became the new date nights for my partner and I, I have decided to create a helper to assist me in winning this game more often.
For this project I am using the original version of Codenames.

- Data: the photos were either taken on my phone from the personal game set or found on Google for a high resolution no-noise photos.

The following code can be found in the 'final.ipynb' file.
### Board of Words:
1. Using a photo taken on the phone:
    - PyTesseract cannot read these files in order if the tiles are slightly misalligned;
    - The light glares result in the pixels being not black and therefore some words disappear after noise cleaning;
    - The background shows up in the back.
    
2. Using a high resolution photo taken from Google:
    - The noise cleaning result in a clean output of white background and black words;
    - PyTesseract was able to read all the information with no issues;
    - After receiving the output string from the PyTesseract I used quick string formatting to get the resulting array of words.
    
    
### Grid recognition:
1. Present:
    - The user gets a field for every row and has to manually input the values for each grid cell, ie, blue, red, red, blue, blue.
  
2. Future:
    - Using openCV: use the matchTemplate function to be able to identify the each cell on the grid and find their locations. Hence, create an array of the grid cells (these methods are in the "grid attempts.ipynb");
    - Using relative distances: create a method that will identify the border of each grid. Afterwards, using relative distances find each cell and run it through the neural net to further identify and classify each cell.
    
    
### Word vectors:
1. The user can input the number of words they want to combine;
2. The program using count permutations finds all possible combinations;
3. Using Word2Vec model the program finds the clue and filters out the bad ones based on the cosine similarity;
4. Outputs the final combinations that have not been filtered and the clues for them.

## Results:
- These are all biased on each person but in my opinion there have been some proper results, some disappointing results and a couple great results.
- Example for the latter: the word SHRDLU for the combination of "skyscraper" and "robot".