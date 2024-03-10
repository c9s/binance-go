binance-go
=========================================================================

binance-go is an api package for binance API.

the API methods are not manually written, which are generated with requestgen <https://github.com/c9s/requestgen>.

## SYNOPSIS

```go

import (
    "github.com/c9s/binance-go/binanceapi"
)

func main() {
    key := os.Getenv("BINANCE_API_KEY")
    secret := os.Getenv("BINANCE_API_SECRET")

    client := binanceapi.NewClient("")
    client.Auth(key, secret)

    req := client.NewTransferAssetRequest()
    req.Asset("BTC").
        FromSymbol("BTCUSDT").
        ToSymbol("BTCUSDT").
        Amount("0.01").
        TransferType(TransferAssetTypeIsolatedMarginToMain)
    res, err := req.Do(ctx)
    if err != nil {
        panic(err)
    }
    fmt.Printf("%+v", res)
}
```

## LICENSE

MIT License

