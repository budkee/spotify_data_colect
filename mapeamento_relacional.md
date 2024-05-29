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

## Mapeamento Relacional

### Albums

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
            external_urls(spotify_url: str),
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

Audiobook_Chapters(
    id_audiobook: str,
    market: str,
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

Users_Saved_Audiobooks(
    limit: int,
    offset: int,
    href_request: str,
    next: str/null,
    previous: str/null,
    total: int,
    items(
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
    )
)

### Categories

Categories(
    locale: str,
    limit: int,
    offset: int,
    href_request: str,
    next: str/null,
    previous: str/null,
    total: int,
    items(
        :array
        href_category: str,
        icons(
            url_img: str,
            height: str/null,
            width: str/null
        ),
        id_category: str,
        name_category: str
    )
)

Single_Category(
    href_category: str,
    icons(
        :array,
        url_img: str,
        height: int,
        width: int
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

Several_Chapters(
    ids: str,
    market: str,
    chapters(
        :array
        audio_preview_url: str/null,
        available_markets: array_str,
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
            :array
            url_ str,
            height: int/null,
            weight: int/null
        ),
        is_playable: boolean,
        languages: array_str,
        name_chapter: str,
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
        audiobook(
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

Several_Episodes(
    ids: str,
    market: str,
    episodes(
        :array
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

### Markets

### Playlists

### Shows

### Tracks

### User
