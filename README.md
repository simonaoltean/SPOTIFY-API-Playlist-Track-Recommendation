# SPOTIFY API Playlist Track Recommendation
Using [Spotify](https://www.spotify.com/)'s API, this short program is designed to take in the choice of a category on Spotify such as Top Lists, Hip-Hop, Pop, Summer, etc., analysing the tracks in this category based on several features and creating a tracklist from the playlists in that category. This program can be used by DJ's to create tracklists following BPM rank, or anyone looking to quickly create a mix with a smooth flow between songs. The tracks are first ranked by popularity (picking popular songs first), then, using Spotify's audio analysis and audio features, multiple data points are collected by the program such as tempo, duration, energy, key, danceability, and more. These features are reduced to three dimensions using scikit-learn's [PCA](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html) dimensionality reduction, retaining the tempo variable. The plot below shows the tracks extracted from the playlists within the category selected.

![dance_plot](https://github.com/simonaoltean/SPOTIFY-API-Playlist-Track-Recommendation/assets/113261870/2b2b5660-3351-490f-8805-16d1375978f2)
##[Watch the demo video.](https://drive.google.com/file/d/1Vpj2j8nD7s0SeXEx5tzWFV6lH6t8luY-/view?usp=sharing)

There is also an option to customize the playlists by pasting the links to the playlists you'd like to include instead of picking a general category of music. The duration of the playlist can be edited in hours, where an hour and 30 minutes would be 1.5 hours. Next, the program uses Sklearn's [KMmeans](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) and [agglomerative clustering](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.AgglomerativeClustering.html) to recommend the next track from a starting point of a track with low BPM (tempo), and moves on to the next cluster of the same label (or color in the plot above) until all the tracks from one cluster have been added to the playlists/tracklist.

Finally, the user can create a playlist on their Spotify account, giving the playlist a name and description. The songs are added in the same order of recommendation, meaning that they are clustered by tempo and two other meaningful audio features.

## User Guide
To use this app, you must first register an app on the [Spotify developer page](https://developer.spotify.com/dashboard/create) using your personal Spotify account, using the redirect URI of "https://example.com/callback" as shown in the image below. Also type in an app name and short description (you can leave out the website).

![spotify_app](https://github.com/simonaoltean/SPOTIFY-API-Playlist-Track-Recommendation/assets/113261870/d34f6810-98e8-4533-a422-c591afcfcc4c)

Take note of your Client ID and Secret Key. As you run the cells of the program, it will ask you to input that information. Run all the cells in the jupyter notebook file, opening the file using either [Google Colab](https://colab.research.google.com/), or [Virtual Studio Code](https://code.visualstudio.com/Download). When creating your playlist, a page will open at the example website where you can give your spotify app permission to access and account and create a playlist in your place. Then, copy the link of the page and paste it back into the program. You now have a custom recommendedtion playlist created!
