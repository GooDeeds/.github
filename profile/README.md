# GooDeeds

GooDeeds is a little project which origin lies in the Ramadan Code Fest 2023 on stackstream for the project Polarstern of SOS Kinderdorf.
We implemented an Android app using .NET MAUI, which is the main product of our project and an API providing some data for the app.
The purpose of GooDeeds is to give an attraction to do good deeds using simple gamification. We implemented this in the shape of an app which gives you daily reminders to do good deeds and rewarding you for completing them with achievements for reaching certain milestones but also experience which highers the level of your avatar.

## GooDeeds API

The GooDeeds API provides [Deeds](https://deedapi.thelooser.de/deed) and [achievements](https://deedapi.thelooser.de/achievement) for the app. Currently you can't add, delete or edit entrys but that is a planned feature.

### Achievements
An achievement consists of an ID, a **type**, a **value**, a **name** and a **description**.\
The **type** is a number which is used to determine what kind of things have to be done, for example to do a certain amount of deeds. This is defined and implemented in the app.\
The **value** is also a number but it describes how many times you have to do the thing defined in the type. If you take the example from before you could say that you would have to complete 10 deeds to get this achievement.\
The **name** of the achievement is a short explanation what you have to do in shape of a string. The name for the achievement to complete 10 deeds is "Complete 10 deeds!".\
The **description**, being a string again, is most of the time a funny text that congratulates you for reaching the achievement.\
Here is an example entry:\
```
{
    "id":1,
    "value":1,
    "type":1,
    "name":"Complete your first deed!",
    "description":"Congratulations! You have completed your first good deed! Keep up the good work!"
}
```

### Deeds
A deed consists of an ID, a **title**, a **description**, **experience** and **deed_generator**.\
The **title** is a string telling you the objective of the object. For instance "Donate money to a charity".\
The **description** contains the informations of the title but it is formulated in a funny way. The description for the first example is "If you are feeling flush and want to spread some love, why not fling some cash towards a charity? It is like giving your wallet a hug, except the warm fuzzy feelings go to someone in need instead of your money!"\
The **experience** is a number which describes the rewarded experience points for completing this deed. The experience for "Donate to a charity" would be 750.
The value of **deed_generator** is used to determine what base text is used while sharing a achievement. The base text is defined in the app.\
Here is an example entry:\
```
{
  "id":18,
  "title":"Donate money to a charity",
  "description":"If you are feeling flush and want to spread some love, why not fling some cash towards a charity? It is like giving your wallet a hug, except the warm fuzzy feelings go to someone in need instead of your money!",
  "experience":750,
  "deed_generator":1
}
```
