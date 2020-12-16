# DIksha JWT 2.0

> A tool for copy pasting jwt/`x-authenticated-user-token`

# Quick Start 🚀

### Available API's
```
Request body:
      POST http://localhost:5000/api/v1/pre_prod/get_jwt
      {
          "email":"abc@xyz.com",
          "password":"********"
      }

Response body:
      {
        "jwt":"[x-authenticated-user-token-here]"
      }
```
```
Request body:
      POST http://localhost:5000/api/v1/prod/get_jwt
      {
          "email":"abc@xyz.com",
          "password":"********"
      }

Response body:
      {
        "jwt":"[x-authenticated-user-token-here]"
      }
```

### Install server dependencies

```bash
npm install
```

### Postman setup
**Copy** the following script
```bash
pm.test("Extract jwt token",  ()=> {
    var jsonData = pm.response.json();
    console.log('jsinData',jsonData);
    if(jsonData.jwt!== "undefined")
        pm.globals.set("x-auth-token", jsonData.jwt);
    else console.log("LL");
});
```
Follow the instructions below to **Paste** it in the postman
```bash
1. Open postamn desktop
2. Navigate into Tests section
3. Paste the copied script
4. Save the route with your convinient name
5. Your done!
```
---
### Usage

## Run the saved route once in a day [As the session expires after 12hrs]
```bash
POST {REQUEST TO SAVED ROUTE}
```
