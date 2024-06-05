# Mapeamento Relacional | Spotify API

## Endpoints

### Get Album

> ENDPOINT: https://api.spotify.com/v1/albums/{id}

### Get Several Albums

> ENDPOINT: https://api.spotify.com/v1/albums?ids={id_1},{id_2},{id_3}

### Get Album Tracks

> ENDPOINT: https://api.spotify.com/v1/albums/{id}/tracks

### Get User's Saved Albums

> ENDPOINT: https://api.spotify.com/v1/me/albums

### Get Available Genre Seeds

> ENDPOINT: https://api.spotify.com/v1/recommendations/available-genre-seeds

### Get Available Markets

> ENDPOINT: https://api.spotify.com/v1/markets

### Get Playlist

> ENDPOINT: https://api.spotify.com/v1/playlists/{playlist_id}

## Mapeamento Relacional

### Albums

Albums(
    _Request_
    id_album: str,
    market_album: str,
    _Response_
    album_type: str,
    total_tracks: int,
    available_markets: array_strings,
    external_urls(
        spotify_url: str
    ),
    href_album: str,
    images(
        url: str,
        height: int/null,
        width: int/null
    ),
    name_album: str,
    release_date: str,
    release_date_precision: str,
    restrictions(reason: str),
    type: str,
    uri: str,
    artists(
        external_urls(spotify_url: str),
        href_artist: str,
        id_artist: str,
        name_artist: str,
        type: str,
        uri_artist: str
    ),
    tracks(
        href_track: str,
        limit: int,
        next: str/null,
        offset: int,
        previous: str/null,
        total: int,
        items(
            artists(
                external_urls(spotify_url: str),
                href_artist: str,
                id_artist: str,
                name: str,
                type: str,
                uri_artist: str
            ),
            available_markets: array_str,
            disc_number: int,
            duration_ms: int,
            explicit: boolean,
            external_urls(
                spotify_url: str
            ),
            href_track: str,
            id_track: str,
            is_playable: boolean,
            linked_from(
                external_urls(spotify_url: str),
                href_track: string,
                id_track: string,
                type: str,
                uri_track: str
            ),
            restrictions(reason: str),
            name_track: str,
            preview_url: str/null,
            track_number: int,
            type: str,
            uri: str,
            is_local: boolean
    ),
    copyrights(
        text: str,
        type: str,
    ),
    external_ids(
        isrc: str,
        ean: str,
        upc: str
    ),
    genres: array_strings,
    label: str,
    popularity: int
    )
)

Album_tracks(
    id_album: str,
    market: str,
    limit: int,
    offset: int,
    href_request: str,
    limit_items: int,
    next_url: str/null,
    offset: int,
    previous_url: str/null,
    total_items: int,
    items(
        artists(
            external_urls(spotify_url: str),
            href_artist: str,
            id_artist: str,
            name: str,
            type: str,
            uri_artist: str
        ),
        available_markets: array_str,
        disc_number: int,
        duration_ms: int,
        explicit: boolean,
        external_urls(spotify_url: str),
        href_request: str,
        id_track: str,
        is_playable: boolean,
        linked_from(
            external_urls(spotify_url: str),
            href_track: string,
            id_track: string,
            type: str,
            uri_track: str
        ),
        restrictions(reason: str),
        name_track: str,
        preview_url: str/null,
        track_number: int,
        type: str,
        uri: str,
        is_local: boolean
    )
)

Users_Albums(
    limit: int,
    offset: int,
    market: str,
    href_request: str,
    next: str/null,
    previous: str/null,
    total: int,
    items(
        added_at: timestamp,
        album(
            album_type: str,
            total_tracks: int,
            available_markets: array_strings,
            external_urls(spotify_url: str),
            href_album: str,
            id_album: str,
            images(
                url_source: str,
                height: int,
                width: int
            ),
            name_album: str,
            release_date: str,
            release_date_precision:str,
            restrictions(reason: str),
            type: str,
            uri_album: str,
            artists(
                external_urls(spotify_url: str),
                href_artist: str,
                id_artist: str,
                name: str,
                type: str,
                uri_artist: str
            ),
            tracks(),
            copyrights(
                text: str,
                type: str
            ),
            external_ids(
                isrc: str,
                ean: str,
                upc: str
            ),
            genres: array_strings,
            label: str,
            popularity: int
        )
    )
)

New_Releases(
    href_request: str,
    limit: int,
    offset: int,
    next: str/null,
    previous: str/null,
    total: int,
    items(
        album_type: str,
        total_tracks: int,
        available_markets: array_strings,
        external_urls(spotify_url: str),
        href_album: str,
        id_album: str,
        images(
            url_source: str,
            height: int,
            width: int
        ),
        name_album: str,
        release_date: str,
        release_date_precision:str,
        restrictions(reason: str),
        type: str,
        uri_album: str,
        artists(
            external_urls(spotify_url: str),
            href_artist: str,
            id_artist: str,
            name: str,
            type: str,
            uri_artist: str
        )
    )
)

