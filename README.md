# Overview
This repository contains rotations for almost all Genshin Impact characters for the https://gcsim.app/simulator calculator

There are different variants of commands for one character, as well as configs are automatically adjusted to the character's constellations and there are artifact set switches that change the rotation

# Getting Started
The `builds.json` file stores a dictionary with characters name keys, inside it describes the id and name rotation for that character.

For example:
```python
name = builds["alhaitham"]["teams"][0]["name"]
id = builds["alhaitham"]["teams"][0]["id"]
config = open(f"teams/alhaitham/{id}.txt", "r").read()
```
---
The `rotations` field means how many loop passes are written in the rotation code. This is necessary to calculate DPR from DPS by the formula
`DPS * TIME / Rotations = DPR`
```json
"rotations": 5
```
---
If the `rotations` field is not mentioned in the json, then it must be equal to `4` for this team

Sometimes there is a field `rules` that stores the list, the value `two-targets` means that there are two enemies in the rotation instead of one as usual and the total DPS will have to be divided by 2.
```json
"rules": ["two-targets"]
```
