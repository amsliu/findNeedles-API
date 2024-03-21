---
title: "Overview of findNeedles APIs"
description: "API reference documentation for the Java function findNeedles"
author: "AmsonLiu"
doc_type: API_reference
date: 03/20/2024
---

# Overview of findNeedles APIs

findNeedles is a Java function that prints a certain output depending on your input. There are a few important parameters to consider. 

1) **haystack** - This is a string input of word(s).
2) **needles** - This is a string array input that stores up to five words.

Consider the scenario where you input more than five words in the paramenter needles. The function will print the error message *"Too many words!"* because the length of needles has exceeded five words.

If else, the parameter haystack is split into an array of words and compared to the words in the parameter needles. The countArray variable specifies how many times a word in haystack appears in needles, and the  for loop counts the number of matches in haystack. The function will then print out each word in needles and the number of matches in haystack.

For example, when you input haystack = "I like to play soccer" and needles = "soccer player", the expected outcome will print:

soccer: 1 <br>
player: 0

> [!NOTE]
> With the exception of whitespace, this function does not disregard special characters when comparing a word in haystack with a word in needles. For example, if you input the *"Hello!"* in haystack, this function will not consider it to be an match with *"Hello"* in needles.

```json
⁄⁄Sample snippet for the API code

public static void findNeedles(String haystack, String[] needles){
if(needles.length > 5){
	System.err.println("Too many words!");
}

else{
	int[] countArray = new int[needles.length];
	for(int i = 0; i < needles.length; i++){
		String[] words = haystack.split("[ \"\'\t\n\b\f\r]", 0);
		for(int j = 0; j < words.length; j++){
			if(words[j].compareTo(needles[i]) == 0){
				countArray[i]++;
			}
		}
	}
	for (int j = 0; j < needles.length; j++) {
		System.out.println(needles[j] + ": " + countArray[j]);
	}
}
}

```




