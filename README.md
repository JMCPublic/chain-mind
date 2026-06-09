# Chain Mind: Linear Crossword / Anagram Puzzle Concept

A short explanation for Paul.

## The Core Idea

The puzzle starts like a set of crossword clues. Each clue has a specific answer, usually a single word.

The answer is not the final goal by itself. One or more letters are taken from the solved answers to reveal a hidden word or phrase.

The extra twist is that the clue answers can also form a chain. The last letter of one solved answer can act as the first letter of another solved answer, so the answers can be linked into a sequence.

That gives the solver a second way to make progress:

- solve the clues
- check the answer lengths
- use first and last letters to find the chain
- extract the hidden letters
- reveal the final answer

## Level 1: Simple Extraction

In the simplest version, the answers are already in the order needed.

The solver takes the last letter of each answer and reads the hidden word.

| Answer | Letter Taken |
|---|---|
| Cobb | B |
| Lea | A |
| Bright | T |
| Hoth | H |

Reading the letters in order gives:

```text
B A T H = BATH
```

This is the clean introductory form. It teaches the extraction rule before asking the solver to find the chain order.

## Level 2: The Chain Is Part of the Puzzle

The next step is to give the clues out of order.

The solver still answers the clues, but now they must use the first-letter and last-letter relationship to arrange the solved words into the intended chain.

- If the chain order is given, the puzzle is mostly clue solving plus extraction.
- If the chain order is hidden, the puzzle becomes partly an anagram or ordering puzzle.
- Answer lengths can be supplied as a helpful guide, for example: `3, 4, 4, 6`.

## Indexed Variant: More Flexible Letter Taking

A stronger variant gives each clue answer length and a bracketed letter position.

The number before the brackets is the length of the answer.

The number inside the brackets tells the solver which letter to take from that answer.

For example:

```text
7(3) means a seven-letter answer, take the third letter.
5(1)(5) means a five-letter answer, take both the first and fifth letters.
```

This gives the setter more flexibility. A word can contribute one letter, or occasionally two letters, which helps complete the final answer even when the chain is not perfect.

## Worked Example: PLANETS

Suppose the final answer is:

```text
PLANETS
```

The solved clue answers might be names of planets, fictional planets, or underworld/mythological places.

| Solved Answer | Guide Shown to Solver | Letter Taken | Role in Final Answer |
|---|---:|---|---|
| Neptune | 7(3) | P | 1st letter |
| Caladan | 7(3) | L | 2nd letter |
| Hades | 5(1)(5) | A and S | 3rd and 7th letters |
| Saturn | 6(6) | N | 4th letter |
| Earth | 5(1) | E | 5th letter |
| Hoth | 4(3) | T | 6th letter |

The extracted letters produce:

```text
P L A N E T S = PLANETS
```

In this example, the clue answers themselves also point towards the answer because they are all planet-like or place-like names.

That can help the solver.

For a harder version, the clue answers could come from a completely different field and only the extraction would reveal `PLANETS`.

## What the Solver Might Be Given

The setter can choose how much help to provide.

A gentle version might include the theme and the answer lengths.

A harder version might give only the clues and the bracketed guides.

| Element | What It Does |
|---|---|
| Theme | Helps the solver guess the field of possible answers. |
| Answer length | Confirms whether a clue answer is likely to be right. |
| Bracket position | Shows which letter to extract from the solved answer. |
| Hidden chain | Lets the solver arrange mixed clues by matching end letters to start letters. |
| Double bracket | Allows one answer to contribute two letters. |

## Difficulty Controls

The same basic mechanism can be made easier or harder by changing a few dials.

1. Easy: clues are in order, the theme is given, and each answer contributes one obvious letter.
2. Medium: clues are mixed, but the answers share a visible theme and the lengths are supplied.
3. Hard: the chain order is hidden and the final answer is only revealed by indexed extraction.
4. Very hard: the clue answers are from a different field, so the final answer cannot be guessed by theme alone.

## The Key Rule to Make Clear

Every puzzle should tell the solver how to read the extracted letters.

They might be read in clue order, in chain order, or in another specified order.

The cleanest version is usually chain order, because the solver is rewarded for solving both the clues and the sequence.

In short:

```text
This is a linear crossword/anagram hybrid.
The clues produce words.
The words form a chain.
Selected letters from those words reveal the final answer.
```

## Word Version

There is also a Word document version in this folder:

[Chain Mind Puzzle Concept - for Paul.docx](./Chain%20Mind%20Puzzle%20Concept%20-%20for%20Paul.docx)
