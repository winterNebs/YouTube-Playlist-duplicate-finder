 # YouTube-Playlist-duplicate-finder
Easy way to compare two large playlists and find duplicates (useful if you want to download stuff)

## How to use:
1. Open your youtube playlist: https://www.youtube.com/playlist?list=xxx...
2. Scroll to the bottom of the playlist (load the entire thing)
3. Open developer console (Chrome/Firefox: CTRL+SHIFT+J) and copy paste the following code 
```js 
var as = document.getElementsByClassName("pl-video-title-link yt-uix-tile-link yt-uix-sessionlink  spf-link");
var arr = Array.prototype.slice.call(as);
var titles = [];
arr.forEach(i=>titles.push(i.text.trim()));
JSON.stringify(titles);
```
4. Scroll all the way to the right and click "Copy"
5. Open the second playlist and load the entire thing
6. Open the developer console and type `var title1 =` and then paste the large string you copied in step 4
7. Copy the paste the following code
```js 
var as = document.getElementsByClassName("pl-video-title-link yt-uix-tile-link yt-uix-sessionlink  spf-link");
var arr = Array.prototype.slice.call(as);
var titles = [];
arr.forEach(i=>titles.push(i.text.trim()));
JSON.stringify(titles);
var dupe = titles.filter((v)=> titles1.indexOf(v)!=-1);
dupe
```
8. The output list should be the list of duplicated items
