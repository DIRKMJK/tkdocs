Search for official documents of the Dutch Lower House (Tweede Kamer) and extract relevant data.

Note that this is work in progress. The package may not work properly. Currently only queries for motions (moties) and amendments (amendementen) are supported.

# Installation

`pip install tkdocs`

# Simple example

```python
from tkdocs import query_tk

data = {
    'query': 'referentiewaarden,minimumloon',
    'fromdate': '2017-03-15',
    'todate': '2023-01-01',
    'operator': 'and',
    'doc_type': 'motie',
    'dir_results': '../data/wml',
    'download_files': True
}

query_tk(**data)
```

This will search for motions with search query `referentiewaarden AND minimumloon`, between 15 March 2017 and 1 January 2023.

Results will be stored as an excel file containing data including date, title, who sponsored the motion, and how parties voted (`../data/wml/results.xlsx`). Since `download_files` was set to `True`, the pdf’s containing the motion text will be downloaded as well, and stored in `../data/wml/files`.

Als long as you don’t change `dir_results`, results will be merged if you do multiple queries.

For all options, see `help(query_tk)`.