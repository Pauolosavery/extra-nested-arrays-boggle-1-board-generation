## Boggle. Generating the playing field

Read about the game [Boggle](http://en.wikipedia.org/wiki/Boggle). You need to implement it in JS. 

Before all, you should model the first part of the game - the generation. The dices are stacked in a box, the box is shaken, resulting in a playing field. Imagine a 4x4 tray and a button next to it. When this button is pressed, the tray is filled with letters. After that, you can play Boggle. This is roughly what we need to implement.

We are supposed to implement two versions. The first will be simplified, the second - realistic.

### Release 0. The simple version of Boggle.

Create a method `shake()`. It will be responsible for shaking the dices in the box. The method `shake()` should modify the playing field, fill it with random letters in the range `A-Z`.

There are no other restrictions so far. The letters can be repeated. Just put a random letter in each cell. Also, if you've read the rules of the game, you know that `Q` always acts as `Qu` in the game like this. But not the case is different. Let `Q` be just `Q` in this release.

Our application should do the following:

* When the field is created, it should look like this (if you do `console.log(board)`):

  ```JavaScript.
   ____
   ____
   ____
   ____
  ```

* When we shake the box, the box will look like this (if we do `console.log(board)`): 

  ```JavaScript
   DUMV
   KSPD
   HCDA
   ZOHG
  ```

* If we shake the box again, the field will look different. For example:

  ```JavaScript.
   QIRZ
   EEBY
   OEJE
   MHCU
  ```

### Release 1. The clever version of Boggle.

It's time to simulate the dice. Carefully figure out what happens to the dices in the real game while shaking the box. Each dice turns a particular side up, towards the players. You don't have to consider carefully the trajectory of each dice to solve the problem. You have the original field, and you have to get the result that you would get in a real game. You might need to use another array to store all the sides of the dice. Or you could go another way.

A list of some possible combinations where "Q" represents "Qu":

```text
AAEEGN
ELRTTY
AOOTTW
ABBJOO
EHRTVW
CIMOTU
DISTTY
EIOSST
DELRVY
ACHOPS
HIMNQU
EEINSU
EEGHNW
AFFKPS
HLNNRZ
DEILRX
```

### Release 2. Let's deal with ``Q''.

> Q is one of the rarest letters of the Latin alphabet, and its existence in words is only possible due to the presence of the neighbouring letter U. Therefore, when playing Boggle, Q is counted as QU, and the length of the composed word is increased by 1.

> For example: `square` (square) can be composed of only 5 letters: S, Q, A, R, E - although the word length will be evaluated as 6 characters.

Now you need to output `Qu` instead of `Q`. How do you do that? There are many ways. Don't forget how the playing field looks like in reality and how it is represented in the program. They are not always the same.

When you implement the replacement of `Q`, you will have to adjust the output of the field on the screen, because most likely your dice will move because of `Qu`, and this is not very good.

For example, you can output in this format:

```text
U N O T
S E W G
S V L T
L Qu C F
```

## Additional materials

* [Boggle on Wikipedia](http://en.wikipedia.org/wiki/Boggle)
* [Play Boggle online](http://www.wordplays.com/boggle)
