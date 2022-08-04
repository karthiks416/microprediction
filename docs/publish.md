## Publishing a stream

Here's how to add to the list of [streams](https://www.microprediction.org/browse_streams.html). 


## 1. [Python](https://microprediction.github.io/microprediction/publish-using-python.html)

    from microprediction import MicroWriter
    mw = MicroWriter(write_key='YOUR WRITE KEY HERE')
    mw.set(name='my_stream.json',value=3.14157) 
    
See [publish-using-python](https://microprediction.github.io/microprediction/publish-using-python.html) for more utilities and patterns. 

## 2. R 

    library(httr)
    httr::PUT(url = paste0("https://api.microprediction.org/live/", 'my_stream.json'),
                  body = list(write_key = 'YOUR WRITE KEY HERE', budget = 1, value = 3.1457))
       
See Fred Viole's [r_examples](https://github.com/microprediction/microprediction/tree/master/r_examples). 

## 3. Julia 

    r = HTTP.request("PUT", "https://api.microprediction.org/live/my_stream.json";
    query=Dict(
        "write_key" => 'YOUR WRITE KEY',
        value => 3.14157))
    JSON.parse(String(r.body))
    
This example is from [Rusty Conover's Julia Client](https://github.com/rustyconover/Microprediction/blob/master/src/Microprediction.jl).

    
## 4. API 

Send a PUT request to [https://api.microprediction.org/live/my_stream.json](https://api.microprediction.org/live/my_stream.json) with the following parameters in the payload:

   - write_key
   - budget (can just set to 1)
   - value (e.g. 3.14157)

## Retrieving results

See [retrieve](https://microprediction.github.io/microprediction/retrieve.html), after the algorithms have had time to find your stream.  