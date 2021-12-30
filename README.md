# Play List Generator

## Data ##
Dataset: https://www.kaggle.com/lukaszamora/history-of-rock-19502020?select=history-of-rock-spotify+-+Copy.csv (history-of-rock-spotify.csv) <br />

## Objective ##
To build a code with a multistep interaction with the user, so a play list can be generated afterwards, based on the 'History Of Rock' dataframe.

## Methods ##
The dataset was of good quality, not needing any further specific cleaning. To achieve compatibility with https://soundiiz.com/, the column 'name' is renamed as 'title'.<br />
The analysis and some columns chracterization was performed under *Python* and *Pandas*, and saved in new dataset to be manipulated. The characterized columns were 'valence', 'release_date', 'energy', 'danceability' and 'popuplarity'.

## Categorizing columns ##
In order to give the user the possibility to choose some of the charactristics of the tracks to be included in the play list, some relevant columns were choosen to be categorized, as follows:

### 1. Release date  ###
This columns specifies the year the track was released.<br />
The categorization was based on decades, from 1950s to 2010s (this last one including the year 2020).<br />
The user is asked to choose a specific decade, following the input instructions.

### 2. Valence ###
This column grades the 'mood' of the song. 'A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).'<br />
These values where categorized in 3 braches using the 30% and 70% quantiles as cut offs.

### 3. Energy ###
In this collumns, 'a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy.'<br />
These values where also categorized in 3 braches using the 30% and 70% quantiles as cut offs.

### 4. Danceability ###
'Describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable.'<br />
In this case, the 70% quantile cut off was used, meanig, songs over this quantile was considered suitable for dancing.

### 5. Popularity ###
This columns specifies the popularity of the track. The value is between 0 and 100, with 100 being the most popular.<br />
In this categorization, a pupular song was consider when it's score was over the mean value, that is over the 50% quantile.

## Play List Generator Function ##

### Choices ###
The first choice the user makes is the number of tracks he/she would like to have in the playlist.<br />
Afterwards, the choices follow the sequence: *release date, valence, energy, popularity and danceability.*<br />
For the first three choices, the user is fisrtly asked if he/she wants to make that category a filter for the playlist. If a negative answer is given, the category is ignored for the purpose of the playlist, meaning that no track is excluded based on that specif category.<br />
For *popularity* and *danceability*, the user is asked if those parameters (tracks being popular and/or suitable for dancing) is something that is of importance building the playlist. If a positive answer is given for each, only popular songs and dancebke songs will be included in the playlist, otherwise, no track would be excluded based on those categories.<br />

### Generating the playlist ###

After all choices have been made, a table with tracks title and respective artist is shown. This table is generated based on the number of tracks the user whisehd to have in the playlist, chosen at the begging. If the resulted dataframe has more tracks, the final list will be a sample based on the number of tracks chosen. Otherwise, it will show the entire resulted dataframe. <br />
Finally, the user is asked if the playlist should be saved. If so, a file *playlist.csv* is saved (with ';' separator). If the answer is negative, the user is aked if he/she would like to run the code again to generate a new list.

### Making use of the *playlist.csv* ###
As a suggestion, the user may take advantage of **Soundiiz* (https://soundiiz.com/tutorial), free of charge, where a playlist can be generated from the *playlist.csv*, and further integrated within the user's favorite interface (e.g. Spotfy, iTunes etc).



