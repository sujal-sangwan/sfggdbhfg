const { prototype } = require('events')
const http = require('http')

const server = http.createServer((req, res) => {
  console.log(req.url, req.method, req.headers)
  if (req.url === '/') {
    res.write(`  
   <html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <head>
      <nav>
        <li>
          <ul>
            <a href="/Home">home</a>
            <a href="/contact">contact</a>
            <a href="/help">help</a>
            <a href="/login">login</a>
            <a href="/logout">logout</a>
          </ul>
        </li>
      </nav>
    </head>
  </body>
</html> `)
    res.end()
  }
  else if (req.url === '/Home') {
    res.write('welcome to home page')
    res.end()
  } else if (req.url === '/contact') {
    res.write('welcome to contact page')
    res.end()
  } else if (req.url === '/help') {
    res.write('welcome to help page')
    res.end()
  } else if (req.url === '/login') {
    res.write('welcome to login page')
    res.end()
  } else if (req.url === '/logout') {
    res.write('welcome to logout page')
    res.end()
  }
})

const PORT = 3000;
server.listen(PORT, () => {
  console.log(`server running at adress http://localhost:${PORT}`)
})
