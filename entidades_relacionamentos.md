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
    *id_playlist*: varchar(62),
    -- Relacionamento: **available_playlist_market**: varchar(2),
    collaborative: boolean,
    description: varchar/null,
    spotify_url: varchar(100),
    total_followers: int,
    -- Relacionamento: **playlist_images**: varchar(62)/int,
    name_playlist: varchar(30),
    -- Relacionamento: **id_owner**: varchar(62),
    public: boolean,
    -- Relacionamento: **playlist_tracks**: varchar(62),
    total_tracks: int,
    uri_playlist: varchar(100),
    is_local: boolean,
    -- Relacionamento: **playlist_episodes**: varchar(62),
    -- Relacionamento: **playlist_categories**: varchar(62),
    message: varchar(255),
)

- Shows(
    -- Relacionamento: **available_show_market**: varchar(2),
    *id_show*: varchar(62),
    copyrights: text(500),
    type_copyrights: varchar(20),
    description: varchar(250),
    explicit: boolean,
    spotify_url: varchar(100),
    -- Relacionamento: **shows_images**: varchar(62)/int,
    is_externally_hosted: boolean,
    -- Relacionamento: **shows_languages**: varchar(62)/int,
    media_type: varchar(30),
    name_show: varchar(30),
    publisher: varchar(30),
    uri_show: varchar(100),
    total_episodes: int,
    -- Relacionamento: **show_episodes**: varchar(62),
    added_at: timestamp
)

- Tracks(
    *id_track*: varchar(62),
    -- Relacionamento: **available_track_market**: varchar(2),
    -- Relacionamento: **albuns_tracks**: varchar(62),
    -- Relacionamento: **artists_tracks**: varchar(62),
    disc_number: int,
    duration_ms: int,
    explict: boolean,
    isrc_id: varchar(62),
    ean_id: varchar(62),
    upc_id: varchar(62),
    spotify_url: varchar(100),
    is_playable: boolean,
    *restrictions(reason: varchar(100)),
    name_track: varchar(30),
    popularity: int,
    preview_url: varchar(90)/null,
    track_number: int,
    track_type: varchar(30),
    uri: varchar(100),
    is_local: boolean,
    total_tracks: int,
    added_at: timestamp,
    * -- Relacionamento: **tracks_audio_features**,
    *seed_artists: varchar(100),
    *seed_genres: varchar(100),
    *seed_tracks: varchar(100),
    *min_acousticness: number(float),
    *max_acousticness: number(float),
    *target_acpusticness: number(float),
    *min_danceability: number(float),
    *max_danceability: number(float),
    *target_danceability: number(float),
    *min_duration_ms: int,
    *max_duration_ms: int,
    *target_duration:ms: int,
    min_energy: number(float),
    max_energy: number(float),
    target_energy: number(float),
    min_instrumentalness: number(float),
    max_instrumentalness: number(float),
    target_instrumentalness: number(float),
    min_key: int,
    max_key: int,
    target_key: int,
    min_liveness: number(float),
    max_liveness: number(float),
    target_liveness: number(float),
    min_loudness: number(float),
    max_loudness: number(float),
    target_loudness: number(float),
    min_mode: int,
    max_mode: int,
    target_mode: int,
    min_popularity: int,
    max_popularity: int,
    target_popularity: int,
    min_speechiness: number(float),
    max_speechiness: number(float),
    target_speechiness: number(float),
    min_tempo: number(float),
    max_tempo: number(float),
    target_tempo: number(float),
    min_time_signature: int,
    mmax_time_signature: int,
    target_time_signature: int,
    min_valence: number(float),
    max_valence: number(float),
    target_valence: number(float),
)

*audio_features(
    acousticness: float,
    analysis_url: varchar(100),
    danceability: float,
    duration_ms: int,
    energy: float,
    *id_track*: varchar(62),
    instrumentalness: float,
    key: int,
    liveness: float,
    loudness: float,
    mode: int,
    speechiness: float,
    tempo: float,
    time_signature: int,
    *track_href: varchar(100),
    *type: ,
    uri: varchar(100),
    valence: float
)

*meta(
    analyzer_version: varchar(10),
    platform: varchar(20),
    detailed_status: varchar(10),
    status_code: int,
    timestamp: int,
    analysis_time: number,
    input_process: varchar(100)
)

*beats(
    start: number(float),
    duration: number(float),
    confidence: number(float)
)

*sections(
    start: number(float),
    duration: number(float),
    confidence: number(float),
    loudness: number(float),
    tempo: number(float),
    tempo_confidence: number(float),
    key: int,
    key_confidence: number(float),
    mode: number(float),
    mode_confidence: number(float),
    time_signature: int,
    time_signature_confidence: number(float),
)

*segments(
    start: number(float),
    duration: number(float),
    confidence: number(float),
    loudness_start: number(float),
    loudness_max: number(float),
    loudness_max_time: number(float),
    loudness_end: number(float),
    pitches: array of numbers,
    timbre: array of numbers,
)

seeds(
    afterFilteringSize: int,
    afterRelikingSize: int,
    *id_seed*: varchar(62),
    InitialPoolSize: int,
    seed_type: varchar(20)
)

- User(
    country: varchar(2),
    display_name: varchar(100),
    email: int, 
    -- Relacionamento: **explict_content_user**: boolean,
    spotify_url: varchar(100),
    total_followers: int,
    *id_user*: varchar(62),
   -- Relacionamento: **user_images**: varchar(62)/int,
   product: varchar(20),
   user_type: varchar(20),
   uri: varchar(40),
   *type_artists/tracks: varchar(20),
   *time_range: varchar(100)
)

explicit_content(
    filter_enabled: boolean,
    filter_locked: boolean,
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

- Available_Playlist_Market(
    *id_playlist*: varchar(62),
    *id_market*: varchar(2)
)

- Playlist_Imges(
    *id_playlist*: varchar(62),
    *id_image*: int
)

owner_Playlist(
    *id_user*: varchar(62),
    *id_playlist*: varchar(62)
)

Playlist_Tracks(
    *id_playlist*: varchar(62),
    *id_tracks*: varchar(62)
)

Playlist_Episodes(
    *id_playlist*: varchar(62),
    *id_episodes*: varchar(62)
)

Playlist_Categories(
    *id_playlist*: varchar(62),
    *id_categories*: varchar(62)
)

Available_Show_Market(
    *id_show*: varchar(62),
    *id_market*: varchar(2)
)

Shows_Images(
    *id_show*: varchar(62),
    *id_image*: int
)

Shows_languages(
    *id_show*: varchar(62),
    *id_languages*: int
)

show_episodes(
    *id_show*: varchar(62),
    *id_episodes*: varchar(62)
)

Available_Track_Market(
    *id_track*: varchar(62),
    *id_market*: varchar(2)
)

Albuns_Tracks(
    *id_albuns*: varchar(62),
    *id_track*: varchar(62)
)
Artists_Tracks(
    *id_artist*: varchar(62),
    *id_track*: varchar(62)
)

Tracks_Audio_Features(
    *id_track*: varchar(62),
    *id_audio_features*: varchar(62)
)

Explict_Content_User(
    *id_user*: varchar(62),
    *id_explict_content*: boolean
)

User_Images(
    *id_user*: varchar(62),
    *id_image*: int,
)