### Artists

Artist(
    id_artist: str,
    external_urls(spotify_url: str),
    followers(
        href: str/null,
        total: int
    ),
    genres: array_strings,
    href_artist: str,
    id_artist: str,
    images(
        url_source: str,
        height: int/null,
        width:int/null
    ),
    name_artist: str,
    popularity: int,
    type: str,
    uri_artist: str
)

Artists_albums(
    id_artist: str,
    include_groups: str,
    market: str,
    limit: int,
    offset: int,
    href_request: str,
    next: str/null,
    previous: str/null,
    total: int,
    items(
        album_type: str,
        total_tracks: int,
        available_markets: array_strings,
        external_urls(spotify_url: str),
        href_album: str,
        id_album: str,
        images(
            url_source: str,
            height: int,
            width: int
        ),
        name_album: str,
        release_date: str,
        release_date_precision:str,
        restrictions(reason: str),
        type: str,
        uri_album: str,
        artists(
            external_urls(spotify_url: str),
            href_artist: str,
            id_artist: str,
            name_artist: str,
            type: str,
            uri_artist: str
        ),
        album_group: str
    )
)

Artists_top_tracks(
    id_artist: str,
    market: str,
    tracks(
        album(
            album_type: str,
            total_tracks: int,
            available_markets: array_strings,
            external_urls(spotify_url: str),
            href_album: str,
            id_album: str,
            images(
                url_source: str,
                height: int,
                width: int
            ),
            name_album: str,
            release_date: str,
            release_date_precision:str,
            restrictions(reason: str),
            type: str,
            uri_album: str,
            artists(
                external_urls(spotify_url: str),
                href_artist: str,
                id_artist: str,
                name_artist: str,
                type: str,
                uri_artist: str
            ),
        ),
        artists(
            external_urls(
                spotify_url: str
            ),
            followers(
                href: str/null,
                total: int
            ),
            genres: array_strings,
            href_artist: str,
            id_artist: str,
            images(
                url_source: str,
                height: int,
                width: int
            )
            name_artist: str,
            popularity: int,
            type: str,
            uri_artist: str
        ),
        available_markets: array_strings,
        disc_number: int,
        duration_ms: int,
        explicit: boolean,
        external_ids(
            isrc: str,
            ean: str,
            upc: str
        ),
        external_urls(
            spotify_url: str
        ),
        href_track: str,
        id_track: str,
        is_playable: boolean,
        linked_from(
            [track_relinking](https://developer.spotify.com/documentation/web-api/concepts/track-relinking)
        ),
        restrictions(),
        name_track: str,
        popularity: int,
        preview_url: str,
        track_number: int,
        type: str,
        uri_track: str,
        is_local: boolean
    )
)

Artists_related_artists(
    external_urls(
        spotify_url: str
    ),
    followers(
        href: str/null,
        total: int
    ),
    genres: array_strings,
    href_artist: str,
    id_artist: str,
    images(
        url_source: str,
        height: int,
        width: int
    ),
    name_artist: str,
    popularity: int,
    type: str,
    uri_artist: str
)

### Audiobook

Audiobook(
    id_audiobook: str,
    market: str,
    authors(
        name: str
    ),
    available_markets: array_strings,
    copyrights(
        text: str,
        type: str
    ),
    description: str,
    html_description: str,
    edition: str,
    explicit: boolean,
    external_urls(
        spotify_url: str
    ),
    href_request: str,
    images(
        url_source: str,
        height: int,
        width: int
    ),
    languages: array_strings,
    media_type: str,
    name_audiobook: str,
    narrators(
        name: str
    ),
    publisher: str,
    type: str,
    uri_audiobook: str,
    total_chapters: int,
    chapters(
        href_request: str,
        limit: int,
        offset: int,
        next: str/null,
        previous: str/null,
        total: int,
        items(
            audio_preview_url: str/null,
            available_markets: array_strings,
            chapter_number: int,
            description: str,
            html_description: str,
            duration_ms: int,
            explicit: boolean,
            external_urls(
                spotify_url: str
            ),
            href_chapter: str,
            id_chapter: str,
            images(
                url_source: str,
                height: int,
                width: int
            ),
            is_playable: boolean,
            languages: array_strings,
            name_chapter: str,
            release_date: str,
            release_date_precision: str,
            resume_point(
                fully_played: boolean,
                resume_position_ms: int
            ),
            type: str,
            uri_chapter: str,
            restrictions(
                reason: str
            )
        )
    )
)

### Categories

Single_Category(
    href_category: str,
    icons(
        :array,
        url_img: str,
        height: int/null,
        width: int/null
    ),
    id_category: str,
    name_category: str
)

### Chapters

Chapter(
    id_chapter: str,
    market: str,
    audio_preview_url: str/null,
    available_markets: array_strings,
    chapter_number: int,
    description: str,
    html_description: str,
    duration_ms: int,
    explict: boolean,
    external_urls(
        spotify_url: str
    ),
    href_chapter: str,
    id_chapter: str,
    images(
        :array
        url: str,
        height: int/null,
        width: int/null
    ),
    is_playable: boolean,
    languages: array_strings,
    name_chapter: str,
    release_date: str,
    release_date_precision: str,
    resume_point(
        fully_played: boolean,
        resume_position_ms: int
    ),
    type: str,
    uri_chapter: str,
    restrictions(
        reason:str
    ),
    audiobook(
        authors(
            authors(
                :array
                name: str
            ),
            available_markets: array_str,
            copyrights(
                text: str,
                type: str
            ),
            description: str,
            html_description: str,
            edition: str,
            explicit: boolean,
            external_urls(
                spotify_url: str
            ),
            href_audiobook: str,
            id_audiobook: str,
            images(
                :array
                url: str,
                height: int/null,
                width: int/null
            ),
            languages: array_str,
            media_type: str,
            name_audiobook: str,
            narrators(
                :array
                name: str
            ),
            publisher: str,
            type: str,
            uri_audiobook: str,
            total_chapters: int
        )
    )
)

### Episodes

Episode(
    id_ep: str,
    market: str,
    audio_preview_url: str,
    description: str,
    html_description: str,
    duration_ms: int,
    explict: boolean,
    external_urls(
        spotify_url: str
    ),
    href_episode: str,
    id_episode: str,
    images(
        :array
        url: str,
        height: int/null,
        width: int/null
    ),
    is_externally_hosted: boolean,
    is_playable: boolean,
    languages: array_str,
    name_ep: str,
    release_date: str,
    release_date_precision: str,
    resume_point(
        fully_played: boolean,
        resume_position_ms: int
    ),
    type: str,
    uri_ str,
    restrictions(
        reason: str
    ),
    show(
        available_markets: array_str,
        copyrights(
            :array
            text: str,
            type: str
        ),
        description: str,
        html_description: str,
        duration_ms: int,
        explict: boolean,
        external_urls(
            spotify_url: str
        ),
        href_show: str,
        id_show: str,
        images(
            :array
            url: str,
            height: int/null,
            width: int/null
        ),
        is_externally_hosted: boolean,
        languages: array_str,
        media_type: str,
        name_ep: str,
        publisher: str,
        type: str,
        uri_show: str,
        total_episodes: int
    )
)

### Genres

Genres(
    genres: array_strings
)

### Markets

Markets(
    markets: array_strings
)

### Playlists

Playlists(
    id_playlist: str,
    market: str,
    fields: str,
    additional_types: str,
    collaborative: boolean,
    description: str/null,
    externals_urls(
        spotify: str
    )
    followers(
        href: str/null,
        total: int
    )
    href: str,
    id_playlist: str,
    images(
        :array
        url: str,
        height: int/null,
        width: int/null
    )
    name: str,
    owner(
        :str,
        external_urls(spotify_url: str),
        followers(
        href: str/null,
        total: int
        )
        href: str,
        id_spotify_user: str,
        type: str,
        uri: str,
        display_name: str/null
    )
    public: boolean,
    id_snapshot: str,
    tracks(
        href: str,
        limit: int,
        next: str/null
        offset: int
        previous: str/null
        total: int,
        items: array_playlistTrackObject
    )
    type: str,
    uri: str
)
playlist_items(
    get(
        id_playlist: str,
        market: str,
        fields: str,
        limit: int,
        offset: int,
        additional_types: str
    )
    pages_tracks(
        href: str,
        limit: int,
        next: str/null,
        offset: int,
        previous: str/null,
        total: int
    )
    items(
        :array_playlistTrackObject,
        added_at: str,
        added_by(
            external_urls(spotify_url: str),
            followers(
                href: str/null,
                total: int
            )
            href: int,
            id_spotifyuser: str,
            type: str,
            uri, str
        )
        is_local: boolean,
        track(
            track_object(
                Albums(
                    id_album: str,
                    market_album: str,
                    album_type: str,
                    total_tracks: int,
                    available_markets: array_strings,
                    external_urls(spotify_url: str),
                    href_album: str,
                    id_album: str,
                    images(
                    url: str,
                    height: int/null,
                    width: int/null
                ),
                name_album: str,
                release_date: str,
                release_date_precision: str,
                restrictions(reason: str),
                type: str,
                uri: str,
                artists(
                    external_urls(spotify_url: str),
                    href_artist: str,
                    id_artist: str,
                    name_artist: str,
                    type: str,
                    uri_artist: str
                )
                Artist(
                    id_artist: str,
                    external_urls(spotify_url: str),
                    followers(
                        href: str/null,
                        total: int
                    ),
                    genres: array_strings,
                    href_artist: str,
                    id_artist: str,
                    images(
                        url_source: str,
                        height: int/null,
                        width:int/null
                    ),
                    name_artist: str,
                    popularity: int,
                    type: str,
                    uri_artist: str
                )
                available_markets: array_str,
                disc_number: int,
                duration_ms: int,
                explict: boolean,
                external_ids(
                    isrc: str,
                    ean: str,
                    upc: str
                ),
                external_urls(spotify_url: str),
                href: str,
                id_track: str,
                is_playable: boolean,
                linked_from(
                    external_urls(spotify_url: str),
                    href_track: string,
                    id_track: string,
                    type: str,
                    uri_track: str
                ),
                restrictions(reason: str),
                name: str,
                popularity: int,
                preview_url: str/null,
                track_number: int,
                type: str,
                uri: str,
                is_local: boolean,
                Episode(
                    id_ep: str,
                    market: str,
                    audio_preview_url: str,
                    description: str,
                    html_description: str,
                    duration_ms: int,
                    explict: boolean,
                    external_urls(
                        spotify_url: str
                    ),
                    href_episode: str,
                    id_episode: str,
                    images(
                        :array
                        url: str,
                        height: int/null,
                        width: int/null
                    ),
                    is_externally_hosted: boolean,
                    is_playable: boolean,
                    languages: array_str,
                    name_ep: str,
                    release_date: str,
                    release_date_precision: str,
                    resume_point(
                        fully_played: boolean,
                        resume_position_ms: int
                    ),
                    type: str,
                    uri_ str,
                    restrictions(
                        reason: str
                    ),
                    show(
                        available_markets: array_str,
                        copyrights(
                            :array
                            text: str,
                            type: str
                        ),
                        description: str,
                        html_description: str,
                        duration_ms: int,
                        explict: boolean,
                        external_urls(
                            spotify_url: str
                        ),
                        href_show: str,
                        id_show: str,
                        images(
                            :array
                            url: str,
                            height: int/null,
                            width: int/null
                        ),
                        is_externally_hosted: boolean,
                        languages: array_str,
                        media_type: str,
                        name_ep: str,
                        publisher: str,
                        type: str,
                        uri_show: str,
                        total_episodes: int
                    )
                )
)
get_featured_playlists(
    get(
        locale: str,
        limit: int,
        offset: int,
    )
    response(
        message: str,
        playlists(
            href: str,
            limit: int,
            next: str/null,
            offset: int,
            previous: str/null,
            total: int
            items(
                collaborative: boolean,
                description: str,
                external_urls(
                href: str,
                id_playlist: str,
                )
                images(
                    url: str,
                    height: int,
                    width: int/null
                )
                name: str,
                owner(
                    external_urls(spotify_url: str),
                    followers(
                    href: str/null,
                    total: int
                    )
                    href: str,
                    id_spotify_user: str,
                    type: str,
                    uri: str,
                    display_name: str/null
                )
                tracks(
                    href: str,
                    total: int
                )
                type: str,
                uri: str
            )
        )
    )
)

### Shows

### Tracks

### User

## Entidades e Relacionamentos

- Album(
    *id_album*: varchar(62),
    album_type: varchar(15),
    total_tracks: int,
    -- Relacionamento: **available_album_market**: varchar(62)/varchar(2),
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
    type: varchar(10),
    uri_track: varchar(90),
    reason_restrictions: varchar(8),
    name_track: varchar(30),
    preview_url: varchar(90)/null,
    track_number: int,
    is_local: boolean
)

- Audiobook(
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

- Episode(
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

- Ep_Images(
    *id_ep*: varchar(62),
    *id_image*: int,
)

- Ep_Languages(
    *id_ep*: varchar(62),
    *id_language*: int,
)

- Categories(
    *id_category*: varchar(62),
    name_category: varchar(30),
    -- Relacionamento: **id_icons**: int
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

- Authors(
    *id_author*: varchar(62),
    name_author: varchar(30),
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

- Languages(
    *id_language*: int,
    language: varchar(30)
)

- Chapter_Languages(
    *id_chapter*: varchar(62),
    *id_language*: int
)

- Genres(
    *id_genre*: int,
    name_genre: varchar(62)
)

- Markets(
    *id_market*: varchar(2),
    country: varchar(20)
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

- Images(
    *id_image*: int,
    url: varchar(100),
    height: int/null,
    width: int/null
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