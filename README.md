# GMTL | Get Me The Lyrics

Is a webapp that consumes the api provided by [Lyrics.ovh](https://lyricsovh.docs.apiary.io) to fetch and display the lyrics of a given song .
This was made using NuxtJs , Axios and Vuetify.

## How does it work :

<div align="center">
<img src="/assets/Lyrics.gif" >
</div>

## Song not found :

```
In case of a typo ,the message displayed is :
```

<div align="center">
<strong><p>The song / artist does not exist or there is a typo somewhere ! please check</p> </strong>
</div>

## False positive :

```
I noticed that sometimes , the status of the request is 200 instead of 404  .
But the response.lyrics returned is empty !
```

<div align="center">
<img src="/assets/falsepositive.png" >
</div>

```
The error is due to the song not being in the database (my educated guess).
So the message displayed would be :
```

<div align="center">
<strong><p>Sorry but these lyrics aren't yet added in the database</p> </strong>
</div>

## Install

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

## Contact

```
you can contact me at ZTF666@protonmail.ch or via my portfolio

```

<div align="center">

<table>
  <tr>
    <td align="center"><a href="https://ztfportfolio.web.app/" target='_blank'><img src="https://avatars1.githubusercontent.com/u/32502988?v=4" width="100px;" alt=""/><br /><sub><b>ZTF666</b></sub></a></td>
  </tr>
</table>

</div>

## License

**💎GMTL | Get Me The Lyrics💎** released under the [MIT](LICENSE) License.
<br><br>

<div align="center">
<strong><p>Made with 💘 by a 👨‍💻 on a 💻 | 2020 | ZTF666 - N.EA</p> </strong>
</div>
