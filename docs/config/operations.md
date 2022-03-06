# Operations

There are a variety of Library Operations that can be utilized in a library.

Within each library, operations can be defined by using the `operations` attribute, as demonstrated below.

```yaml
libraries:
  Movies:
    metadata_path:
      - git: meisnate12/MovieCharts
    operations:
      mass_critic_rating_update: tmdb
      split_duplicates: true
```

The available attributes for the operations attribute are as follows

| Attribute                                                     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|:--------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `assets_for_all`                                              | Search in assets for images for every item in your library.<br>**Values:** `true` or `false`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `delete_collections_with_less`                                | Deletes every collection with less than the given number of items.<br>**Values:** number greater then 0                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `delete_unmanaged_collections`                                | Deletes every unmanaged collection<br>**Values:** `true` or `false`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `mass_genre_update`                                           | Updates every item's genres in the library to the chosen site's genres<br>**Values:** <table class="clearTable"><tr><td>`tmdb`</td><td>Use TMDb for Genres</td></tr><tr><td>`tvdb`</td><td>Use TVDb for Genres</td></tr><tr><td>`omdb`</td><td>Use IMDb through OMDb for Genres</td></tr></table>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `mass_content_rating_update`                                  | Updates every item's content rating in the library to the chosen site's genres<br>**Values:** <table class="clearTable"><tr><td>`mdb`</td><td>Use MdbList for Content Ratings</td></tr><tr><td>`mdb_commonsense`</td><td>Use Commonsense Rating through MDbList for Content Ratings</td></tr><tr><td>`omdb`</td><td>Use IMDb through OMDb for Content Ratings</td></tr></table>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `mass_audience_rating_update`/<br>`mass_critic_rating_update` | Updates every item's audience/critic rating in the library to the chosen site's rating<br>**Values:** <table class="clearTable"><tr><td>`tmdb`</td><td>Use TMDb Rating</td></tr><tr><td>`omdb`</td><td>Use IMDbRating through OMDb</td></tr><tr><td>`mdb`</td><td>Use MdbList Score</td></tr><tr><td>`mdb_imdb`</td><td>Use IMDb Rating through MDbList</td></tr><tr><td>`mdb_metacritic`</td><td>Use Metacritic Rating through MDbList</td></tr><tr><td>`mdb_metacriticuser`</td><td>Use Metacritic User Rating through MDbList</td></tr><tr><td>`mdb_trakt`</td><td>Use Trakt Rating through MDbList</td></tr><tr><td>`mdb_tomatoes`</td><td>Use Rotten Tomatoes Rating through MDbList</td></tr><tr><td>`mdb_tomatoesaudience`</td><td>Use Rotten Tomatoes Audience Rating through MDbList</td></tr><tr><td>`mdb_tmdb`</td><td>Use TMDb Rating through MDbList</td></tr><tr><td>`mdb_letterboxd`</td><td>Use Letterboxd Rating through MDbList</td></tr></table> |
| `mass_trakt_rating_update`                                    | Updates every movie/show's user rating in the library to match your custom rating on Trakt if there is one<br>**Values:** `true` or `false`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `mass_collection_mode`                                        | Updates every Collection in your library to the specified Collection Mode<br>**Values:** `default`: Library default<br>`hide`: Hide Collection<br>`hide_items`: Hide Items in this Collection<br>`show_items`: Show this Collection and its Items<table class="clearTable"><tr><td>`default`</td><td>Library default</td></tr><tr><td>`hide`</td><td>Hide Collection</td></tr><tr><td>`hide_items`</td><td>Hide Items in this Collection</td></tr><tr><td>`show_items`</td><td>Show this Collection and its Items</td></tr></table>                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `update_blank_track_titles `                                  | Search though every track in a music library and replace any blank track titles with the tracks sort title<br>**Values:** `true` or `false`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `split_duplicates`                                            | Splits all duplicate movies/shows found in this library<br>**Values:** `true` or `false`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `radarr_add_all`                                              | Adds every item in the library to Radarr. The existing paths in plex will be used as the root folder of each item, if the paths in Plex are not the same as your Radarr paths you can use the `plex_path` and `radarr_path` [Radarr](radarr) details to convert the paths.<br>**Values:** `true` or `false`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `radarr_remove_by_tag`                                        | Removes every item from Radarr with the Tags given<br>**Values:** List or comma separated string of tags                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `sonarr_add_all`                                              | Adds every item in the library to Sonarr. The existing paths in plex will be used as the root folder of each item, if the paths in Plex are not the same as your Sonarr paths you can use the `plex_path` and `sonarr_path` [Sonarr](sonarr) details to convert the paths.<br>**Values:** `true` or `false`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `sonarr_remove_by_tag`                                        | Removes every item from Sonarr with the Tags given<br>**Values:** List or comma separated string of tags                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `genre_mapper`                                                | Allows genres to be changed to other genres or be removed from every item in your library.<br>**Values:** [see below for usage](#genre-mapper)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `metadata_backup`                                             | Creates/Maintains a PMM [Metadata File](../metadata/metadata) with a full `metadata` mapping based on the library's items locked attributes.<br>**Values:** [see below for usage](#metadata-backup)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

## Genre Mapper

You can use the `genre_mapper` operation to map genres in your library.

Each attribute under `genre_mapper` is a separate mapping and has two parts.
* The key (`Action` in the example below) is what the genres will end up as.
* The value(`Action/Adventure, Action & Adventure` in the example below) is what genres you want mapped to the key.

So this example will change go through every item in your library and change the genre `Action/Adventure` or `Action & Adventure` to `Action` and `Romantic Comedy` to `Comedy`.

```yaml
library:
  Movies:
    operations:
      genre_mapper:
        Action: Action/Adventure, Action & Adventure
        Comedy: Romantic Comedy
```

you can also use a list:

```yaml
library:
  Movies:
    operations:
      genre_mapper:
        Action:
         - Action/Adventure
         - Action & Adventure
        Comedy: Romantic Comedy
```

To just Remove a Genre without replacing it just set the Genre to nothing like this.

```yaml
library:
  Movies:
    operations:
      genre_mapper:
        Action: Action/Adventure, Action & Adventure
        Romantic Comedy:
```

This example will change go through every item in your library and change the genre `Action/Adventure` or `Action & Adventure` to `Action` and remove every instance of the Genre `Romantic Comedy`.


## Metadata Backup 

Creates/Maintains a Plex Meta Manager [Metadata File](../metadata/metadata) with a full `metadata` mapping based on the library's items locked attributes.

If you point to an existing Metadata File then PMM will Sync the changes to the file, so you won't lose non plex changes in the file.

There are a few different options to determine how the `metadata_backup` works.

| Attribute           | Description                                                                                                                                                         |
|:--------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `path`              | Path to where the metadata will be saved/maintained<br>**Default:** <<library_name>>_Metadata_Backup.yml in your config folder<br>**Values:** Path to Metadata File |
| `exclude`           | Exclude all listed attributes from being saved in the metadata file<br>**Values:** Comma-separated string or list of attributes                                     |
| `sync_tags`         | All Tag Attributes will have the `.sync` option and blank attribute will be added to sync to as well<br>**Default:** `false`<br>**Values:** `true` or `false`       |
| `add_blank_entries` | Will add a line for entries that have no metadata changes<br>**Default:** `true`<br>**Values:** `true` or `false`                                                   |