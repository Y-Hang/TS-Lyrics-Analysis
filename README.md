# Taylor Swift Lyrics Analysis: *How Love Story becomes Bad Blood*

With AMA's *Artist of the Decade* award, Billboard's *Women of the Decade* award, CMA's *Pinnacle Award*, and 2 Grammy's *Album of the Year*, Taylor Swift is undoubtedly one of the most successful artists of the 2010s decade. Interestingly, Taylor debuted as a country singer and pocketed her first Grammy Album of the Year with country album *Fearless*. Then her career gradually shifted towards pop music and she crowned herself a second Grammy Album of the Year with pop ablum *1989*. Thought there have been nonstop discussions and media coverage on the comparison between the *country Taylor* and the *pop Taylor*, the lyrics of her songs can still provide us with a more unmediated and less-touched perspective to observe the evolution of this country-to-pop crossover princess.

This project analyzed the lyrics of 112 songs (including bonus tracks but not voice memos in deluxe versions) from Taylor Swift's 7 studio albums (*self-titled*, *Fearless*, *Speak Now*, *Red*, *1989*, *reputation*, and *Lover*). [Highlight of the goal: text similarity, and methods of this project]

**Table of Content**\
[Part I: Datasets Overview & Data Preprocessing](#Part-I-Datasets-Overview--Data-Preprocessing)\
[Part II: Exploratory Data Analysis](#Part-II-Exploratory-Data-Analysis)\
[Part III: TF-IDF Analysis](#Part-III-TF-IDF-Analysis)\
[Part IV: LDA with Jensen-Shannon Distance](#Part-IV-LDA-with-Jensen-Shannon-Distance)\
[Part V: Word Mover's Distance](#Part-V-Word-Movers-Distance)

## Part I: Datasets Overview & Data Preprocessing
The lyrics data was compiled from [Kaggle](https://www.kaggle.com/PromptCloudHQ/taylor-swift-song-lyrics-from-all-the-albums) (including Taylor's first 6 studio albums) and [Azlyrics](https://www.azlyrics.com/) (including Taylor's latest album *Lover*). The [Kaggle](https://www.kaggle.com/PromptCloudHQ/taylor-swift-song-lyrics-from-all-the-albums) data was stored in a clean and structured csv file where each row was a line of a song. But in our analysis, each single song functions as an observation, and we only need the *lyrics*, *album title* and *track title* of each song. So I grouped the original data by track title and kept wanted columns. Below is what I got:\
![Grouped_kaggle_file_head](/images/grouped_kaggle_file_head.png)

However, this dataset did not contain the lyrics from Taylor's latest album *Lover*. I found a lyrics website [Azlyrics](https://www.azlyrics.com/) and used *BeautifulSoup* and *requests* in *Python* to scrape the lyrics of album *Lover*. After removing the line breaks (\r, \n) in the scraped data, the lyrics looked like below picture:\
![Cleaned_azlyrics_file_head](/images/cleaned_azlyrics_file_head.png)

Appending the above two datasets together, we got the data for preprocessing. I built a customized `preprocess()` function to:
1. Lowercase all lyrics.
2. Remove punctuations and special characters.
3. Count total words of each song.
4. Remove stopwords (after counting total words).
5. Stem the lyrics.
6. Count the number of unique words in each song.

Applying the `preprocess()` funtion to our data, we got the following output (the results below were sorted descendingly by total words count):\
![Preprocessed_final_file_head_sorted](/images/preprocessed_final_file_head_sorted.png)
- *lyric_all* is the full lyrics without punctuations and special characters
- *total_count* is the count of total words in a song, or the length of *lyric_all*
- *lyric* is the lyrics words without punctuations, special characters and stopwords
- *unique_count* is the count of unique words in column *lyric*
- *uniqueness* is the ratio of *unique_count* over *total_count* to measure the redundancy of lyrics

## Part II: Exploratory Data Analysis
Total words by song-album
![Total Words by Song Album](/images/total_words_by_song_album.png)

<script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
<div id="cd52e831-399a-403d-9bb2-0c56214b1d38" style="height: 100%; width: 100%;" class="plotly-graph-div"></div>
<script type="text/javascript">window.PLOTLYENV=window.PLOTLYENV || {};window.PLOTLYENV.BASE_URL="https://plot.ly";Plotly.newPlot("cd52e831-399a-403d-9bb2-0c56214b1d38", [{"type": "pie", "values": [4500, 2500, 1053, 500], "labels": ["Oxygen", "Hydrogen", "Carbon_Dioxide", "Nitrogen"]}], {}, {"linkText": "Export to plot.ly", "showLink": true})</script>

![Uniqueness by Song Album](/images/uniqueness_by_song.html)

## Part III: TF-IDF Analysis
## Part IV: LDA with Jensen-Shannon Distance
## Part V: Word Mover's Distance