# Get Room Messages

The get room messages uses the user id in retrieving the messages sent to the room thereby checking the organization id to know which organization is using the room.

> GET /messages/:room_id/

  
> Note: `you need to create a room for you to get messages of the particular organisation.` 

  
## Path Parameter
A unique ID  of the room is required to locate the messages of the particular room.
  

```sh
/messages/room_id
integer
Required
```

  

## Request

```sh
Bearer [ACCESS_TOKEN]
application/json
```

  

## Responses with sample

  
`200 ok`
>Successfully Get all room messages with status code 200 and returns all room messages in json format.

`example:`
```sh
content-type: application/json
{
    "code": 200,
        "data": [{
           "message":  "Happy mother's day", "created_time":"2018-05-13T06:25:16+0000", 
        "id": "1742085185888234_1648933289336758"
           },
        {
        "message": "Days were gone",
        "created_time":"2018-04-27T02:30:14+0000",
        "id": "1742085185888234 1622033204560100" 
        }]  
}
```
`400 Bad Request`
>This error occurs due to invalid path parameters provided like id

`example:`
```sh
content-type: application/json
{    
    "code": 400,    
    "message": "Bad Request"
}
```

`401 Invalid Access Token`
>Return an error with status code 401 when the access token is missing or invalid.

`example:`

```sh
content-type: application/json
{        
    "code": 401,        
    "message": "Bad Request"
}
```


`500 Internal Server Error`
>return an error with status code 500 which means server error.

`example:`
```sh
content-type: application/json
{    
    "code": 500,    
    "message": "internal server error"
}
```
