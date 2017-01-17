# Outline of first day's lecture, "Data Science in the Humanities."

## I. Overview of the humanities and data science.

### What is data science?

![data science Venn diagram, by Drew Conway](https://static1.squarespace.com/static/5150aec6e4b0e340ec52710a/t/51525c33e4b0b3e0d10f77ab/1364352052403/Data_Science_VD.png)

Drew Conway's Venn diagram is very influential, and not at all a bad place to start! But we can get a little beyond that, if we rely on [David Donoho's 2015 article "50 Years of Data Science."](http://courses.csail.mit.edu/18.337/2015/docs/50YearsDataScience.pdf) Data science is not just statistics + hacking + domain knowledge. It's more specifically related to a shift in data analysis that flows

1. From John Tukey's 1962 intervention, which moved statistics in the direction of science rather than math, and
2. From the later rise of a "predictive culture" in data analysis, associated with machine learning.

We'll talk about both of those things later in more detail, but for right now, the important takeaway is just that there are *principled changes in the logic of data analysis* that have *caused* it to fuse more deeply with computer science and domain knowledge.

### What are the humanities?

That's actually a harder question, because the line between "humanities" and "social sciences" is blurry and contested. All these fields study human behavior and human experience. And social scientists can do qualitative interpretation as well as quantitative data analysis. But, generally, the fields we call the humanities have differed from social sciences

1. Because they care about the subtleties of expressive forms (art, music, literature) that are hard to generalize about, and also,
2. Because they're interested in understanding the *historical particularity* of human expression rather than deducing universal laws of human behavior.

### What can data science achieve in the humanities, and why should we care?

Part of the reason people are excited about data science is that the new approach to analysis Donoho calls "the predictive culture" is able to grapple with things we never used to call "data" at all. We don't have to start with nice structured datasets (i.e., tables where each column represents a variable with a clear definition). We can start with anything. Tweets, novels, songs, emojis. We'll talk later about how that became possible, but right now I just want to say, that's going to be an enormous change for the humanities. Quantitative analysis is becoming useful for us; it can start to grapple with subtleties that used to elude it.

We're discovering things like, a massive shift in the history of the novel, away from emotion and moral judgment, and toward concrete description. We're discovering new ways of thinking about character -- ways of mapping assumptions about gender, for instance, and measuring the way those assumptions change over time.

All of this could matter for you if you work with humanistic material as a researcher or librarian, but these same techniques of analysis also matter outside the university. That's why I began with a blog post from Instagram!

And it's a two-way street; it's important to realize that the humanities also have things to teach data analysts about interpreting human expression. For instance, I mentioned that humanists care about historical particularity. That's can be important even if you're interested mainly in the present. When data analysis gets overconfident, and goes wrong, it often goes wrong by misinterpreting a local particularity as a general pattern. Algorithms by themselves aren't going to save us from making that mistake. So we have to learn a more holistic approach, where we're always thinking about the sources of our data and the limits of our interpretation. That matters even in the private sector.

### What is data, anyway?

I gave you an optional link to Daniel Rosenberg's article about the history of the concept of data. Basically the key is is that the word comes from the Latin for "something given," and was used initially to describe the assumptions that we take as starting points for reasoning. This is why people often talk about "raw data." The idea has always been that data are things *prior* to interpretation. They are the things you start with. Before you have a theory, or a hypothesis; before you even have a "fact," you have a bunch of undigested data.

That's the idea; that's the notion. But of course in reality, we need to remember to question the assumption that data precede interpretation. If we have data, it means someone has chosen what to measure, and if that choice is itself shaped by blind spots or biases, then the data will have blind spots and biases.

## II. Preparing for hands-on coding work.

It's going to be I think one-third lecture, two-thirds hands-on exploration. And to do the hands-on exploration you'll need to learn how to write code in Python. I'm not assuming that you come in with prior experience in Python. We'll start from the basics. But I have to admit, we'll move pretty quickly.

1. Make sure everyone is able to install Anaconda.
2. Create a course folder, with subfolders for code, data, and results.
3. Django Girls' command line tutorial.
4. Navigate to your course folder.
5. Say "spyder."
6. This is an interactive Python *console.*

## III. Interactive exploration of data types on Spyder.

### Variables and data types.

From a 30,000-foot perspective, data analysis is very simple.

1. You put data in containers.
2. You manipulate the containers.

Obviously, there's a bit more to it than that, but it makes sense to start by thinking about the kinds of "containers" we have available.

We'll call these variables. In Python, when you use an equals sign, you are evaluating whatever is on the right side, and putting it in the container on the left.

For instance

 x = 4 + 1

If you look here in the upper right-hand corner, at variable explorer, you'll see that X now contains 5. Now let's say other_variable = x. See what happens.

Variable naming conventions.

Variables come in several *data types.* Let's start by looking at some of the primitive types.

1. Integer
2. Float
3. Boolean
4. String

Create a float. Compare two numeric variables. Assign the result of an expression to a Boolean variable.

What about words? To represent alphabetic information, we need a "string."

sentence = "Here are 4 words."

A string is a sequence of characters, and we can easily *slice* parts of the sequence. Say 
sentence[0:4]
Now say
sentence[4: ]
now sentence[-6: ]

four = sentence[9:10]
now try
four > 3
You get an error, because the string '4' is not the same thing as the integer 4.

However, we can do certain kinds of math with strings:
sayhi = 'hello' + ' ' + 'world'

Since strengths are a sequence, they have a len().
when we writen len() we're making a function call.
Sentence is the *argument* that we're passing to len().
What happens if we provide no argument?

Here's another function. Suppose we wanted to know the numeric value of
our string 'four.' You can say
four = int(four)
Now it's an integer!

### Collections.

But Python wouldn't be very useful if we had to handle every single piece of data separately. We need a way of managing *collections* of data.

A list is a sequence, just like a string is a sequence of characters.
firstlist = [3,2,0,8,3]
lists have a length, and you can slice them just like strings.

what if we want to add something to a list?

firstlist.append(7)

This is a very important syntactic pattern. It's like a function call, but this is a special sort of function that belongs to the variable "firstlist." We call it a method. In this case it's a list method; a method that belongs to every list.

What happens if we mistype?
firstlist.append[7]

Here's another method:
firstlist.sort()

Notice that we don't have to *reassign* firstlist when we call these methods. We don't have to say firstlist = firstlist.append(0)
In fact that won't work.
Instead we can change the list in place by appending or sorting. That's because lists are mutable. You can change them.

Strings aren't mutable. You can't append something to a string; you have to create a new string that is, for instance, 'hello' + ' ' + 'world'

If you don't need order, you can use a set instead of a list

set = set(firstlist)

One of the most powerful collection types is a dictionary. Let's create one.
noveldates = dict()
noveldates['Mrs Dalloway'] = 1925
noveldates['Moby Dick'] = 1851

if we know the key, we can retrieve the value
notice what happens if we give a key that doesn't exist

### Review

So, review: we've covered four primitive data types, and three collections.
We've also covered syntactic concepts.
An *expression* gets evaluated to a value.
A *variable assignment* puts the value on the right side of = into a variable on the left.
We also learned about functions, and methods.

### First program

Let's write a simple program that counts words.
First let's clear the variable space with %reset.

sentence = input('Enter a sentence: ')
words = sentence.split(' ')
sentence_length = len(words)
print('That had ' + str(sentence_length) + ' words.')

We can run this in spyder, and we'll see the values of the variables.
Then we can interact with the variables at the console.

But you can see that this is not going to be a great way to document our work. Things run and overwrite other things. Nothing is saved permanently. It's a good way to learn a language, but difficult to tell how you got where you are.

To work with Python in a more permanent and better-documented way, you would use a Jupyter notebook.

## IV. Jupyter notebooks.

From this point forward, we'll proceed following the script in ex1iteration.ipynb.


