# Food
A small command-line tool for tracking the price of food from different sources.

### Examples of behaviour

Here are some sample use-cases. Example data is used to illustrate input & expected output. Lines prefixed with `>` denote output. 

##### Adding entries

```
food kaisers
> Adding entries for kaisers, blank entry closes session
peas 1.99
corn 2.44
corn chips 2.49
breakfast tea 50s 6

> Stored 4 new entries under kaisers, total spend of 12.92 recorded
```

##### Searching entries

```
food search peas
> Found 3 entries for peas:
> ------------------------------
> 2014-01-05	Kaisers 	1.99
> 2014-01-04	Eurogida	1.80
> 2014-01-02	Biomarkt	2.25
> ------------------------------
> Avg: 2.01
> Least expensive: Kaisers
> Most expensive:  Biomarkt
```

##### Searching entries for a specific source

```
food kaisers search peas
> Found 2 entries for peas at Kaisers:
> ------------------
> 2014-01-05	1.99
> 2014-01-04	1.89
> ------------------
> Avg: 1.94
> Change: +5.29%
```

##### Removing an entry

```
food rm 1353920
> Removed entry 1353920 (2014-01-05, Kaisers, peas, 1.99)
```

##### Listing sources

```
food ls
> There are 6 sources recorded:
> -----------------------------
> ALDI
> Biomarket Karl-Marxstr
> Eurogida
> Kaisers
> LIDL
> LPG Biomarket
```

##### Statistics

```
food stats
> There are 206 entries in total
> There are 6 different locations recorded
> Total expenditure recorded is 412.60
```

### Other elements for consideration

- Displaying UUIDs for items (important for removal)
- Listing all items
- Removing an entire source (eg. `food rm kaisers`)

### Technology

The [Level](https://github.com/level/level) package could be used to store a user's data locally, similar to how it has been done in [Clocker](https://github.com/substack/clocker).
