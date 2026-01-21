**To Do**:
- Go over contribution statements
- Go over errors
- Make script for creating list of ids for repeated experiments
- Make script for extracting bad dois
- Back down timeout to lower time and compare grabbed statements

**Changes To Code**:
- Add additional 'journal-article' type check - done
- Add landing and pdf url the same check - done
- Add additional language check on abstract (greek letters should be fine, could do percentage base)
	- Possibly use python langdetect
- Add sciencedirect landing-only parse, just set pdf_url to None

**Statistics Notes**:
- ~29% of papers had failed requests - means I can likely add many dois into blacklisted set
- Of papers with succesful requests, ~7% contribution rate (dates range from 1990s to 2025 from what I saw so this matches the rate which is expected - similar to S3 bucket extraction)
- big amount of contribution statements found from sciencedirect alone
	- 21% of found statements, but ~16% of science direct links had statements

**General Notes**:
- Somehow got a video?
- Still ending up with papers of different languages