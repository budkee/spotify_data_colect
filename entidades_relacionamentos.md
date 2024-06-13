# Entidades e Relacionamentos

## Entidades

- Albuns(
    *id_album*: varchar(62),
    album_type: varchar(15),
    total_tracks: int,
    -- Relacionamento: **available_album_market**: varchar(2),
    spotify_url: varchar(100),
    href_album: varchar(100),
    **image**: int,
    name_album: varchar(30),
    release_date: varchar(7),
    release_date_precision: varchar(5),
    reason_restrictions: varchar(8),
    uri: varchar(40),
    -- Relacionamento: **album_artists**: varchar(62),
    -- Relacionamento: **album_tracks**: varchar(62)/int,
    copyrights: text(500),
    type_copyrights: varchar(20),
    isrc_id: varchar(62),
    ean_id: varchar(62),
    upc_id: varchar(62),
    -- Relacionamento: **album_genres**: varchar(62)/int,
    label: varchar(30),
    popularity: int
)

- Artists(
    *id_artist*: varchar(62),
    name_artist: varchar(30),
    url_artist: varchar(100),
    uri_artist: varchar(100),
    total_followers: int,
    -- Relacionamento: **artist_genres**: varchar(62),
    -- Relacionamento: **artist_images**: varchar(62)/int,
    popularity: int
)

- Tracks(
    *id_track*: int,
    -- Relacionamento: **artists_tracks**: int/varchar(62),
    -- Relacionamento: **available_track_market**: varchar(62)/varchar(2),
    disc_number: int,
    duration_ms: int,
    explicit: boolean,
    spotify_url: varchar(100),
    is_playable: boolean,
    uri_track: varchar(90),
    reason_restrictions: varchar(8),
    name_track: varchar(30),
    preview_url: varchar(90)/null,
    track_number: int,
    is_local: boolean
)

- Audiobooks(
    *id_audiobook*: varchar(62),
    -- Relacionamento: **available_audiobook_market**: varchar(62)/varchar(2),
    -- Relacionamento: **audiobooks_authors**: varchar(62)/varchar(62),
    copyrights: text(500),
    type_copyrights: varchar(20),
    description: varchar(250),
    edition: varchar(30),
    explicit: boolean,
    spotify_url: varchar(100),
    -- Relacionamento: **audiobook_images**: varchar(62)/int,
    -- Relacionamento: **audiobook_languages**: varchar(62)/int,
    name_audiobook: varchar(30),
    -- Relacionamento: **name_narrators**: varchar(30),
    publisher: varchar(60),
    uri_audiobook: varchar(100),
    total_chapters: int
)

- Chapters(
    *id_chapter*: varchar(62),
    chapter_number: int,
    description: varchar(250),
    duration_ms: int,
    explicit: boolean,
    spotify_url: varchar(100),
    -- Relacionamento: **chapter_images**: varchar(62)/int,
    -- Relacionamento: **chapter_languages**: varchar(62)/int,
    is_playable: boolean,
    name_chapter: varchar(30),
    release_date: varchar(7),
    release_date_precision: varchar(5),
    fully_played: boolean,
    resume_position_ms: int,
    uri_chapter: varchar(100),
    reason_restrictions: varchar(8),
    audio_preview_url: varchar(100)/null
)

- Episodes(
    *id_ep*: varchar(62),
    audio_preview_url: varchar(100),
    description: varchar(250),
    duration_ms: int,
    explicit: boolean,
    spotify_url: varchar(100),
    -- Relacionamento: **ep_images**: varchar(62)/int,
    -- Relacionamento: **ep_languages**: varchar(62)/int,
    is_playable: boolean,
    name_ep: varchar(30),
    release_date: varchar(7),
    release_date_precision: varchar(5),
    fully_played: boolean,
    resume_position_ms: int,
    uri_chapter: varchar(100),
    reason_restrictions: varchar(8),
)

- Categories(
    *id_category*: varchar(62),
    name_category: varchar(30),
    -- Relacionamento: **id_icons**: int
)

- Authors(
    *id_author*: varchar(62),
    name_author: varchar(30),
)

- Languages(
    *id_language*: int,
    language: varchar(30)
)

- Genres(
    *id_genre*: int,
    name_genre: varchar(62)
)

- Markets(
    *id_market*: varchar(2)
)

- Images(
    *id_image*: int,
    url: varchar(100),
    height: int/null,
    width: int/null
)

- Playlists(

)

- Shows(

)

- Tracks(

)

- User(

)


## Relacionamentos

- Ep_Images(
    *id_ep*: varchar(62),
    *id_image*: int,
)

- Ep_Languages(
    *id_ep*: varchar(62),
    *id_language*: int,
)

- Category_Icons(
    *id_icon*: int,
    url_img: varchar(100),
    height: int/null
    width: int/null
)

- Available_Audiobook_Market(
    *id_audiobook*: varchar(62),
    *id_market*: varchar(2)
)

- Audiobooks_Authors(
    *id_audiobook*: varchar(62),
    *id_author*: varchar(62)
)

- Audiobooks_Narrators(
    *id_audiobook*: varchar(62),
    *id_narrator*: varchar(62),
    name_narrator: varchar(30)
)

- Audiobooks_Images(
    *id_audiobook*: varchar(62),
    *id_image*: int
)

- Audiobooks_Languages(
    *id_audiobook*: varchar(62),
    *id_language*: int
)

- Chapter_Languages(
    *id_chapter*: varchar(62),
    *id_language*: int
)

- Album_Artists(
    *id_album*: varchar(62),
    *id_artist*: varchar(62)
)

- Album_Tracks(
    *id_album*: varchar(62),
    *id_track*: int,
    **market**: varchar(2)
)

- Album_Genres(
    *id_album*: varchar(62),
    *id_genre*: int
)

- Available_Album_Market(
    *id_album*: varchar(62),
    *id_market*: varchar(2)
)

- Available_Track_Market(
    *id_track*: varchar(62),
    *id_market*: varchar(2)
)

- Artists_Tracks(
    *id_track*: int,
    *id_artist*: varchar(62)
)

- Album_Images(
    *id_album*: varchar(62),
    *id_image*: int
)

- Artist_Images(
    *id_artist*: varchar(62),
    *id_image*: int
)

- Chapter_Images(
    *id_chapter*: varchar(62)
    *id_image*: int
)
