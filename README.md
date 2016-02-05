# matching_script
Modification of fuzzy search for parsing Conm and Compustat databases for Research on Firm Aquisitions


#How it works
The matching was done using a fuzzy search implementation in javascript that leveraged the fuzzy search library Fuse.js (http://kiro.me/projects/fuse.html). This library takes in a single string and fuzzy searches against a dataset of user-provided strings. However, since the datasets was very large ( > 20,000 entries on average), the algorithm had to be optimized and automated to match the data efficiently. I used the structure of the data to design the implementation of the algorithm. For example, because each observation was a company name whose first two letters rarely changed, the search algorithm hard searches on the first two letters of the input string, and then fuzzy search the remaining letters to account for changes in suffixes (“Inc.”->”Incorporated”) or addition of spaces, dashes, or commas between the remaining letters (“Acrymed Inc” -> “AcryMed, Inc.”).The sensitivity of the fuzzy search was tuned in order to exclude the false positive matches like “AeroGen Inc” -> “Aesgen, Inc.”
