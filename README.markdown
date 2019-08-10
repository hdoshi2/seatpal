# SeatPal

Welcome to SeatPal!

SeatPal allows the user to select seats for a wonderful play.

Tech Stack
-Ruby
-React

Developed by: Hari Doshi


## Setup

### For frontend:

1. `cd` into `frontend` directory
2. Run `yarn` to install dependencies
3. Run `yarn start` to launch the application on `http://localhost:3000`

### For backend:

1. `cd` into `api` directory
2. Run `bundle` to install Sinatra
3. Run `ruby seatpal.rb` to launch the server on port `4567`

## Feature Requirements (Mockup provided doc/)

We want to render the seats that we get from the `/api/seats` endpoint in a 4 by 3 grid.

```
curl localhost:4567/api/seats

[{
  "id": "683ace57-e545-486b-9ce7-2d99b33099de",
  "row": "C",
  "seat": 1
}, {
  "id": "d41d2b86-55e0-4de8-9889-fa9282359f64",
  "row": "A",
  "seat": 1
}, {
  "id": "39429c3a-33ba-4464-ae2c-c4badc5a9f0b",
  "row": "B",
  "seat": 1
}, {
  "id": "bc476090-6ff3-4260-9146-c741ac502614",
  "row": "C",
  "seat": 2
}, {
  "id": "97823eb2-6b27-41c4-8a13-c08458f0a67e",
  "row": "B",
  "seat": 2
}, {
  "id": "fb5e4e1d-4556-4675-b0bf-c5877beb9a2e",
  "row": "A",
  "seat": 3
}, {
  "id": "70fc3df4-f30f-4d44-ad9e-9a945d9cf513",
  "row": "B",
  "seat": 3
}, {
  "id": "f3bcf859-f57d-4765-8270-d2012122ec4c",
  "row": "A",
  "seat": 2
}, {
  "id": "02af0894-420e-4551-9509-f111e9da195d",
  "row": "C",
  "seat": 4
}, {
  "id": "e1ab623e-981e-4c2f-ab4a-d5286d06d077",
  "row": "C",
  "seat": 3
}, {
  "id": "d0960350-bcaa-499e-9e76-6aaa373ab680",
  "row": "B",
  "seat": 4
}, {
  "id": "4e7f69a1-c389-4e7c-b02d-b92764a0b57b",
  "row": "A",
  "seat": 4
}]
```


As the user selects seats we want to list the selected seats on the right side of the screen.

When the user clicks the reserve button, we want to send a post request to `/api/reservations` with the seats that the user selected. The reservations endpoint will return JSON that looks like `{ prize: true|false }`. If prize is true it means that they are our 10,000th customer! In this case we want to show confetti on the screen, [here is a JS library for confetti](https://github.com/wesleycho/confetti.js/), but feel free to use another one if you have one you prefer. If prize is false, we just want to show a normal confirmation message that they're reservation was successful.


```
curl -XPOST http://localhost:4567/api/reservations
{"prize":false}
```

```
curl -XPOST http://localhost:4567/api/reservations
{"prize":true}
```
