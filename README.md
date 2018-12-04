# Datasets created for the EURO CSS Data Challenge
## Base file with the search query and results (hash)
- File: all_people_hap*.zip (extract by "unzip -p 'all_people_hap*.zip' | cat > all_people_hap.tsv")
- Columns:
geo_location:
keyword: search term
language: language of user
login_status: logged in into google
plugin_id: plugin id
plugin_version: plugin version
result_hash: hash result of search
search_date: search date
search_type: google news or google search
user: user id
geo_location2: postal code
const_i: constituency id (can be linked to number of votes)
day: day of search
av_haps_all: average happiness of the text in the links
std_haps_all: std of the average happiness of the text in the links
count_haps_all: number of articles with info on text
count_ideo_all: number of articles with info on ideology
user2: concatenation of user + login_status (sometimes it can log out)
{party}_ideo: average ideology of the party {party} in the links. 0 = links never shared by {party}. 1 = links only shared by {party}
{party}_std_ideo: std of the ideology of the party {party} in teh text of the links

## Conversion table hash to links
- Large file, download from the datapende website or email garcia@uva.nl


## Ideology of each link
Based on the Twitter activity of politicians and organizations
- File: ideology_media.tsv
- Columns:
party: \in (AfD 	CDU 	CSU 	FDP 	Grüne 	Linke 	SPD)
netloc: netloc of link (e.g. instagram, zeit or faz)
count_netloc: number of tiems the netloc has been shared
count: number of times it has been shared by the party
count_p: number of times the party has shared a link
ratio: fraction of times the link has been shared by the party (count/count_p)
sum_netloc: sum of ratios of netloc by all parties (normalization constant)
ideology: ratio/sum_netloc

## Text in the links
- File: link_text_*.zip (extract using: "unzip -p 'all_text_links_*.zip' | cat > all_text_links.tsv")
- Columns:
Link_original: Original link
Link_obtained: Link returned by website
Text: Raw text in website


## Happiness of the text in the links
- File: links_happiness_language.tsv 
- Language and happiness of the text in the links, using labMTsimple.storyLab  and detect_language
- Columns (no header!): 
Original link
Language
Raw mean happiness
Raw STD of happiness
Weigthed average of happiness (weight = TFIDF score of word)
Weighted STD of happiness (weight = TFIDF score of word)
Empty column (placeholder for other measures of happiness)
Empty column (placeholder for other measures of happiness)
Empty column (placeholder for other measures of happiness)
Empty column (placeholder for other measures of happiness)
Length of text



## Votes by constituency
- File: votes_by_constituency.tsv
- From website: https://www.bundeswahlleiter.de/en/bundestagswahlen/2017/ergebnisse/bund-99/land-{}.html ({} is a number from 1 to 16, both included)
- Columns:
col: Political party
state_i: State id
state: State name
constituency: Consituency name
constituency_i: Consituency id
num2: Number of votes
diff2: Difference in percentage points from last election
vote_const: Total votes in the constituency
perc: Percentage of votes



