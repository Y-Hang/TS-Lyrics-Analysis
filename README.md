# Taylor Swift Lyrics Anlysis: *From Country Love Story to Pop Bad Blood*

With AMA's *Artist of the Decade* award, Billboard's *Women of the Decade* award, CMA's *Pinnacle Award*, and 2 Grammy's *Album of the Year*, Taylor Swift is undoubtedly one of the most successful artists of the 2010s decade. Interestingly, Taylor debuted as a country singer and pocketed her first Grammy Album of the Year with country album *Fearless*. Then her career gradually shifted towards pop music and she crowned herself a second Grammy Album of the Year with pop ablum *1989*. Massive media coverage of Taylor's success in both country and pop music almost makes this topic a cliche, but the lyrics of her songs can provide us with a more unmediated and detailed perspective to observe the evolution of this country-to-pop crossover princess.

This project analyzed the lyrics of 112 songs (including bonus tracks but not voice memos in deluxe versions) from Taylor Swift's 7 studio albums (*self-titled*, *Fearless*, *Speak Now*, *Red*, *1989*, *reputation*, and *Lover*). The lyrics data is compiled from [Kaggle](https://www.kaggle.com/PromptCloudHQ/taylor-swift-song-lyrics-from-all-the-albums) (including her first 6 studio albums) and [Azlyrics](https://www.azlyrics.com/) (including her newest album *Lover*).

**Table of Content**\
[Part I: Datasets Overview & Data Preprocessing](#Part-T-Datasets-Overview--Data-Preprocessing)\
[Part II: Exploratory Data Analysis](#Part-II-Exploratory-Data-Analysis)\
[Part III: TF-IDF Analysis](#Part-III-TF-IDF-Analysis)\
[Part IV: LDA with Jensen-Shannon Distance](#Part-IV-LDA-with-Jensen-Shannon-Distance)\
[Part V: Word Mover's Distance](#Part-V-Word-Movers-Distance)

## Part I: Datasets Overview & Data Preprocessing
The lyrics data from [Kaggle](https://www.kaggle.com/PromptCloudHQ/taylor-swift-song-lyrics-from-all-the-albums) was stored in a clean and structured csv file where each row was a line of a song:\
![Original_kaggle_file_head](/images/original_kaggle_file_head.png)

In our analysis, each single song functions as an observation and we only need the *lyrics*, *album title* and *track title* information of each song. So I grouped the original data by track title and kept wanted columns. Below is what I got:\
![Grouped_kaggle_file_head](/images/grouped_kaggle_file_head.png)

However, this dataset did not contain the lyrics from Taylor's latest album *Lover*. I found a lyrics website [Azlyrics](https://www.azlyrics.com/) and used *BeautifulSoup* and *requests* in *Python* to scrape the lyrics of album *Lover*. After removing the line breaks (\r, \n) in the scraped data, the lyrics looked like below picture:\
![Cleaned_azlyrics_file_head](/images/cleaned_azlyrics_file_head.png)

I appended these two datasets together and got the final dataset, which was structured exactly the same as above two datasets and thus was not shown here.

So far, we have collected all wanted lyrics data. So I built a customized `preprocess()` function to lowercase all lyrics, remove punctuations and special characters, count total words of each song, remove stopwords (after counting total words), stem the lyrics, and count the number of unique words in each song. The results below were sorted descendingly by total words count:\
![Preprocessed_final_file_head_sorted](/images/preprocessed_final_file_head_sorted.png)
- *lyric_all* is the full lyrics without punctuations and special characters
- *total_count* is the count of total words in a song, or the length of *lyric_all*
- *lyric* is the unique words in *lyric_all*
- *unique_count* is the count of unique words in a song, or the length of *lyric*
- *uniqueness* is the ratio of *unique_count* over *total_count* to measure the redundancy of lyrics

## Part II: Exploratory Data Analysis
## Part III: TF-IDF Analysis
## Part IV: LDA with Jensen-Shannon Distance
## Part V: Word Mover's Distance
