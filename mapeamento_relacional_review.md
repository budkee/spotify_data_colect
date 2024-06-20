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
    id_album: str,
    market_album: str,
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

Users_Saved_Episodes(
    market: str,
    limit: int,
    offset: int,
    href_request: str,
    next: str/null,
    previous: str/null,
    total_items: int,
    items(
        :array
        added_at: str,
        episode(
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
    name_playlist: str,
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

get_playlist_items(
    get(
        id_playlist: str,
        market: str,
        fields: str,
        limit: int,
        offset: int,
        additional_types: str
    )
    ###Response
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
            id_spotify_user: str,
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
                    uri: str,
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
        )
    )
)

get_current_user_playlit(
    limit: int,
    offset: int,
    href: str,
    limit: int,
    next: str/null,
    offset: int,
    previous: str/null,
    total: int,
    items(
        collaborative: boolean,
        descripting: str,
        external_urls(
            spotify_url: str
        )
    href: str,
    id_playlist: str,
    images(
        url: str,
        height: int/null,
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
        id_user_spotify: str,
        type: str,
        uri: str,
        display_name: str/null
    )
    public: boolean,
    id_snapshot: str,
    tracks(
        href: str,
        total: int
    )
    type: str,
    uri: str
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
                    spotify_url: str,
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
                ),
                public: boolean,
                id_snapshot: str,
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

get_user_playlist(
    id_user: str,
    limit: int,
    offset: int,
    ### Response
    href: str,
    limit: int,
    next: str/null,
    offset: int,
    previous: str/null,
    total: int,
    items(
        collaborative: boolean,
        description: str,
        external_urls(
        href: str,
        id_playlist: str,
    )
    images(
        url: str,
        height: int/null,
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

get_category_playlist(
    id_category: str,
    limit: int,
    offset: int
)
response(
    message: str,
    playlists(
        href: str,
        limit: int,
        next: str,
        offset: int,
        previous: int/null,
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
                height: int/null,
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
            public: boolean,
            id_snapshot: str,
            tracks(
                href: str,
                total: int
            )
            type: str,
            uri: str
        )
    )
)

get_playlist_cover_image(
    id_playlist: str,
    ### Response
    url: str,
    height: int,
    width: int/null
)

### Shows

get_show(
    market: str,
    id_show: str,
    ### Response
    available_markets: array_strings,
    copyrights(
        text: str,
        type: str
    )
    description: str,
    html_description: str,
    explict: boolean,
    external_urls(spotify_url: str)
    href: str,
    id: str
    images(
        url: str,
        height: int/null,
        width: int/null
    ),
    is_externally_hosted: boolean,
    languages: array_str,
    media_type: str,
    name: str,
    publisher: str,
    type: str,
    uri: str,
    total_episodes: int
    episodes(
        href: str,
        limit: int,
        next: str/null,
        offset: int,
        previous: str/null,
        total: int,
        items(
            audio_preview_url: str/null,
            description:  str,
            html_description: str,
            duration_ms: int,
            explict: boolean,
            externals_urls(spotify_url: str)
            href: str,
            id_episodes: str,
            images(
                url: str,
                height: int/null,
                width: int/null
            ),
            is_externally_hosted: boolean,
            is_playable: boolean,
            language: str,
            languages: array_str,
            name: str,
            release_date: str,
            release_date_precision
            resume_point(
                fully_played: boolean,
                resume_position_ms
            )
            type: str,
            uri: str,
            restrictions(
                reason: str
            )
        )
    )
)


get_several_shows(
    market: str,
    list_ids_for_the_show: str(50),
    shows(
        available_markets: array_strings,
        copyrights(
            text: str,
            type: str
        )
        description: str,
        html_description: str,
        explict: boolean,
        external_urls(spotify_url: str)
        href: str,
        id: str
        images(
            url: str,
            height: int/null,
            width: int/null
        ),
        is_externally_hosted: boolean,
        languages: array_str,
        media_type: str,
        name: str,
        publisher: str,
        type: str,
        uri: str,
        total_episodes: int
    )
)


get_shows_episodes(
    id_show: str,
    market: str,
    limit: int,
    offset: int
    ### Response
    href: str,
    limit: int,
    next: str/null,
    offset: int,
    previous: str/null,
    total: int,
    items(
        audio_preview_url: str/null,
        description:  str,
        html_description: str,
        duration_ms: int,
        explict: boolean,
        externals_urls(spotify_url: str)
        href: str,
        id_episodes: str,
        images(
            url: str,
            height: int/null,
            width: int/null
        ),
        is_externally_hosted: boolean,
        is_playable: boolean,
        language: str,
        languages: array_str,
        name: str,
        release_date: str,
        release_date_precision
        resume_point(
            fully_played: boolean,
            resume_position_ms
        )
        type: str,
        uri: str,
        restrictions(
            reason: str
        )
    )
)


get_user_saved_shows(
    limit: int,
    offset: int,
    ### Response
    href: str,
    limit: int,
    next: str/null,
    offset: int,
    previous: str/null,
    total: int,
    items(
        added_at: str(date-time)
        shows(
            available_markets: array_strings,
            copyrights(
                text: str,
                type: str
            )
            description: str,
            html_description: str,
            explict: boolean,
            external_urls(spotify_url: str)
            href: str,
            id: str
            images(
                url: str,
                height: int/null,
                width: int/null
            ),
            is_externally_hosted: boolean,
            languages: array_str,
            media_type: str,
            name: str,
            publisher: str,
            type: str,
            uri: str,
            total_episodes: int
        )
    )
)

### Tracks

get_track(
    id_track: str,
    market: str,
    album(
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
    ),
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
    linkedfrom: contains information about the originally requested track,
    restrictions(
        reason: str (market, product, explict),
    ),
    name: str,
    popularity: int,
    preview_url: str/null,
    track_number: int,
    type: str,
    uri: str,
    is_local: boolean
    )
)

get_several_tracks(
    market: str,
    ids: str,
    tracks(
        album(
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
                name_album: str,
                release_date: str,
                release_date_precision: str,
                restrictions(reason: str),
                type: str,
                uri: str,
            )
            artists(
                external_urls(spotify_url: str),
                href_artist: str,
                id_artist: str,
                name_artist: str,
                type: str,
                uri_artist: str
            )
        )
    )
    artists(
        external_urls(spotify_url: str),
        followers(
            href: str/null,
            total: int
        ),
        genres: array_str,
        href: str,
        id_artist: str,
        images(
            url: str,
            height: int/null,
            width: int/null
        ),
        name: str,
        popularity: int,
        type: str,
        uri: str
    ),
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
    linked_from: contains information about the originally requested track,
    restrictions(reason: str),
    name: str,
    popularity: int,
    preview_url: str/null,
    track_number: int,
    type: str,
    uri: str,
    is_local: boolean
)

get_user_saved_tracks(
    market: str,
    limit: int,
    offset: int,
    previous: str/null,
    total: int,
    items(
        added_at: str(date-time),
        track(
            album(
                album_type: str,
                total_tracks: int,
                available_markets: array_str,
                external_urls(spotify_url: str),
                href: str,
                id_album: str,
                images(
                    url: str,
                    height: int/null,
                    width: int/null
                ),
                name: str,
                release_date: str,
                release_date_precision: str,
                restrictions(
                    reason: str
                )
                type: str,
                uri: str,
                artist(
                    external_urls(spotify_url: str)
                    href: str,
                    id_artist: str,
                    name: str,
                    type: str,
                    uri: str,
                )
            artists(
                external_urls(spotify_url: str),
                followers(
                    href: str/null,
                    total: int
                ),
                genres: array_str,
                href: str,
                id_artist: str,
                images(
                    url: str,
                    height: int/null,
                    width: int/null
                ),
                name: str,
                popularity: int,
                type: str,
                uri: str
            ),
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
            linked_from: contains information about the originally requested track,
            restrictions(reason: str),
            name: str,
            popularity: int,
            preview_url: str/null,
            track_number: int,
            type: str,
            uri: str,
            is_local: boolean
            )
        )
    )
)

get_Several_Tracks'_Audio_Features(
    id_list_tracks: str(100),
    audio_features(
        acousticness: float,
        analysis_url: str,
        danceability: float,
        duration_ms: int,
        id_track: str,
        instrumentalness: float,
        key: int,
        liveness: float,
        loudness: float,
        mode: int,
        speechiness: float,
        tempo: float,
        time_signature: int,
        track_href: str,
        type: str,
        uri: str,
        valence: float
    )
)

get_Track_Audio_Features(
    id_track: str,
    ###RESPONSE
    acousticness: float,
    analysis_url: str,
    danceability: float,
    duration_ms: int,
    id_track: str,
    instrumentalness: float,
    key: int,
    liveness: float,
    loudness: float,
    mode: int,
    speechiness: float,
    tempo: float,
    time_signature: int,
    track_href: str,
    type: str,
    uri: str,
    valence: float
)

get_track_audio_analysis(
    id_track: str,
    ###RESPONSE
    meta(
        analyzer_version: str,
        platform: str,
        detailed_status: str,
        status_code: int,
        timestamp: int,
        analysis_time: number,
        input_process: str
    ),
    track(
        num_samples: int,
        duration: number,
        sample_md5: str,
        offset_seconds: int,
        window_seconds: int,
        analysis_simple_rate: int,
        analysis_channels: int,
        end_of_fade_in: number,
        start_of_fade_out: number,
        loudness: float,
        tempo: float,
        tempo_confidence: number,
        time_signature: int,
        key: int,
        key_confidence: number,
        mode: int,
        mode_confidence: number,
        codestring: str,
        code_version: number,
        echosprinting: str,
        echoprint_version: number,
        synchstring: str,
        synch_version:  number,
        rhythmstring: str,
        rhythm_version: number
    )
    bars(
        start: number,
        duration: number,
        confidence: number
    )
    beats(
        start: number,
        duration: number,
        confidence: str
    )
    sections(
        start: number,
        duration: number,
        confidence: number,
        loudness: number,
        tempo: number,
        tempo_confidence: number,
        key: int,
        key_confidence: number,
        mode: number,
        mode_confidence: number,
        time_signature: int,
        time_signature_confidence: number
    )
    segments(
        start: number,
        duration: number,
        confidence: number,
        loudness_start: number,
        loudness_max: number,
        loudness_max_time: number,
        loudness_end: number,
        pitches: array_numbers,
        timbre: array_numbers
    )
    tatums(
        start: number,
        duration: number,
        confidence: number,
    )
)

get_recommendations(
    limit: int,
    market: str,
    seeds_artists: str,
    seeds_genres: str,
    min_accousticness: number,
    target_accousticness: number,
    min_danceability: number,
    max_danceability: number,
    target_danceability: number,
    min_duration_ms: int,
    max_duration_ms: int,
    target_duration_ms: int,
    min_energy: number,
    max_energy: number,
    target_energy: number,
    min_instrumentalness: number,
    max_instrumentalness: number,
    target_instrumentalness: number,
    min_key: int,
    max_key: int,
    target_key: int,
    min_liveness: number,
    max_liveness: number,
    target_liveness: number,
    min_loudness: number,
    max_loudness: number,
    target_loudness: number,
    min_mode: int,
    max_mode: int,
    target_mode: int,
    min_popularity: int,
    max_popularity: int,
    target_popularity: int,
    min_speechiness: number,
    max_speechiness: number,
    target_speechiness: number,
    min_tempo: number,
    max_tempo: number,
    target_tempo: number,
    min_time_signature: int,
    max_time_signature: int,
    target_time_signature: int,
    min_valence: number,
    max_valence: number,
    target_valence: number
    ###RESPONSE
    seeds(
        afterFilteringSize: int,
        afterRelinkingSize: int,
        href: str,
        id: str(the id used to select this seed. This will be the same as the string used in the seed_artists, seed_tracks or seed_genres parameter.)
        initialPoolSize: int,
        type: str
    )
    tracks(
        album(
            album_type: str,
            total_tracks: int,
            available_markets: array_str,
            external_urls(spotify_url: str),
            href: str,
            id_album: str,
            images(
                url: str,
                height: int/null,
                width: int/null
            ),
            name: str,
            release_date: str,
            release_date_precision: str,
            restrictions(
                reason: str
            )
            type: str,
            uri: str,
            artist(
                external_urls(spotify_url: str)
                href: str,
                id_artist: str,
                name: str,
                type: str,
                uri: str,
            )
        artists(
            external_urls(spotify_url: str),
            followers(
                href: str/null,
                total: int
            ),
            genres: array_str,
            href: str,
            id_artist: str,
            images(
                url: str,
                height: int/null,
                width: int/null
            ),
            name: str,
            popularity: int,
            type: str,
            uri: str
        ),
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
        linked_from: contains information about the originally requested track,
        restrictions(reason: str),
        name: str,
        popularity: int,
        preview_url: str/null,
        track_number: int,
        type: str,
        uri: str,
        is_local: boolean
        )
    )
)

### User

Get_Current_User_Profile(
    ###RESPONSE
    country: str,
    display_name: str,
    email: int,
    explict_content(
        filter_enabled: boolean,
        filter_locked: boolean
    )
    external_urls(spotify_url: str),
    followers(
        href: str/null,
        total: int
    )
    href: str,
    id_spotify_user: str,
    images(
        url: str,
        height: int/null,
        width: int/null
    ),
    product: str,
    type: str,
    uri: str
)

get_User_Top_Items(
    type: str,
    time_range: str,
    limit: int,
    offset: int,
    ###RESPONSE
    href: str,
    limit: int,
    next: str/null,
    offset: int,
    previous: str/null,
    total: int,
    items(
        artist(
            external_urls(spotify_url: str),
            followers(
                href: str/null,
                total: int
            ),
            genres: array_str,
            href: str,
            id_artist: str,
            images(
                url: str,
                height: int/null,
                width: int/null
            ),
            name: str,
            popularity: int,
            type: str,
            uri: str
        ),
        tracks(
            album(
                album_type: str,
                total_tracks: int,
                available_markets: array_str,
                external_urls(spotify_url: str),
                href: str,
                id_album: str,
                images(
                    url: str,
                    height: int/null,
                    width: int/null
                ),
                name: str,
                release_date: str,
                release_date_precision: str,
                restrictions(
                    reason: str
                )
                type: str,
                uri: str,
                artist(
                    external_urls(spotify_url: str)
                    href: str,
                    id_artist: str,
                    name: str,
                    type: str,
                    uri: str,
                )
            artists(
                external_urls(spotify_url: str),
                followers(
                    href: str/null,
                    total: int
                ),
                genres: array_str,
                href: str,
                id_artist: str,
                images(
                    url: str,
                    height: int/null,
                    width: int/null
                ),
                name: str,
                popularity: int,
                type: str,
                uri: str
            ),
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
            linked_from: contains information about the originally requested track,
            restrictions(reason: str),
            name: str,
            popularity: int,
            preview_url: str/null,
            track_number: int,
            type: str,
            uri: str,
            is_local: boolean
            )
        )
    )
)

get_user_profile(
    id_user: str,
    display_name: str/null,
    external_urls(spotify_url: str),
    followers(
        href: str/null,
        total: int
    )
    href: str,
    id_spotify_user: str,
    images(
        url: str,
        height: int/null,
        width: int/null
    ),
    type: str,
    uri: str
)

get_followed_artists(
    type: str,
    after: str,
    limit: int
    artists(
        href: str,
        limit: int,
        next: str,
        cursors(
            after: str,
            before: str
        )
        total: int,
        items(
            external_urls(spotify_url: str),
            followers(
                href: str/null,
                total: int
            )
            href: str,
            id_spotify_user: str,
            images(
                url: str,
                height: int/null,
                width: int/null
            ),
            type: str,
            uri: str
        )
    )
)
