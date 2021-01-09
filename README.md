# What is this?
• This is a resource repository storing trivia data for [Adam-Bot.](https://github.com/adampy/gcsediscordbot) All questions from all topics are stored here.
# How do I create a quiz?
• If you want to create a quiz, your .csv file must implement the following format.
`Question,Answer1,Answer2,Answer3,...,AnswerN`

• When there is a maximum of ***n*** answers, other questions ***must*** account for ***n*** answers and implement empty answers. If you make this spreadsheet in Excel, it does this automatically once you save as a .csv file. For example:
```csv
Circumference of a circle = ?,2pir,pid,pi*d,2*pi*r,(2pi)r,(pi)d
p(A or B) = ?,A+B,A + B,,,,
```

• You can have as many answers as you'd like, but Adam-Bot performs the `.lower()` function on both the answer and the user input, so you do not need to worry about having multiple answers for every possible case.

# Architecture
• Adam-Bot, running on Heroku, contians a list of all trivia names and sends HTTP requests to those raw csv files. Upon retreiving these in plaintext, it uses the `csv` module to parse it. When using the bot, `-trivia list` can be performed to see what trivias are available. If this file is updated, then Adam-Bot needs to be restarted or the `-trivia reload` command needs to be run.
