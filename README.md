# gradable_nouns

The term "gradable noun" - a noun that can be inflected to specify the degree or grade of something - is not often encountered, but is nevertheless used in everyday speech. Terms such as "linguistic value" and "linguistic variable" also address this space, although there seems to be some overlap/confusion in the definition of "linguistic variable".

Inasmuch as measurement theory is the study of how numbers are assigned to objects and phenomena, this project is a pragmatic approach to the linguistic handling of phrases such as "large family", "young person", or "modest increase". It starts with an initially small collection of nouns in json format (see https://github.com/colingoldberg/gradable_nouns/blob/master/data/noun_measures.json) for which adjectives have been found that can be considered to be "measures" of that noun.

Consider an example entry - the noun "accuracy":
```
	"accuracy": {
		"ranked": ["low", ["great", "high"]],
		"values": {
			"great": {
				"great.a.01": {
					"def": "relatively large in size or number or extent; larger than others of its kind; ~~a great juicy steak~~; ~~a great multitude~~; ~~the great auk~~; ~~a great old oak~~; ~~a great ocean liner~~; ~~a great delay~~  ; remarkable or out of the ordinary in degree or magnitude or effect; ~~a great crisis~~; ~~had a great stake in the outcome~~  ; of major significance or importance; ~~a great work of art~~; ~~Einstein was one of the outstanding figures of the 20th centurey~~",
					"nnixs": [0],
					"reason": "synset_part1: great equals adj"
				},
				"rank": 1.0
			},
			"high": {
				"high.a.01": {
					"def": "greater than normal in degree or intensity or amount; ~~a high temperature~~; ~~a high price~~; ~~the high point of his career~~; ~~high risks~~; ~~has high hopes~~; ~~the river is high~~; ~~he has a high opinion of himself~~  ; (used of the smell of meat) smelling spoiled or tainted  ; (literal meaning) being at or having a relatively great or specific elevation or upward extension (sometimes used in combinations like ~~knee-high~~); ~~a high mountain~~; ~~high ceilings~~; ~~high buildings~~; ~~a high forehead~~; ~~a high incline~~; ~~a foot high~~  ; used of sounds and voices; high in pitch or frequency  ; happy and excited and energetic  ; standing above others in quality or position; ~~people in high places~~; ~~the high priest~~; ~~eminent members of the community~~",
					"nnixs": [0],
					"reason": "synset_part1: high equals adj"
				},
				"rank": 1.0
			},
			"low": {
				"low.a.01": {
					"def": "very low in volume; ~~a low murmur~~; ~~the low-toned murmur of the surf~~  ; used of sounds and voices; low in pitch or frequency  ; low or inferior in station or quality; ~~a humble cottage~~; ~~a lowly parish priest~~; ~~a modest man of the people~~; ~~small beginnings~~  ; no longer sufficient; ~~supplies are low~~; ~~our funds are depleted~~  ; less than normal in degree or intensity or amount; ~~low prices~~; ~~the reservoir is low~~  ; unrefined in character; ~~low comedy~~  ; literal meanings; being at or having a relatively small elevation or upward extension; ~~low ceilings~~; ~~low clouds~~; ~~low hills~~; ~~the sun is low~~; ~~low furniture~~; ~~a low bow~~",
					"nnixs": [0],
					"reason": "synset_part1: low equals adj"
				},
				"rank": 0.50
			}
		},
		"nodes": [{
			"id": 50068,
			"name": "accuracy",
			"synset": "accuracy.n.01",
			"def": "(mathematics) the number of significant figures given in a number; ~~the atomic clock enabled scientists to measure time with much greater accuracy~~  ; the quality of being near to the true value; ~~he was beginning to doubt the accuracy of his compass~~; ~~the lawyer questioned the truth of my account~~"
		}]
	}
  ```
  
For each noun, the element "ranked" is an ordered list of adjectives (or a list of adjectives), which provides a basis for comparing one adjective with another. This is an admittedly subjective ordering - consider it to be a start, which allows the calculation of the element "rank" for each adjective.

So in the example above:
- "low" has a rank of 0.50
- "great" has a rank of 1.0
- "high" has a rank of 1.0

Please note:
- These three adjectives are surely not the only ones that can apply to the noun "accuracy" - more adjectives can be added. (Other nouns have many more adjectives).

Another example:
```
"mistake":
"ranked": [
			["little", "minor", "slight", "small"],
			["awful", "bad", "big", "costly", "grave", "serious", "significant"],
			["critical", "disastrous", "fatal", "fundamental"], "worst"
		]
```

In the above example, "little", "minor", "slight", and "small" would all be considered to have the same rank.

The "values" element for each noun contains more detail about each adjective - in alphabetical order. Multiple synsets may exist for each adjective. Please note that the "def" contents derive from the "stanford_wordnet_nltk_corpus" project - see https://github.com/colingoldberg/stanford_wordnet_nltk_corpus - that are different from the original wordnet corpus.

Other elements, such as "nnixs" and "nodes" can be safely ignored for the purposes of this repository.

This project is ongoing. I hope that you will consider this collection as useful as I do. Please contribute nouns and associated adjectives, as well as any comments or suggestions, via the issues tab.

