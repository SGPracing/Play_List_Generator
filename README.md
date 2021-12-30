# Play List Generator

## Data ##
Dataset: https://www.kaggle.com/lukaszamora/history-of-rock-19502020?select=history-of-rock-spotify+-+Copy.csv (history-of-rock-spotify.csv) <br />

## Objective ##
To build a code with a multistep interaction with the user, so a play list can be generated afterwards, based on the 'History Of Rock' dataframe.

## Methods ##
The dataset was of good quality, not needing any further specific cleaning. The analysis and some columns chracterization was performed under *Python* and *Pandas*, and saved in new dataset to be manipulated. The characterized columns were 'valence', 'release_date', 'energy', 'danceability' and 'popuplarity'.

## Categorizing columns ##
In order to give the user the possibility to choose some of the charactristics of the tracks to be included in the play list, some relevant columns were choosen to be categorized, as follows:

### 1. Release date (release_date) ###
This columns specifies the year the track was released.<br />
The categorization was based on decades, from 1950s to 2010s (this last one including the year 2020).<br />
The user is asked to choose a specific decade, following the input instructions.

### 2. Valence (valence) ###
This column grades the 'mood' of the song. 'A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).'<br />
These values where categorized in 3 braches using the 30% and 70% quantiles as cut offs.

### 3. Energy (energy) ###
In this collumns, 'a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy.'<br />
These values where also categorized in 3 braches using the 30% and 70% quantiles as cut offs.

### 4. Danceability (danceability) ###
'Describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable.'<br />
In this case, the 70% quantile cut off was used, meanig, songs over this quantile was considered suitable for dancing.

### 5. 

