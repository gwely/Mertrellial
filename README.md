# Mertrellial

Updates Trello cards via Mercurial commit messages.

## Usage

`new Mertrellial("<repository directory filepath>", "<Trello appy key>", "<Trello auth token>").CheckCommits();`

You can set the `app key` and `auth token` in the constructor as default values so your instantiation is a little more clean. You can also specify a `DateTime` from which to check for commits (the default is within the last hour):

`new Mertrellial("<repo path>").CheckCommits(DateTime.Now.AddHours(-1))`

## Syntax

`<VERB> <BOARD> card <CARD #> commit message`

The verb is optional. It will move the card to the specified list.

Example:

`coding Mertrellial card 2: updated README`

## Personalization

You'll want to personalize the Trello list names and verb identifiers. The `VERBS` List is defined at the top of the `Mertrellial` class.
The `Verb` class is where the verbs are translated into Trello lists.

For instance, my default Trello lists are `Planning,Coding,Testing,User Acceptance,Done`. So I use the following verbs to move cards to the specified lists:

```
developing -> Development,
coding -> Development,
testing -> Testing,
waiting -> User Acceptance,
finishing -> Done,
finished -> Done
```

## Dependencies

[Trello.NET](https://github.com/dillenmeister/Trello.NET/)

[Mercurial.NET](https://mercurialnet.codeplex.com/)