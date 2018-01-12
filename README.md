# is-connect 

> Check if the internet connection is up

Works in Golang

it's useless as it only tells you if there's a local connection, and not whether the internet is accessible.


## Install

```
$ go get github.com/alimasyhur/is-connect
```


## Usage

```js
import "log"
import "github.com/alimasyhur/is-connect"

func main() {
    //check if online
    if isconnect.IsOnline() {
        //true
    }

    //sample check url http://google.com
    status, message := isconnect.IsReachable("http://google.com")

    if status {
        //true, do operation
        log.Println(message)        
    }else {
        //get error message
        log.Println(message)
    }
}
```


## API

### isOnline()
>
Default TImeout: `5000`

Milliseconds to wait for a server to respond.

Internet Protocol version to use. This is an advanced option that is usually not neccessary to be set, but it can prove useful to specifically assert IPv6 connectivity.

## How it works

The following checks are run in parallel:

- Retrieve [google.com](https://google.com) via HTTPS

When the first check succeeds, the returned Promise is resolved to `true`.

## License

MIT © [Sindre Sorhus](https://sindresorhus.com)