## Idaho roadkill cleaning log
 Fixed improper utf-8 decoding
 Normalized dates to ISO 8601
 Converted blank cells to "null"

```[
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Note using expression grel:value.replace(\"â€™\",\"'\")",
    "engineConfig": {
      "facets": [],
      "mode": "row-based"
    },
    "columnName": "Note",
    "expression": "grel:value.replace(\"â€™\",\"'\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/column-split",
    "description": "Split column Observed by field lengths",
    "engineConfig": {
      "facets": [],
      "mode": "row-based"
    },
    "columnName": "Observed",
    "guessCellType": true,
    "removeOriginalColumn": true,
    "mode": "lengths",
    "fieldLengths": [
      3,
      1,
      3,
      1,
      2,
      1,
      12,
      1,
      4
    ]
  },
  {
    "op": "core/column-removal",
    "description": "Remove column Observed 8",
    "columnName": "Observed 8"
  },
  {
    "op": "core/column-removal",
    "description": "Remove column Observed 7",
    "columnName": "Observed 7"
  },
  {
    "op": "core/column-removal",
    "description": "Remove column Observed 6",
    "columnName": "Observed 6"
  },
  {
    "op": "core/column-removal",
    "description": "Remove column Observed 4",
    "columnName": "Observed 4"
  },
  {
    "op": "core/column-removal",
    "description": "Remove column Observed 2",
    "columnName": "Observed 2"
  },
  {
    "op": "core/column-removal",
    "description": "Remove column Observed 1",
    "columnName": "Observed 1"
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Aug\",\"08\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Aug",
                "l": "Aug"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Aug\",\"08\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Apr\",\"04\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Apr",
                "l": "Apr"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Apr\",\"04\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Dec\",\"12\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Dec",
                "l": "Dec"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Dec\",\"12\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Feb\",\"02\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Feb",
                "l": "Feb"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Feb\",\"02\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Jan\",\"01\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Jan",
                "l": "Jan"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Jan\",\"01\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Jul\",\"07\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Jul",
                "l": "Jul"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Jul\",\"07\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Jun\",\"06\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Jun",
                "l": "Jun"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Jun\",\"06\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Mar\",\"03\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Mar",
                "l": "Mar"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Mar\",\"03\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"May\",\"05\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "May",
                "l": "May"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"May\",\"05\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Nov\",\"11\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Nov",
                "l": "Nov"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Nov\",\"11\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Oct\",\"10\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Oct",
                "l": "Oct"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Oct\",\"10\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed 3 using expression grel:value.replace(\"Sep\",\"09\")",
    "engineConfig": {
      "facets": [
        {
          "type": "list",
          "name": "Observed 3",
          "expression": "value",
          "columnName": "Observed 3",
          "invert": false,
          "selection": [
            {
              "v": {
                "v": "Sep",
                "l": "Sep"
              }
            }
          ],
          "selectNumber": false,
          "selectDateTime": false,
          "selectBoolean": false,
          "omitBlank": false,
          "selectBlank": false,
          "omitError": false,
          "selectError": false
        }
      ],
      "mode": "row-based"
    },
    "columnName": "Observed 3",
    "expression": "grel:value.replace(\"Sep\",\"09\")",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  },
  {
    "op": "core/column-move",
    "description": "Move column Observed 9 to position 2",
    "columnName": "Observed 9",
    "index": 2
  },
  {
    "op": "core/column-move",
    "description": "Move column Observed 9 to position 1",
    "columnName": "Observed 9",
    "index": 1
  },
  {
    "op": "core/column-addition",
    "description": "Create column Observed at index 2 based on column Observed 9 using expression grel:value + \"-\" + cells[\"Observed 3\"].value + \"-\" + cells[\"Observed 5\"].value",
    "engineConfig": {
      "facets": [],
      "mode": "row-based"
    },
    "newColumnName": "Observed",
    "columnInsertIndex": 2,
    "baseColumnName": "Observed 9",
    "expression": "grel:value + \"-\" + cells[\"Observed 3\"].value + \"-\" + cells[\"Observed 5\"].value",
    "onError": "set-to-blank"
  },
  {
    "op": "core/column-removal",
    "description": "Remove column Observed 9",
    "columnName": "Observed 9"
  },
  {
    "op": "core/column-removal",
    "description": "Remove column Observed 3",
    "columnName": "Observed 3"
  },
  {
    "op": "core/column-removal",
    "description": "Remove column Observed 5",
    "columnName": "Observed 5"
  },
  {
    "op": "core/text-transform",
    "description": "Text transform on cells in column Observed using expression value.toDate()",
    "engineConfig": {
      "facets": [],
      "mode": "row-based"
    },
    "columnName": "Observed",
    "expression": "value.toDate()",
    "onError": "keep-original",
    "repeat": false,
    "repeatCount": 10
  }
]```
