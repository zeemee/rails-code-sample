# Rails Developer Code Sample Project

###### Purpose

The purpose of this exercize is to give us an example of your work within bounds, guildelines and specifications suppled to you. It provides us some insight into how you work, how you think, and how you build things. It also provides the opportunity for multiple discussion points during an interview. Hopefully this is also fun!

###### The Ask

We would like you to build a rails app that serves a public api. The api consists of two endpoints:

* A pageable api that allows for searching
* An api that accepts an id, and provides details on a specific object

###### Requirements

* You can build this with any version of Rails and Ruby you see fit
* You can build this with any gems, databases or services you see fit
* There should be reasonable test coverage
* You must use the data provided in the Resources section. How you design things and how you work with that data is up to you.
* A basic administration interface to modify database records should exist. ActiveAdmin or similar packages are completely fine to use.

###### Specifications

The search endpoint should be defined as follows:

`GET /api/search?index=<number>&limit=<number>&query=<string>`

Paramaters:
**index**: A numerical index that represents the offset to start returning results from. Default 0.
**limit**: A numerical limit on results to return. Default 10.
**query**: A string to query for results. This should search the **name** of a cocktail recipe inclusively, as in, 'rita' should find 'Margarita'. An empty query string should result in an empty results array.

The result format should look like this:

```
{
  "drinks": 
    [
      {
        "id": 1234,
        "name": "Aztec Punch",
        "category": "Punch Party Drink",       
        "image": "https://www.thecocktaildb.com/images/media/drink/uqwuyp1454514591.jpg"
      },
      ...
   ]
}
```

The details endpoint should be defined as follows:
`GET /api/detail?id=<some type of id>`

Parameters:
**id**: This should be an identifier of a cocktail recipe record. I'd assume an int, but if you want to use a UUID string, that's fine too.

The result format should look like this:

```
{
  "drinks": 
    [
      {
        "id": 1234,
        "name": "Aztec Punch",
        "category": "Punch Party Drink",
        "container": "Punch bowl",
        "instructions": "Mix all ingredients in a pitcher. Mix thoroughly and pour into whatever is available, the bigger the better! This drink packs a big punch, so don't over do it.",
        "image": "https://www.thecocktaildb.com/images/media/drink/uqwuyp1454514591.jpg",
        "ingredients" : [
          {
            "name" : "Lemonade",
            "measurement": "1 can"
          },
          ...
        ]
      }
   ]
}
```

###### Resources

This project provides two data files for your use to populate your database, [cocktail_recipes.csv](cocktail_recipes.csv) and [cocktail_recipes.json](cocktail_recipes.json). They both contain the same data, but  one is a flat structure suited for csv ingestion, the other is a hierarchal json file if you prefer to work with that format.

This data is based on the free api at [The Cocktail DB](https://www.thecocktaildb.com), because why can't work be fun? :)

###### Submission

We're flexible in how you submit your work. If you want to .zip it up and email it, that's fine, if you want to create a private github account and submit a link to a repo, that's fine too.

###### Thoughts and Notes

This is just an exercise. While the methods and approaches you take to problems should be indicative of how you would approach a problem in a production environment, we don't expect any over-the-top work here. Don't spend tons of time on it. If you think something really needs a complex solution that would take a lot of work, implement a lesser solution, write a note in comments about a proper solution, and we can discuss it.


