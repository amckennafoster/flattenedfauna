## Colorado Cougar Encounters Cleaning Log

### Dataset: ColoradoCougarRoadkill.csv 

### Original download: https://cpw.state.co.us/Documents/Research/Mammals/Publications/Alldredge-Front-Range-Cougar-Progress-Report.pdf#search=roadkill

Used [Tabula](https://tabula.technology/) tool to isolate tabular data from PDF

Filled down Cougar ID values

Filled down Sex values

Filtered by status = Dead

Remove columns: Conditioning, Release Loc, and Capture columns

Normalized Occurrence values

Changed all blank cells to "null" string

```[
  {
    "op": "core/text-transform",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Status",
          "expression": "value",
          "columnName": "Status",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Dead",
                "l": "Dead"
              }
            }
          ],
          "selectBlank": false,
          "selectError": false
        },
        {
          "type": "list",
          "name": "Occurrence",
          "expression": "value",
          "columnName": "Occurrence",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Road Kill",
                "l": "Road Kill"
              }
            },
            {
              "v": {
                "v": "Roadkill",
                "l": "Roadkill"
              }
            }
          ],
          "selectBlank": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Occurrence",
    "expression": "grel:forEach(value.split(\" \"), v, v).join(\"\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10,
    "description": "Text transform on cells in column Occurrence using expression grel:forEach(value.split(\" \"), v, v).join(\"\")"
  },
  {
    "op": "core/row-star",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Status",
          "expression": "value",
          "columnName": "Status",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Unknown",
                "l": "Unknown"
              }
            },
            {
              "v": {
                "v": "Unknwon",
                "l": "Unknwon"
              }
            },
            {
              "v": {
                "v": "Uncollared",
                "l": "Uncollared"
              }
            },
            {
              "v": {
                "v": "Alive",
                "l": "Alive"
              }
            }
          ],
          "selectBlank": true,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "starred": true,
    "description": "Star rows"
  },
  {
    "op": "core/row-removal",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Status",
          "expression": "value",
          "columnName": "Status",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Unknown",
                "l": "Unknown"
              }
            },
            {
              "v": {
                "v": "Unknwon",
                "l": "Unknwon"
              }
            },
            {
              "v": {
                "v": "Uncollared",
                "l": "Uncollared"
              }
            },
            {
              "v": {
                "v": "Alive",
                "l": "Alive"
              }
            }
          ],
          "selectBlank": true,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "description": "Remove rows"
  },
  {
    "op": "core/row-star",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Status",
          "expression": "value",
          "columnName": "Status",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Dead",
                "l": "Dead"
              }
            },
            {
              "v": {
                "v": "Unknown",
                "l": "Unknown"
              }
            },
            {
              "v": {
                "v": "Unknwon",
                "l": "Unknwon"
              }
            },
            {
              "v": {
                "v": "Uncollared",
                "l": "Uncollared"
              }
            },
            {
              "v": {
                "v": "Alive",
                "l": "Alive"
              }
            }
          ],
          "selectBlank": true,
          "selectError": false
        },
        {
          "type": "list",
          "name": "Occurrence",
          "expression": "value",
          "columnName": "Occurrence",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Livestock Depredation",
                "l": "Livestock Depredation"
              }
            },
            {
              "v": {
                "v": "Intraspecific Mort",
                "l": "Intraspecific Mort"
              }
            },
            {
              "v": {
                "v": "Livestock depredation",
                "l": "Livestock depredation"
              }
            },
            {
              "v": {
                "v": "Found dead",
                "l": "Found dead"
              }
            },
            {
              "v": {
                "v": "Pet Depredation",
                "l": "Pet Depredation"
              }
            },
            {
              "v": {
                "v": "Natural Mortality",
                "l": "Natural Mortality"
              }
            },
            {
              "v": {
                "v": "Human Conflict",
                "l": "Human Conflict"
              }
            },
            {
              "v": {
                "v": "In town (natural mort)",
                "l": "In town (natural mort)"
              }
            },
            {
              "v": {
                "v": "Encounter",
                "l": "Encounter"
              }
            },
            {
              "v": {
                "v": "Hunter Harvest",
                "l": "Hunter Harvest"
              }
            },
            {
              "v": {
                "v": "Euthanized/Lisa Wolfe",
                "l": "Euthanized/Lisa Wolfe"
              }
            },
            {
              "v": {
                "v": "Hunter",
                "l": "Hunter"
              }
            },
            {
              "v": {
                "v": "Depredation/Shot",
                "l": "Depredation/Shot"
              }
            },
            {
              "v": {
                "v": "Hunting",
                "l": "Hunting"
              }
            },
            {
              "v": {
                "v": "DWM Capture Mort",
                "l": "DWM Capture Mort"
              }
            },
            {
              "v": {
                "v": "Punctured intestine",
                "l": "Punctured intestine"
              }
            },
            {
              "v": {
                "v": "Deer Kill/Shot",
                "l": "Deer Kill/Shot"
              }
            },
            {
              "v": {
                "v": "Intraspecific mortality",
                "l": "Intraspecific mortality"
              }
            },
            {
              "v": {
                "v": "Shot",
                "l": "Shot"
              }
            },
            {
              "v": {
                "v": "Possible Intraspecific",
                "l": "Possible Intraspecific"
              }
            }
          ],
          "selectBlank": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "starred": true,
    "description": "Star rows"
  },
  {
    "op": "core/row-removal",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Status",
          "expression": "value",
          "columnName": "Status",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Dead",
                "l": "Dead"
              }
            },
            {
              "v": {
                "v": "Unknown",
                "l": "Unknown"
              }
            },
            {
              "v": {
                "v": "Unknwon",
                "l": "Unknwon"
              }
            },
            {
              "v": {
                "v": "Uncollared",
                "l": "Uncollared"
              }
            },
            {
              "v": {
                "v": "Alive",
                "l": "Alive"
              }
            }
          ],
          "selectBlank": true,
          "selectError": false
        },
        {
          "type": "list",
          "name": "Occurrence",
          "expression": "value",
          "columnName": "Occurrence",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Livestock Depredation",
                "l": "Livestock Depredation"
              }
            },
            {
              "v": {
                "v": "Intraspecific Mort",
                "l": "Intraspecific Mort"
              }
            },
            {
              "v": {
                "v": "Livestock depredation",
                "l": "Livestock depredation"
              }
            },
            {
              "v": {
                "v": "Found dead",
                "l": "Found dead"
              }
            },
            {
              "v": {
                "v": "Pet Depredation",
                "l": "Pet Depredation"
              }
            },
            {
              "v": {
                "v": "Natural Mortality",
                "l": "Natural Mortality"
              }
            },
            {
              "v": {
                "v": "Human Conflict",
                "l": "Human Conflict"
              }
            },
            {
              "v": {
                "v": "In town (natural mort)",
                "l": "In town (natural mort)"
              }
            },
            {
              "v": {
                "v": "Encounter",
                "l": "Encounter"
              }
            },
            {
              "v": {
                "v": "Hunter Harvest",
                "l": "Hunter Harvest"
              }
            },
            {
              "v": {
                "v": "Euthanized/Lisa Wolfe",
                "l": "Euthanized/Lisa Wolfe"
              }
            },
            {
              "v": {
                "v": "Hunter",
                "l": "Hunter"
              }
            },
            {
              "v": {
                "v": "Depredation/Shot",
                "l": "Depredation/Shot"
              }
            },
            {
              "v": {
                "v": "Hunting",
                "l": "Hunting"
              }
            },
            {
              "v": {
                "v": "DWM Capture Mort",
                "l": "DWM Capture Mort"
              }
            },
            {
              "v": {
                "v": "Punctured intestine",
                "l": "Punctured intestine"
              }
            },
            {
              "v": {
                "v": "Deer Kill/Shot",
                "l": "Deer Kill/Shot"
              }
            },
            {
              "v": {
                "v": "Intraspecific mortality",
                "l": "Intraspecific mortality"
              }
            },
            {
              "v": {
                "v": "Shot",
                "l": "Shot"
              }
            },
            {
              "v": {
                "v": "Possible Intraspecific",
                "l": "Possible Intraspecific"
              }
            }
          ],
          "selectBlank": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "description": "Remove rows"
  },
  {
    "op": "core/text-transform",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Status",
          "expression": "value",
          "columnName": "Status",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Dead",
                "l": "Dead"
              }
            },
            {
              "v": {
                "v": "Unknown",
                "l": "Unknown"
              }
            },
            {
              "v": {
                "v": "Unknwon",
                "l": "Unknwon"
              }
            },
            {
              "v": {
                "v": "Uncollared",
                "l": "Uncollared"
              }
            },
            {
              "v": {
                "v": "Alive",
                "l": "Alive"
              }
            }
          ],
          "selectBlank": true,
          "selectError": false
        },
        {
          "type": "list",
          "name": "Occurrence",
          "expression": "value",
          "columnName": "Occurrence",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "RoadKill",
                "l": "RoadKill"
              }
            },
            {
              "v": {
                "v": "Roadkill",
                "l": "Roadkill"
              }
            },
            {
              "v": {
                "v": "Livestock Depredation",
                "l": "Livestock Depredation"
              }
            },
            {
              "v": {
                "v": "Intraspecific Mort",
                "l": "Intraspecific Mort"
              }
            },
            {
              "v": {
                "v": "Livestock depredation",
                "l": "Livestock depredation"
              }
            },
            {
              "v": {
                "v": "Found dead",
                "l": "Found dead"
              }
            },
            {
              "v": {
                "v": "Pet Depredation",
                "l": "Pet Depredation"
              }
            },
            {
              "v": {
                "v": "Natural Mortality",
                "l": "Natural Mortality"
              }
            },
            {
              "v": {
                "v": "Human Conflict",
                "l": "Human Conflict"
              }
            },
            {
              "v": {
                "v": "In town (natural mort)",
                "l": "In town (natural mort)"
              }
            },
            {
              "v": {
                "v": "Encounter",
                "l": "Encounter"
              }
            },
            {
              "v": {
                "v": "Hunter Harvest",
                "l": "Hunter Harvest"
              }
            },
            {
              "v": {
                "v": "Euthanized/Lisa Wolfe",
                "l": "Euthanized/Lisa Wolfe"
              }
            },
            {
              "v": {
                "v": "Hunter",
                "l": "Hunter"
              }
            },
            {
              "v": {
                "v": "Depredation/Shot",
                "l": "Depredation/Shot"
              }
            },
            {
              "v": {
                "v": "Hunting",
                "l": "Hunting"
              }
            },
            {
              "v": {
                "v": "DWM Capture Mort",
                "l": "DWM Capture Mort"
              }
            },
            {
              "v": {
                "v": "Punctured intestine",
                "l": "Punctured intestine"
              }
            },
            {
              "v": {
                "v": "Deer Kill/Shot",
                "l": "Deer Kill/Shot"
              }
            },
            {
              "v": {
                "v": "Intraspecific mortality",
                "l": "Intraspecific mortality"
              }
            },
            {
              "v": {
                "v": "Shot",
                "l": "Shot"
              }
            },
            {
              "v": {
                "v": "Possible Intraspecific",
                "l": "Possible Intraspecific"
              }
            }
          ],
          "selectBlank": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Occurrence",
    "expression": "value.toTitlecase()",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10,
    "description": "Text transform on cells in column Occurrence using expression value.toTitlecase()"
  },
  {
    "op": "core/row-star",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Status",
          "expression": "value",
          "columnName": "Status",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Dead",
                "l": "Dead"
              }
            },
            {
              "v": {
                "v": "Unknown",
                "l": "Unknown"
              }
            },
            {
              "v": {
                "v": "Unknwon",
                "l": "Unknwon"
              }
            },
            {
              "v": {
                "v": "Uncollared",
                "l": "Uncollared"
              }
            },
            {
              "v": {
                "v": "Alive",
                "l": "Alive"
              }
            }
          ],
          "selectBlank": true,
          "selectError": false
        },
        {
          "type": "list",
          "name": "Occurrence",
          "expression": "value",
          "columnName": "Occurrence",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Shot killing goat",
                "l": "Shot killing goat"
              }
            },
            {
              "v": {
                "v": "Shot/Hunter",
                "l": "Shot/Hunter"
              }
            },
            {
              "v": {
                "v": "Shot/hunter",
                "l": "Shot/hunter"
              }
            },
            {
              "v": {
                "v": "Shot/Depredation",
                "l": "Shot/Depredation"
              }
            },
            {
              "v": {
                "v": "Unknown Mort.",
                "l": "Unknown Mort."
              }
            },
            {
              "v": {
                "v": "Shot/depredation",
                "l": "Shot/depredation"
              }
            },
            {
              "v": {
                "v": "Unknown mortality",
                "l": "Unknown mortality"
              }
            },
            {
              "v": {
                "v": "Shot by hunter",
                "l": "Shot by hunter"
              }
            },
            {
              "v": {
                "v": "Unknown Mortality",
                "l": "Unknown Mortality"
              }
            },
            {
              "v": {
                "v": "RoadKill",
                "l": "RoadKill"
              }
            },
            {
              "v": {
                "v": "Livestock Depredation",
                "l": "Livestock Depredation"
              }
            },
            {
              "v": {
                "v": "Intraspecific Mort",
                "l": "Intraspecific Mort"
              }
            },
            {
              "v": {
                "v": "Livestock depredation",
                "l": "Livestock depredation"
              }
            },
            {
              "v": {
                "v": "Found dead",
                "l": "Found dead"
              }
            },
            {
              "v": {
                "v": "Pet Depredation",
                "l": "Pet Depredation"
              }
            },
            {
              "v": {
                "v": "Natural Mortality",
                "l": "Natural Mortality"
              }
            },
            {
              "v": {
                "v": "Human Conflict",
                "l": "Human Conflict"
              }
            },
            {
              "v": {
                "v": "In town (natural mort)",
                "l": "In town (natural mort)"
              }
            },
            {
              "v": {
                "v": "Encounter",
                "l": "Encounter"
              }
            },
            {
              "v": {
                "v": "Hunter Harvest",
                "l": "Hunter Harvest"
              }
            },
            {
              "v": {
                "v": "Euthanized/Lisa Wolfe",
                "l": "Euthanized/Lisa Wolfe"
              }
            },
            {
              "v": {
                "v": "Hunter",
                "l": "Hunter"
              }
            },
            {
              "v": {
                "v": "Depredation/Shot",
                "l": "Depredation/Shot"
              }
            },
            {
              "v": {
                "v": "Hunting",
                "l": "Hunting"
              }
            },
            {
              "v": {
                "v": "DWM Capture Mort",
                "l": "DWM Capture Mort"
              }
            },
            {
              "v": {
                "v": "Punctured intestine",
                "l": "Punctured intestine"
              }
            },
            {
              "v": {
                "v": "Deer Kill/Shot",
                "l": "Deer Kill/Shot"
              }
            },
            {
              "v": {
                "v": "Intraspecific mortality",
                "l": "Intraspecific mortality"
              }
            },
            {
              "v": {
                "v": "Shot",
                "l": "Shot"
              }
            },
            {
              "v": {
                "v": "Possible Intraspecific",
                "l": "Possible Intraspecific"
              }
            }
          ],
          "selectBlank": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "starred": true,
    "description": "Star rows"
  },
  {
    "op": "core/row-removal",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Status",
          "expression": "value",
          "columnName": "Status",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Dead",
                "l": "Dead"
              }
            },
            {
              "v": {
                "v": "Unknown",
                "l": "Unknown"
              }
            },
            {
              "v": {
                "v": "Unknwon",
                "l": "Unknwon"
              }
            },
            {
              "v": {
                "v": "Uncollared",
                "l": "Uncollared"
              }
            },
            {
              "v": {
                "v": "Alive",
                "l": "Alive"
              }
            }
          ],
          "selectBlank": true,
          "selectError": false
        },
        {
          "type": "list",
          "name": "Occurrence",
          "expression": "value",
          "columnName": "Occurrence",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [
            {
              "v": {
                "v": "Shot killing goat",
                "l": "Shot killing goat"
              }
            },
            {
              "v": {
                "v": "Shot/Hunter",
                "l": "Shot/Hunter"
              }
            },
            {
              "v": {
                "v": "Shot/hunter",
                "l": "Shot/hunter"
              }
            },
            {
              "v": {
                "v": "Shot/Depredation",
                "l": "Shot/Depredation"
              }
            },
            {
              "v": {
                "v": "Unknown Mort.",
                "l": "Unknown Mort."
              }
            },
            {
              "v": {
                "v": "Shot/depredation",
                "l": "Shot/depredation"
              }
            },
            {
              "v": {
                "v": "Unknown mortality",
                "l": "Unknown mortality"
              }
            },
            {
              "v": {
                "v": "Shot by hunter",
                "l": "Shot by hunter"
              }
            },
            {
              "v": {
                "v": "Unknown Mortality",
                "l": "Unknown Mortality"
              }
            },
            {
              "v": {
                "v": "RoadKill",
                "l": "RoadKill"
              }
            },
            {
              "v": {
                "v": "Livestock Depredation",
                "l": "Livestock Depredation"
              }
            },
            {
              "v": {
                "v": "Intraspecific Mort",
                "l": "Intraspecific Mort"
              }
            },
            {
              "v": {
                "v": "Livestock depredation",
                "l": "Livestock depredation"
              }
            },
            {
              "v": {
                "v": "Found dead",
                "l": "Found dead"
              }
            },
            {
              "v": {
                "v": "Pet Depredation",
                "l": "Pet Depredation"
              }
            },
            {
              "v": {
                "v": "Natural Mortality",
                "l": "Natural Mortality"
              }
            },
            {
              "v": {
                "v": "Human Conflict",
                "l": "Human Conflict"
              }
            },
            {
              "v": {
                "v": "In town (natural mort)",
                "l": "In town (natural mort)"
              }
            },
            {
              "v": {
                "v": "Encounter",
                "l": "Encounter"
              }
            },
            {
              "v": {
                "v": "Hunter Harvest",
                "l": "Hunter Harvest"
              }
            },
            {
              "v": {
                "v": "Euthanized/Lisa Wolfe",
                "l": "Euthanized/Lisa Wolfe"
              }
            },
            {
              "v": {
                "v": "Hunter",
                "l": "Hunter"
              }
            },
            {
              "v": {
                "v": "Depredation/Shot",
                "l": "Depredation/Shot"
              }
            },
            {
              "v": {
                "v": "Hunting",
                "l": "Hunting"
              }
            },
            {
              "v": {
                "v": "DWM Capture Mort",
                "l": "DWM Capture Mort"
              }
            },
            {
              "v": {
                "v": "Punctured intestine",
                "l": "Punctured intestine"
              }
            },
            {
              "v": {
                "v": "Deer Kill/Shot",
                "l": "Deer Kill/Shot"
              }
            },
            {
              "v": {
                "v": "Intraspecific mortality",
                "l": "Intraspecific mortality"
              }
            },
            {
              "v": {
                "v": "Shot",
                "l": "Shot"
              }
            },
            {
              "v": {
                "v": "Possible Intraspecific",
                "l": "Possible Intraspecific"
              }
            }
          ],
          "selectBlank": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "description": "Remove rows"
  }
  {
    "op": "core/mass-edit",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Age",
          "expression": "value",
          "columnName": "Age",
          "invert": false,
          "omitBlank": false,
          "omitError": false,
          "selection": [],
          "selectBlank": true,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Age",
    "expression": "value",
    "edits": [
      {
        "from": [
          ""
        ],
        "fromBlank": true,
        "fromError": false,
        "to": "null"
      }
    ],
    "description": "Mass edit cells in column Age"
  }
]``
