---
layout: default
title: Method Reference - SpotifyWebAPI
---


### __construct

    void SpotifyWebAPI\SpotifyWebAPI::__construct(\SpotifyWebAPI\Request $request)

Constructor
Set up Request object.



#### Arguments
* $request **\SpotifyWebAPI\Request** - Optional. The Request object to use.


#### Return values
* **void** 



### addMyTracks

    boolean SpotifyWebAPI\SpotifyWebAPI::addMyTracks(string|array $tracks)

Add tracks to the current user's Spotify library.

Requires a valid access token.
https://developer.spotify.com/web-api/save-tracks-user/

#### Arguments
* $tracks **string\|array** - ID(s) of the track(s) to add.


#### Return values
* **boolean** Whether the tracks was successfully added.



### addUserPlaylistTracks

    boolean SpotifyWebAPI\SpotifyWebAPI::addUserPlaylistTracks(string $userId, string $playlistId, string|array $tracks, array|object $options)

Add tracks to a user's playlist.

Requires a valid access token.
https://developer.spotify.com/web-api/add-tracks-to-playlist/

#### Arguments
* $userId **string** - ID of the user who owns the playlist.
* $playlistId **string** - ID of the playlist to add tracks to.
* $tracks **string\|array** - ID(s) of the track(s) to add.
* $options **array\|object** - Optional. Options for the new tracks.
    * int position Optional. Zero-based position of where in the playlist to add the tracks. Tracks will be appened if omitted or false.



#### Return values
* **boolean** Whether the tracks was successfully added.



### createUserPlaylist

    array|object SpotifyWebAPI\SpotifyWebAPI::createUserPlaylist(string $userId, array|object $data)

Create a new playlist for a user.

Requires a valid access token.
https://developer.spotify.com/web-api/create-playlist/

#### Arguments
* $userId **string** - ID of the user to create the playlist for.
* $data **array\|object** - Data for the new playlist.
    * name string Required. Name of the playlist.
    * public bool Optional. Whether the playlist should be public or not.



#### Return values
* **array\|object** The new playlist. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### deleteMyTracks

    boolean SpotifyWebAPI\SpotifyWebAPI::deleteMyTracks(string|array $tracks)

Delete tracks from current user's Spotify library.

Requires a valid access token.
https://developer.spotify.com/web-api/remove-tracks-user/

#### Arguments
* $tracks **string\|array** - ID(s) of the track(s) to delete.


#### Return values
* **boolean** Whether the tracks was successfully deleted.



### deletePlaylistTracks

    string|boolean SpotifyWebAPI\SpotifyWebAPI::deletePlaylistTracks(string $userId, string $playlistId, array $tracks, string $snapshotId)

Delete tracks from a playlist and retrieve a new snapshot ID.

Requires a valid access token.
https://developer.spotify.com/web-api/remove-tracks-playlist/

#### Arguments
* $userId **string** - ID of the user who owns the playlist.
* $playlistId **string** - ID of the playlist to delete tracks from.
* $tracks **array** - Array of arrays with tracks to delete and optional position in the playlist where the track is located.
    * id string Required. Spotify track ID.
    * position array Optional. Position of the track in the playlist.

* $snapshotId **string** - Optional. The playlist&#039;s snapshot ID.


#### Return values
* **string\|boolean** A new snapshot ID or false if the tracks weren&#039;t deleted.



### getAlbum

    array|object SpotifyWebAPI\SpotifyWebAPI::getAlbum(string $albumId)

Get a album.

https://developer.spotify.com/web-api/get-album/

#### Arguments
* $albumId **string** - ID of the album.


#### Return values
* **array\|object** The requested album. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getAlbums

    array|object SpotifyWebAPI\SpotifyWebAPI::getAlbums(array $albumIds)

Get multiple albums.

https://developer.spotify.com/web-api/get-several-albums/

#### Arguments
* $albumIds **array** - IDs of the albums.


