# Wikipedia US States Data - All 50 States

## Dataset Overview
This dataset contains comprehensive Wikipedia information for all 50 United States. Each state's Wikipedia page content has been extracted and saved as individual text files for easy access and analysis.

**Extraction Date:** April 19, 2026  
**Total States:** 50  
**Total Files:** One .txt file per state

---

## Dataset Contents

### File Structure
```
us_states_data/
├── Alabama.txt
├── Alaska.txt
├── Arizona.txt
│
└── Wyoming.txt
```

Each `.txt` file contains:
- Full Wikipedia article text for that state
- Complete sections (History, Geography, Government, Economy, Culture, etc.)
- Relevant information about the state
- Demographics and population data
- Natural resources and climate
- Major cities and landmarks

### States Included
All 50 US States:

**Alphabetical List:**
Alabama, Alaska, Arizona, Arkansas, California, Colorado, Connecticut, Delaware, Florida, Georgia, Hawaii, Idaho, Illinois, Indiana, Iowa, Kansas, Kentucky, Louisiana, Maine, Maryland, Massachusetts, Michigan, Minnesota, Mississippi, Missouri, Montana, Nebraska, Nevada, New Hampshire, New Jersey, New Mexico, New York, North Carolina, North Dakota, Ohio, Oklahoma, Oregon, Pennsylvania, Rhode Island, South Carolina, South Dakota, Tennessee, Texas, Utah, Vermont, Virginia, Washington, West Virginia, Wisconsin, Wyoming

---

## Data Source

**Source:** Wikipedia (English Edition)  
**Extraction Method:** Python `wikipediaapi` library  
**Language:** English

### Citation
> Wikipedia contributors. (2026). *[State Name]*. In Wikipedia, The Free Encyclopedia. Retrieved from Wikipedia API on April 19, 2026.

---

## License

This dataset is licensed under **CC-BY-SA 4.0 (Creative Commons Attribution-Share Alike 4.0)**.

### License Details:
- **Attribution Required:** You must credit Wikipedia and the original authors
- **Share-Alike:** Any derivative works must use the same CC-BY-SA 4.0 license
- **You are free to:**
  - Share the dataset
  - Adapt and create derivative works
  - Use for commercial purposes
- **You must:**
  - Provide appropriate credit
  - Include a link to the license
  - Indicate if changes were made
  - Apply the same license to derivative works

**License Text:** https://creativecommons.org/licenses/by-sa/4.0/

---

## Dataset Specifications

- **Format:** Plain Text (.txt)
- **Encoding:** UTF-8
- **Total Size:** Approximately 15-20 MB
- **File Count:** 50 files (one per state)
- **Average File Size:** ~300-400 KB per state
- **Largest Files:** California, Texas, New York (more population/content)
- **Smallest Files:** Wyoming, Vermont, Alaska (less populous)

---

## How to Use

### 1. **Load and Read Files**
```python
import os

# Read a single state's data
with open('us_states_data/California.txt', 'r', encoding='utf-8') as file:
    content = file.read()
    print(content)
```

### 2. **Process All States**
```python
import os

states_dir = 'us_states_data'

for filename in os.listdir(states_dir):
    if filename.endswith('.txt'):
        filepath = os.path.join(states_dir, filename)
        with open(filepath, 'r', encoding='utf-8') as file:
            content = file.read()
            # Process content...
            print(f"Processing: {filename}")
```

### 3. **NLP / Text Analysis**
```python
from collections import Counter
import re

# Extract all text from all states
texts = {}
for filename in os.listdir('us_states_data'):
    if filename.endswith('.txt'):
        state_name = filename.replace('.txt', '').replace('_', ' ')
        with open(f'us_states_data/{filename}', 'r', encoding='utf-8') as f:
            texts[state_name] = f.read()

# Perform analysis
all_text = ' '.join(texts.values())
words = re.findall(r'\w+', all_text.lower())
word_freq = Counter(words)

# Find most common words
print(word_freq.most_common(20))
```

### 4. **Compare States**
```python
# Find which state has the longest article
state_lengths = {}
for filename in os.listdir('us_states_data'):
    if filename.endswith('.txt'):
        state_name = filename.replace('.txt', '').replace('_', ' ')
        with open(f'us_states_data/{filename}', 'r', encoding='utf-8') as f:
            state_lengths[state_name] = len(f.read())

longest = max(state_lengths, key=state_lengths.get)
print(f"Longest article: {longest} ({state_lengths[longest]} characters)")
```

---

## Use Cases

- **NLP & Text Analysis:** Text preprocessing, sentiment analysis, topic modeling
- **Educational Research:** Learning about US states, geography, demographics
- **Machine Learning:** Training models on state-specific information
- **Data Science Projects:** Feature extraction, text mining, comparative analysis
- **Geographic Analysis:** State characteristics, population trends, economic data
- **Information Retrieval:** Building search indexes for state information
- **Social Studies:** Teaching resources for US geography and civics
- **Regional Comparison:** Analyzing similarities/differences between states

---

## Data Quality Notes

- **Extraction Date:** April 19, 2026
- **Completeness:** All 50 states successfully extracted
- **Data Variety:**
  - Large states (CA, TX, NY) have more comprehensive articles
  - All states maintain consistent structure with Wikipedia standards
  - Content accuracy depends on Wikipedia's editorial standards

---

## Statistics by State

### Largest Articles (by content):
- California - Largest population and economy
- Texas - Large geographic area and population
- New York - Historical significance and population

### Smallest Articles:
- Wyoming - Smallest population
- Vermont - Smaller population
- Alaska - Smaller population but geographic significance

---

## Update Information

- **Dataset Version:** 1.0
- **Last Updated:** April 19, 2026
- **Extraction Tool:** Extract_US_States.py

For the most current information, consider re-running the extraction from Wikipedia using the provided Python script.

---

## Acknowledgments

- **Wikipedia Community:** For maintaining comprehensive state information
- **Data Extraction:** Python `wikipediaapi` library
- **Contributor:** Muhammad Sudais Khalid

---

## Questions & Support

For issues or questions about the dataset:
1. Check individual state Wikipedia pages for source information
2. Refer to the extraction script (Extract_US_States.py) for methodology
3. Review CC-BY-SA 4.0 license terms for usage rights

---

## Disclaimer

This dataset is a derivative work of Wikipedia content. Users must comply with CC-BY-SA 4.0 licensing requirements when using, sharing, or modifying this data. The dataset creators are not responsible for the accuracy or completeness of Wikipedia content.

---

**Happy analyzing! 🇺🇸**
