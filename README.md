# 数据可视化
数据可视化及备份


### 数据格式化
``` js
function toSimple(type = 'song', raw) {
    if(type === 'song') {
        return {
            album_logo: raw.albumLogo,
            album_name: raw.albumName,
            artist_name: raw.artistName,
            artist_alias: raw.artistAlias,
            artists: raw.artistVOs && raw.artistVOs.map(_ => {
                return {
                    name: _.artistName,
                    id: _.artistId,
                    alias: _.alias
                }
            }),
            song_name: raw.songName,
            song_id: raw.songId,
            song_writes: raw.songwriters
        }
    }

    if (type === 'album') {
        return {
            album_id: raw.albumId,
            album_logo: raw.albumLogo,
            company: raw.company,
            language: raw.language,
            play_count: raw.playCount,
            recommends: raw.recommends,
            album_category: raw.albumCategory,
            publish: raw.gmtPublish,
            album_name: raw.albumName,
            artist_name: raw.artistName,
            artist_id: raw.artistId,
            artists: raw.artists.map(_ => {
                return {
                    comments: _.comments,
                    description: _.description,
                    area: _.area,
                    name: _.artistName,
                    id: _.artistId,
                    alias: _.alias
                }
            }),
        }
    }

    if (type === 'artist') {
        return {
            artist_logo: raw.artistLogo,
            alias: raw.alias,
            artist_id: raw.artistId,
            artist_name: raw.artistName,
            area: raw.area,
            comments: raw.comments,
            likes: raw.countLikes,
            gender: raw.gender,
            play_count: raw.playCount,
            recommends: raw.recommends,
            roles: raw.roles && raw.roles.map(_ => _.name),
            styles: raw.styles && raw.styles.map(_ =>  _.styleName),
        }
    }

    if (type === 'collect') {
        return {
            id: raw.listId,
            collect_logo: raw.collectLogo,
            name: raw.collectName,
            description: raw.description,

            collects: raw.collects,
            comments: raw.comments,
            play_count: raw.playCount,
            views: raw.views,

            gmt_create: raw.gmtCreate,
            gmt_modify: raw.gmtModify,
            song_count: raw.songCount,

            songs: raw.songs && raw.songs.map(_ => {
                return {
                    description: _.description,
                    album_id: _.albumId,
                    language: _.albumLanguage,
                    album_name: _.albumName,
                    artist_name: _.artistName,
                    composer: _.composer,
                    arrangement: _.arrangement,
                    song_name: _.songName,
                    songwriters: _.songwriters,
                    singers: _.singers,
                }
            }),

            author: raw.userName,
            avatar: raw.user.avatar,
        }
    }
}

```
