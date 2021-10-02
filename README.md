# API results
Result from api

## router get

```js
router.get('/anime/shizuka', async (req, res, next) => {
        var Apikey = req.query.apikey
            
	if(!Apikey) return res.json(loghandler.notparam)
	if(listkey.includes(Apikey)){

  const shizuka = JSON.parse(fs.readFileSync(__path +'/${your file database}/shizuka.json'));
  const randshizuka = shizuka[Math.floor(Math.random() * shizuka.length)];
  data = await fetch(randshizuka).then(v => v.buffer())
  await fs.writeFileSync(__path +'/tmp/shizuka.jpeg', data)
  res.sendFile(__path +'/tmp/shizuka.jpeg')
} else {
res.json(loghandler.invalidKey)
}
})
```
</p>

## textpro scraper

please look at the WhatsApp bot repository 

```js
/**
 * Textpro saver by @isywl_ aka Rey
 * Coded by ibnusyawal
**/

var fs = require('fs')
var needle = require('needle')

needle.defaults()['user_agent'] = 'Googlebot'

var text = process.argv.splice(2).join` ` || 'Reys'
var urls = 'https://server-api-rey.herokuapp.com/api/textpro/${theme}?text={text}&apikey=apirey'
    .replace('{text}', text)

var filename = `${Date.now()}_textpro.png`

needle(urls, (err, resp, body) => {
    needle.get(body.result)
        .pipe(fs.createWriteStream(filename))
        .on('done', err => console.log(`saved as name: ${filename}`))
})
```
</p>
