# abbr

A tool to find and expand abbreviations within a string. Designed for scientific writing.



abbr is an abbreviation of "abbreviations." It is a regular expression based tool to find and expand abbreviations in text, and it is designed for use with scientific writing.
Use cases may include counting terms within a scientific article when the relationship between full term and abbreviation is not known ahead of time or improving meta-analytic estimates of term frequency.

Abbreviations are expected to be presented using parentheses, as is standard in APA format.

Currently supported:
- Initialisms/Acronyms in parentheses: E.g., full term (FT)
  - This includes acronyms using non-initial letters: E.g., full term (fuTE)
  - All letters within the abbreviation must occur in the words preceding the abbreviation's first use.
- The above, with citations after the abbreviation: E.g., full term (FT; Example et al., 2016)


## Installation
```shell
git clone git@github.com:NBCLab/abbr.git
cd abbr/

# for users:
python setup.py install

# for developers:
python setup.py develop
```

## Usage
abbr can be used both to generate a dictionary of terms used in a text, as well as to expand those terms within the text. We can use abbr to find all abbreviations within a text, and return a dictionary of terms as well as identified definitions:
```python
from abbr import findall
d = findall(text)
```

Where *d* will be a dictionary similar to the following:
```python
{
"RMTg": "rostromedial tegmental nucleus",
"CRF": "corticotropin-releasing factor",
"VTA/SN": "ventral tegmental area/substantia nigra compacta",
"VS": "ventral striatum",
"LHb": "lateral habenula",
"nAChR": "nicotinic acetylcholine receptors"
}
```

abbr can also be used directly to expand abbreviations within a text and return the expanded text.
```python
from abbr import expandall
text = expandall(text)
```

