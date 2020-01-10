# Taylor Swift Lyrics Anlysis: *From Country Love Story to Pop Bad Blood*

With AMA's *Artist of the Decade* award, Billboard's *Women of the Decade* award, CMA's *Pinnacle Award*, and 2 Grammy's *Album of the Year*, Taylor Swift is undoubtedly one of the most successful artists of the 2010s decade. Interestingly, Taylor debuted as a country singer and pocketed her first Grammy Album of the Year with country album *Fearless*. Then her career gradually shifted towards pop music and she crowned herself a second Grammy Album of the Year with pop ablum *1989*. Massive media coverage of Taylor's success in both country and pop music almost makes this topic a cliche, but the lyrics of her songs can provide us with a more unmediated and detailed perspective to observe the evolution of this country-to-pop crossover princess.

This project analyzed the lyrics of 112 songs (including bonus tracks but not voice memos in deluxe versions) in Taylor Swift's 7 studio albums (*self-titled*, *Fearless*, *Speak Now*, *Red*, *1989*, *reputation*, and *Lover*). The lyrics data is compiled from [Kaggle](https://www.kaggle.com/PromptCloudHQ/taylor-swift-song-lyrics-from-all-the-albums) (including her first 6 studio albums) and [Azlyrics](https://www.azlyrics.com/) (including her newest album *Lover*).

**Table of Content**\
[Part I: Datasets Overview & Data Preprocessing](#Part-T-Datasets-Overview--Data-Preprocessing)\
[Part II: Exploratory Data Analysis](#Part-II-Exploratory-Data-Analysis)\
[Part III: TF-IDF Analysis](#Part-III-TF-IDF-Analysis)\
[Part IV: LDA with Jensen-Shannon Distance](#Part-IV-LDA-with-Jensen-Shannon-Distance)\
[Part V: Word Mover's Distance](#Part-V-Word-Movers-Distance)

## Part I: Datasets Overview & Data Preprocessing
The lyrics data from [Kaggle](https://www.kaggle.com/PromptCloudHQ/taylor-swift-song-lyrics-from-all-the-albums) is stored in a clean and structured csv file where each row is a line of a song:
![Original_kaggle_file_head](/images/original_kaggle_file_head.png)

However, this dataset does not contain the lyrics from Taylor's latest album *Lover*. So I found a lyrics website [Azlyrics](https://www.azlyrics.com/) and used *BeautifulSoup* and *requests* in *Python* to scrape the lyrics of *Lover*. This is what I got:
![Original_azlyrics_file_head](/images/original_azlyrics_file_head.png)

## Part II: Exploratory Data Analysis
## Part III: TF-IDF Analysis
## Part IV: LDA with Jensen-Shannon Distance
## Part V: Word Mover's Distance
