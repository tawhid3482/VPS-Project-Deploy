# VPS Project Deploy

## Step-1

First enter VPS IP address

```js
sss root@<ip address>
```

Then enter your password

```js
root@<ip address>'s password:
```

## Step-2

make sure it has
Go to www folder

```js
cd /var/www
```

Check all project

```js
ls;
```

## Step-3

Clone your github project

```js
git clone git@github.com:MdAfsarHossain/VPS-Project-Deploy.git
```

## Step-4

```js
ls;
```

```js
cd vps-project-deploy/
```

```js
npm i
```

```js
npm run build
```

## Step-5

```js
sudo ufw enable
```

```js
sudo ufw status
```

```js
sudo ufw allow 5008
```

```js
sudo ufw status
```

```js
npm run start
```

```js
sudo ufw reload
```

## Step-React -create server.cjs file

```js
const express = require("express");
const path = require("path");

const app = express();
const PORT = 4000;

// dist folder serve
app.use(express.static(path.join(__dirname, "dist")));

// React SPA fallback (MOST IMPORTANT)
app.get("*", (req, res) => {
  res.sendFile(path.join(__dirname, "dist", "index.html"));
});

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});

```
```js
server.cjs
pm2 start server.cjs --name mpcpest-frontend
pm2 save
```
## Step-6

```js
npm i -g pm2
```

```js
pm2 start npm --name "vps-project-deploy" -- start
```

```js
pm2 logs vps-project-deploy
```

```js
pm2 ls
```

# After Successfully Deploy for redeploy follow this step

```js
git pull
```

```js
npm i
```

```js
npm run build
```

```js
pm2 ls
```

```js
pm2 restart <id_no>
```
