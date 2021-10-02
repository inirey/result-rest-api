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