#### Return values
* **array\|object** The requested albums. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getAlbumTracks

    array|object SpotifyWebAPI\SpotifyWebAPI::getAlbumTracks(string $albumId, array|object $options)

Get a album's tracks.

https://developer.spotify.com/web-api/get-several-albums/

#### Arguments
* $albumId **string** - ID of the album.
* $options **array\|object** - Optional. Options for the tracks.
    * int limit Optional. Limit the number of tracks.
    * int offset Optional. Number of tracks to skip.



#### Return values
* **array\|object** The requested album tracks. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getArtist

    array|object SpotifyWebAPI\SpotifyWebAPI::getArtist(string $artistId)

Get an artist.

https://developer.spotify.com/web-api/get-artist/

#### Arguments
* $artistId **string** - ID of the artist.


#### Return values
* **array\|object** The requested artist. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getArtists

    array|object SpotifyWebAPI\SpotifyWebAPI::getArtists(array $artistIds)

Get multiple artists.

https://developer.spotify.com/web-api/get-several-artists/

#### Arguments
* $artistIds **array** - IDs of the artists.


#### Return values
* **array\|object** The requested artists. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getArtistRelatedArtists

    array|object SpotifyWebAPI\SpotifyWebAPI::getArtistRelatedArtists(string $artistId)

Get an artist's related artists.

https://developer.spotify.com/web-api/get-related-artists/

#### Arguments
* $artistId **string** - ID of the artist.


#### Return values
* **array\|object** The artist&#039;s related artists. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getArtistAlbums

    array|object SpotifyWebAPI\SpotifyWebAPI::getArtistAlbums(string $artistId, array|object $options)

Get an artist's albums.

https://developer.spotify.com/web-api/get-artists-albums/

#### Arguments
* $artistId **string** - ID of the artist.
* $options **array\|object** - Optional. Options for the albums.
    * array album_type Optional. Album types to return. If omitted, all album types will be returned.
    * string market Optional. A ISO 3166-1 alpha-2 country code. Limit the results to tracks that are playable in this market.
    * int limit Optional. Limit the number of albums.
    * int offset Optional. Number of albums to skip.



#### Return values
* **array\|object** The artist&#039;s albums. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getArtistTopTracks

    array|object SpotifyWebAPI\SpotifyWebAPI::getArtistTopTracks(string $artistId, string $country)

Get an artist's top tracks in a country.

https://developer.spotify.com/web-api/get-artists-top-tracks/

#### Arguments
* $artistId **string** - ID of the artist.
* $country **string** - An ISO 3166-1 alpha-2 country code specifying the country to get the top tracks for.


#### Return values
* **array\|object** The artist&#039;s top tracks. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getFeaturedPlaylists

    array|object SpotifyWebAPI\SpotifyWebAPI::getFeaturedPlaylists(array|object $options)

Get Spotify featured playlists.

Requires a valid access token.
https://developer.spotify.com/web-api/get-list-featured-playlists/

#### Arguments
* $options **array\|object** - Optional. Options for the playlists.
    * string locale Optional. An lowercase ISO 639 language code and an uppercase ISO 3166-1 alpha-2 country code. Separated by an underscore. Show playlists in this language.
    * string country Optional. An ISO 3166-1 alpha-2 country code. Show playlists from this country.
    * string timestamp Optional. A ISO 8601 timestamp. Show playlists relevant to this date and time.
    * int limit Optional. Limit the number of playlists.
    * int offset Optional. Number of playlists to skip.



#### Return values
* **array\|object** The featured playlists. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getNewReleases

    array|object SpotifyWebAPI\SpotifyWebAPI::getNewReleases(array|object $options)

Get new releases.

Requires a valid access token.
https://developer.spotify.com/web-api/get-list-new-releases/

#### Arguments
* $options **array\|object** - Optional. Options for the items.
    * string country Optional. An ISO 3166-1 alpha-2 country code. Show items relevant to this country.
    * int limit Optional. Limit the number of items.
    * int offset Optional. Number of items to skip.



