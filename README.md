# Discussion Questions: Execution Context

## Objectives

- Explain JavaScript execution context in terms of English language patterns
- Predict behavior of JavaScript's `this` keyword

## Exercise: Context in Language

In conversation, we use pronouns to 'stand in' for the nouns they refer to. In order to understand sentences that take advantage of this 'language feature', speakers need to be able to infer the meaning _from the context_.

For the following example phrases, figure out what the **bolded pronoun** refers to:

> 🎵 Oh, **I** just can't wait to be king! 🎵

> All the world's a stage, and all the men and women merely players: **they** have their exits and their entrances. [Shakespeare, As You Like It]

> Every building is designed around the movements of people: **they** have their exits and their entrances.

> **This** weekend we are going to visit Grandma

> "Hello, who is **this**?"

### Context in Language Discussion Questions

In English, you are able to follow certain (unconscious) rules to determine what a particular pronoun refers to.

1. The phrase "**they** have their exits and their entrances" referred to a different **they** in the two different sentences. What let you know what the pronoun referred to?

2. What rules does the JavaScript engine use to infer the meaning of `this`?

> Note: Interpreting the phrase "Hello, who is **this**?" in English follows similar rules to the way the JavaScript engine determines the meaning of `this`. It's based on the _caller_ (unless another rule applies). You might keep this example in mind if you're trying to remember how JavaScript's `this` rules work.

## Predicting the behavior of JavaScript's `this` keyword

In your groups, for each of the following snippets, predict the output. Then, run the sample code and check if your answer was right. If you predicted wrong, try to figure out why the code behaved differently from what you expected.

Pay close attention - the rules aren't always what you think at first glance.

### Example 1

```js
var telephone = {
  origin: "home phone",
  answer: function() {
    console.log(`Hello, ${this.origin} called the function`);
  }
};

telephone.answer();
```

### Example 2

```js
var telephone = {
  origin: "home phone",
  answer: function() {
    console.log(`Hello, ${this.origin} called the function`);
  }
};

answer = telephone.answer;
answer();
```

### Example 3

```js
var telephone = {
  answer: function() {
    console.log(`Hello, ${this.origin} called the function`);
  }
};

var cellphone = {
  origin: "cell phone"
};

cellphone.answer = telephone.answer;
cellphone.answer();
```

### Example 4

```js
var telephone = {
  origin: "home phone",
  answer: () => {
    console.log(`Hello, ${this.origin} called the function`);
  }
};

telephone.answer();
```
