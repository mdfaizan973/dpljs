# How to deploy our BackEnd server--
# npm init -y
#  npm i json-server
# package.json -->
 "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js"
  },
# npm start
# db.json will have have data
# create --> index.js 
`const jsonServer = require('json-server')
const cors = require('cors')
const path = require('path')

const server = jsonServer.create()
const router = jsonServer.router(path.join(__dirname, 'db.json'))
const middlewares = jsonServer.defaults()

server.use(cors())
server.use(jsonServer.bodyParser)
server.use(middlewares)
server.use(router)

const PORT = 8000

server.listen(PORT, () => {
  console.log(`JSON Server is running on http://localhost:${PORT}`)
})`
# .gitignore -> node_module