#### Return values
* **array\|object** The new releases. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getMySavedTracks

    array|object SpotifyWebAPI\SpotifyWebAPI::getMySavedTracks(array|object $options)

Get the current user’s saved tracks.

Requires a valid access token.
https://developer.spotify.com/web-api/get-users-saved-tracks/

#### Arguments
* $options **array\|object** - Optional. Options for the tracks.
    * int limit Optional. Limit the number of tracks.
    * int offset Optional. Number of tracks to skip.



#### Return values
* **array\|object** The user&#039;s saved tracks. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getReturnAssoc

    boolean SpotifyWebAPI\SpotifyWebAPI::getReturnAssoc()

Get the return type for the Request body element.




#### Return values
* **boolean** Whether an associative array or an stdClass is returned.



### getTrack

    array|object SpotifyWebAPI\SpotifyWebAPI::getTrack(string $trackId)

Get a track.

https://developer.spotify.com/web-api/get-track/

#### Arguments
* $trackId **string** - ID of the track.


#### Return values
* **array\|object** The requested track. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getTracks

    array|object SpotifyWebAPI\SpotifyWebAPI::getTracks(array $trackIds)

Get multiple tracks.

https://developer.spotify.com/web-api/get-several-tracks/

#### Arguments
* $trackIds **array** - IDs of the tracks.


#### Return values
* **array\|object** The requested tracks. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getUser

    array|object SpotifyWebAPI\SpotifyWebAPI::getUser(string $userId)

Get a user.

https://developer.spotify.com/web-api/get-users-profile/

#### Arguments
* $userId **string** - ID of the user.


#### Return values
* **array\|object** The requested user. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getUserPlaylists

    array|object SpotifyWebAPI\SpotifyWebAPI::getUserPlaylists(string $userId, array|object $options)

Get a user's playlists.

Requires a valid access token.
https://developer.spotify.com/web-api/get-list-users-playlists/

#### Arguments
* $userId **string** - ID of the user.
* $options **array\|object** - Optional. Options for the tracks.
    * int limit Optional. Limit the number of tracks.
    * int offset Optional. Number of tracks to skip.



#### Return values
* **array\|object** The user&#039;s playlists. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getUserPlaylist

    array|object SpotifyWebAPI\SpotifyWebAPI::getUserPlaylist(string $userId, string $playlistId, array|object $options)

Get a user's specific playlist.

Requires a valid access token.
https://developer.spotify.com/web-api/get-playlist/

#### Arguments
* $userId **string** - ID of the user.
* $playlistId **string** - ID of the playlist.
* $options **array\|object** - Optional. Options for the playlist.
    * array fields Optional. A list of fields to return. See Spotify docs for more info.



#### Return values
* **array\|object** The user&#039;s playlist. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### getUserPlaylistTracks

    array|object SpotifyWebAPI\SpotifyWebAPI::getUserPlaylistTracks(string $userId, string $playlistId, array|object $options)

Get the tracks in a user's playlist.

Requires a valid access token.
https://developer.spotify.com/web-api/get-playlists-tracks/

#### Arguments
* $userId **string** - ID of the user.
* $playlistId **string** - ID of the playlist.
* $options **array\|object** - Optional. Options for the tracks.
    * array fields Optional. A list of fields to return. See Spotify docs for more info.
    * int limit Optional. Limit the number of tracks.
    * int offset Optional. Number of tracks to skip.



#### Return values
* **array\|object** The tracks in the playlist. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### me

    array|object SpotifyWebAPI\SpotifyWebAPI::me()

Get the currently authenticated user.

Requires a valid access token.
https://developer.spotify.com/web-api/get-current-users-profile/


#### Return values
* **array\|object** The currently authenticated user. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### myTracksContains

    array SpotifyWebAPI\SpotifyWebAPI::myTracksContains(string|array $tracks)

