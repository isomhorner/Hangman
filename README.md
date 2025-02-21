#so, start from beginning, this is what happens:
#1.
#you imported random so that you can do the random.choice

#2. Next, you see all the ACSII (sp?) art, where each hangman stage is stored as an item
	##in the 'stages' List
	#2a. you also have another List, word_list, that shows the animals that'll be randomly chosen

#3. Next, you create a 'lives' variable equal to 6, to number of lives for your hangman stages

#4. Here's where you are creating that chosen_word variable, to generate a random word from the 	#animals List using random.choise

#5. Next, you want to show the user the # of letters in their mystery word... with an underscore/blank: _
    #5a To do this, you create a blank variable called placeholder.
    #5b. then you do FOR LOOP to carry the loop out for the # character length (len()) of the chosen_word
    #5c. each time it runs, it adds a _ to the placeholder variable


#6. You create a boolean variable, where it's default is = False
    #6a. So as the game_over is equalled to False, the game isn't over yet
    #6a. We need this for the while loop, so that it goes as the game is still in play

#7. You need to store the correct answer(s) of the user. Otherwise, they're going to keep guessing, and their previous
        ##guess will disappear. They need to be stored... as a List
    #7a. You create a list called correct_letters, and it's blank with []
    #7b. This is also created in its own block, so that it's accumulating as the loops are taking place.        #and it isn't being wiped clean after each round of the loops



#8: the user guesses start, here. you use a while loop to ask the user "guess a letter" for as many times
    #as it takes until the game_over is True (aka while not game_over)
    #8b. here, you create the guess variable, to capture the answers of the user... what is their letter guess?
        #8i. it also adds a .lower() to be sure that it lowercases their answer, since the animals are in lowercase

#9. now you create the Display variable, and it's empty. it's going to be used to build and keep track of
    #where _s are, and where a correct letter is
    #9a. This occurs inside the block since it's totally dependent on the happenings of the for loop


#10 so, now we get into a FOR LOOP, where the magic happens
    #10. for each letter in the randomly chosen word:
        #10. if that letter matches what was guessed: then that letter will be added to the display in that position
            #10a. if that letter matches what was guessed: it will also be stored in that correct_letters list
                #that we made earlier... the .append means that each loop is allowed to add another letter to the list
        #10i. this elif is very important, here
            #10ia. if there wasn't here, that correct_letters.append wouldn't do shit
            #10ib. with this "elif letter in correct_letters: display += letter" ... if on a previous run of the while
                #loop, was a letter already guessed to be correct?
                ##... then, it needs to still be added to the list of correct_letters *and* the new display, too.
            #10ic. so now, whenever we check our letters and we want to fill in the other previous letters in the 
#               # 'display' variable, the elif statement will ask if there's a letter already saved in the 
                #correct_letters List, and if so, it'll show up in the new Display for each loop until it's all
                #filled up and... the Game Over step will happen
        #10ii. if that letter does NOT match: then a _ will be added to the display in that position


#11. We need to account for the times where the user makes an incorrect guess, and loses a life,
	#and the appropriate hangman picture comes up
	#11a. Here, we say "if the guess isn't in the randomly chosen word, then lives goes down 1
		#and a new "life" count is saved... and then the new 'lives' # will be the index
		#of the hangman picture that'll come up from the stages List

#12. Now we're getting into the Game Over parts. this one says that when lives is down to 0, then
	#game over is true (aka it's Game Over), and the You Lose message gets printed

#11this is where the game finally ends. This says that, in its own block, that if there isn't a _, then
    #that means that there are no more remaining letters to be guessed
   #11a. This means that the user has guessed all the letters, and they won, and game is over
   #11b. So, there. if _ isn't in the display, then game_over switches to True, and the while loop is done
