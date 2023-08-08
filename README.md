# pp-worker 

1. See YouTube Video:
# برای دیدن آموزش به کانال زیر مراجعه کنید:
   [https://www.youtube.com/@IR_Tech](https://www.youtube.com/watch?v=o0ui2vK34Q0) 
   
   🎗Telegram channel:
 [https://www.t.me/P_tech2024](https://www.t.me/P_tech2024)


for android download -->[hacker's Keyboard](https://play.google.com/store/apps/details?id=org.pocketworkstation.pckeyboard)

.
2. Clone this repository deploy in cloudflare pages.

## Deploy in worker.dev

1. Copy `_worker.js` code from [here](https://github.com/Ptechgithub/pp-worker/blob/main/_worker.js).

### UUID Setting (Optional)

1. When deploy in cloudflare pages, you can set uuid in `wrangler.toml` file. variable name is `UUID`.

2. When deploy in worker.dev, you can set uuid in `_worker.js` file. variable name is `userID`.

### UUID Setting Example

1. single uuid environment variable

   ```.environment
   UUID = "uuid here your want to set"
   ```

2. multiple uuid environment variable

   ```.environment
   UUID = "uuid1,uuid2,uuid3"
   ```

   note: uuid1, uuid2, uuid3 are separated by commas`,`.
   when you set multiple uuid, you can will use `https://pp-worker.pages.dev/uuid1` to get the clash config and vless:// link.

## subscribe vless:// link (Optional)

1. visit `https://pp-worker.pages.dev/uuid your set` to get the subscribe link.

2. visit `https://pp-worker.pages.dev/sub/uuid your set` to get the subscribe content with `uuid your set` path.

   note: `uuid your set` is the uuid you set in UUID enviroment or `wrangler.toml`, `_worker.js` file.
   when you set multiple uuid, you can wiill use `https://pp-worker.pages.dev/sub/uuid1` to get the subscribe content with `uuid1` path.(only support first uuid in multiple uuid set)

3. visit `https://pp-worker.pages.dev/sub/uuid your set/?format=clash` to get the subscribe content with `uuid your set` path and `clash` format. content will return with base64 encode.

   note: `uuid your set` is the uuid you set in UUID enviroment or `wrangler.toml`, `_worker.js` file.
   when you set multiple uuid, you can wiill use `https://pp-worker.pages.dev/sub/uuid1/?format=clash` to get the subscribe content with `uuid1` path and `clash` format.(only support first uuid in multiple uuid set)

## multiple port support (Optional)

By default, the port is 80 and 443. If you want to add more ports, you can use the following ports:

```text
http port   --->  80, 8080, 8880, 2052, 2086, 2095
https port  ---> 443, 8443, 2053, 2096, 2087, 2083
```
 
1) Since the IP of the Workers node changes frequently, please do not log in to important accounts on this node
 
2) Since the pages.dev domain has HSTS enabled by default, it cannot use nodes with non-TLS ports

3) if you deploy in cloudflare pages, http port is not supported. Simply add multiple ports node drictly use subscribe link, subscribe content will return all Cloudflare supported ports.

## proxyIP (Optional)

note: `proxyIP` is the ip or domain you want to set. this means that the proxyIP is used to route traffic through a proxy rather than directly to a website that is using Cloudflare's (CDN). if you don't set this variable, connection to the Cloudflare IP will be cancelled (or blocked)...

resons: Outbound TCP sockets to Cloudflare IP ranges are temporarily blocked, please refer to the [tcp-sockets documentation](https://developers.cloudflare.com/workers/runtime-apis/tcp-sockets/#considerations)

## Usage

frist, open your pages.dev domain `https://pp-worker.pages.dev/` in your browser, then you can see the following page:
The path `/uuid your seetting` to get the clash config and vless:// link.