Check if tracks is saved in the current user's Spotify library.

Requires a valid access token.
https://developer.spotify.com/web-api/check-users-saved-tracks/

#### Arguments
* $tracks **string\|array** - ID(s) of the track(s) to check for.


#### Return values
* **array** Whether each track is saved.



### replacePlaylistTracks

    boolean SpotifyWebAPI\SpotifyWebAPI::replacePlaylistTracks(string $userId, string $playlistId, string|array $tracks)

Replace all tracks in a user's playlist with new ones.

Requires a valid access token.
https://developer.spotify.com/web-api/replace-playlists-tracks/

#### Arguments
* $userId **string** - ID of the user.
* $playlistId **string** - ID of the playlist.
* $tracks **string\|array** - ID(s) of the track(s) to add.


#### Return values
* **boolean** Whether the tracks was successfully replaced.



### search

    array|object SpotifyWebAPI\SpotifyWebAPI::search(string $query, string|array $type, array|object $options)

Search for an item.

Requires a valid access token if market=from_token is used.
https://developer.spotify.com/web-api/search-item/

#### Arguments
* $query **string** - The term to search for.
* $type **string\|array** - The type of item to search for.
* $options **array\|object** - Optional. Options for the search.
    * string market Optional. A ISO 3166-1 alpha-2 country code. Limit the results to items that are playable in this market.
    * int limit Optional. Limit the number of items.
    * int offset Optional. Number of items to skip.



#### Return values
* **array\|object** The search results. Type is controlled by SpotifyWebAPI::setReturnAssoc().



### setAccessToken

    void SpotifyWebAPI\SpotifyWebAPI::setAccessToken(string $accessToken)

Set the access token to use.



#### Arguments
* $accessToken **string** - The access token.


#### Return values
* **void** 



### updateUserPlaylist

    boolean SpotifyWebAPI\SpotifyWebAPI::updateUserPlaylist($userId, $playlistId, array|object $data)

Update the details of a user's playlist.

Requires a valid access token.
https://developer.spotify.com/web-api/change-playlist-details/

#### Arguments
* $userId **mixed**
* $playlistId **mixed**
* $data **array\|object** - Data for the new playlist.
    * name string Required. Name of the playlist.
    * public bool Optional. Whether the playlist should be public or not.



#### Return values
* **boolean** Whether the playlist was successfully updated.



### currentUserFollows

    array SpotifyWebAPI\SpotifyWebAPI::currentUserFollows($type, $ids)

Check to see if the current user is following one or more artists or other Spotify users
Requires a valid access token.

https://developer.spotify.com/web-api/check-current-user-follows/

#### Arguments
* $type **mixed**
* $ids **mixed**


#### Return values
* **array** Whether each id (for user or artist) is followed.



### followArtistsOrUsers

    boolean SpotifyWebAPI\SpotifyWebAPI::followArtistsOrUsers($type, $ids)

Add the current user as a follower of one or more artists or other Spotify users
Requires a valid access token.

https://developer.spotify.com/web-api/follow-artists-users/

#### Arguments
* $type **mixed**
* $ids **mixed**


#### Return values
* **boolean** Whether it worked or not.



### unfollowArtistsOrUsers

    boolean SpotifyWebAPI\SpotifyWebAPI::unfollowArtistsOrUsers($type, $ids)

Remove the current user as a follower of one or more artists or other Spotify users
Requires a valid access token.

https://developer.spotify.com/web-api/unfollow-artists-users/

#### Arguments
* $type **mixed**
* $ids **mixed**


#### Return values
* **boolean** Whether it worked or not.



### setReturnAssoc

    void SpotifyWebAPI\SpotifyWebAPI::setReturnAssoc(boolean $returnAssoc)

Set the return type for the Request body element.



#### Arguments
* $returnAssoc **boolean** - Whether to return an associative array or an stdClass.


#### Return values
* **void** 

