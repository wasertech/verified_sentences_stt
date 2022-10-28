# Verified Sentences for STT

Verified sentences for STT uses, by Data Manager.


## Small sample

Using the [Training Wizard for STT](https://gitlab.com/waser-technologies/models/en/stt/-/blob/master/model.train), 

Users are presented with some sentences from the NLU data.

Their role is to determine if the sentences can be used to train a language model for STT.

If a sentence is usable, then it is accepted (`true += 1`).
Else it is rejected (`false =+ 1`).

At the end of the process users can share their results.

They look like so.

```toml
# reviews.toml

["can you lookup something for me please"]
true = 1
false = 0
lang = ["en",]

["answer me this"]
true = 1
false = 0
lang = ["en",]

[ddgr]
true = 0
false = 1
lang = ["en",]
```

To find if any sentence is valid, get the boolean with the highest count.

Checkout [`reviews.toml`](reviews.toml) to see everything.

`lang` is a list of languages the sentences has been or not verified

## Usage

This data can be used to quickly train a language model for STT applications (such as [Assistant](https://gitlab.com/waser-technologies/technologies/assistant)). It can also be used to train a classifier to automate even more the process.

Using the Training Wizard, you can pull requests automatically once you are done validating your data.
