# Fetch API

## Fetch
~~~javascript 1.6

    # Fetch 참고사항
        - HTTP error 상태를 reject 하지 않는다.
        - 기본적인 쿠키 헤더를 보내거나 받지 않고 credentials 옵션을 이용한다.
        
    # Basic Usage
    
        fetch(<URL of Resource>)
        .then((response) => {
            return response.json() || response.blob() || ...
        })
        .then((json||blob) => {
            let objectURL = URL.createObjectURL(blob)
            myImage.src = objectURL
        })
        
    # Applying Headers
    
        let myHeaders = new Headers()
        
        let myInit = {
            method: 'GET || POST || ...',
            headers: myHeaders,
            mode: 'cors',
            cache: 'default'
        }
        
        fetch(<URL of Resource>, myInit)
~~~

<hr>

## Headers

~~~javascript 1.6

    # Basic Usage
    
        let content = "Hello World"
        let myHeaders = new Headers()
        myHeaders.append("Content-Type", "text/plain")
        myHeaders.append("Content-Length", content.length.toString())
    
    # Checking Header Content (Bool)
        
        let myHeaders = new Headers()
        myHeaders.has("Content-Type") => true || false
        
    # Setting & Getting Header
    
        let myHeaders = new Headers()
        myHeaders.set("Content-Type", "text/html")
        myHeaders.get("Content-Type") => "text/html"
        
    # Delete Header
    
        let myHeaders = new Headers()
        myHeaders.delete("Some Header")
        
~~~

## Type Checking

~~~javascript 1.6
    
    # Check Type of Response Content Type
    
    fetch(Request).then((response)=>{
        
        let contentType = response.headers.get('Content-Type')
        
        if(contentType && contentType.indexOf("application/json") !== -1){
            return response.json()
        }
        else{
            console.log("Content-Type is not application/json")
        }
        
    })
    
~~~

## Body

~~~javascript 1.6

    # Types of Body
    
        - ArrayBuffer
        - Blob/File
        - String
        - URLSearchParams
        - FormData

~~~

