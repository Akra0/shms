<!DOCTYPE html>
<html lang="en">
<head>
  <style>
  html {
      height: 100vh;
      width: 100vw;
  }

  @keyframes fadein {
      from {
          opacity: 0;
      }

      to {
          opacity: 1;
      }
  }

  @property --angle {
      syntax: "<angle>";
      initial-value: 0deg;
      inherits: false;
  }

  @keyframes gradient {
      from {
          --angle: 135deg;
      }

      to {
          --angle: 215deg;
      }
  }

  body {
      height: 100vh;
      width: 100vw;
      overflow: auto;
      margin: 0;
      --angle: 135deg;
      animation: gradient alternate ease-in-out 10s infinite;
      background: linear-gradient(var(--angle), #c5c5c5, #3e3d3d);
      background-size: 200%;
      background-position: -100% -100%;
      color: #f00;
      font-family: "Inconsolata", "Cascadia Mono", monospace;
  }

  .centered {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
  }

  #main {
      padding: 2em;
      background: #fff;
      border-radius: 15px;
      box-shadow: 0 0 5px #111;
      animation: fadein 1.5s;
  }

  #logo {
      height: 96px;
      width: 96px;
  }

  p {
      margin: .5em;
      white-space: nowrap;
  }

  h1 {
      margin: 5px;
      font-size: 3em;
      color: #000;
  }

  .warning {
      color: #c83;
  }

  a {
      text-decoration: none;
      color: #0cf;
  }

  input {
      margin: 5px;
      padding: 5px;
      outline: none;
      border: 1px #0000 solid;
      border-radius: 5px;
      background: #333;
      transition: background 1s;
      color: #fff;
      font-family: "Inconsolata", "Cascadia Mono", monospace;
      font-size: 1em;
      text-align: center;
  }

  input:focus {
      border: 1px #222 solid;
  }

  input::placeholder {
      text-align: center;
      color: #aaa;
  }

  input:focus::placeholder {
      opacity: 0;
  }

  input[type="text"] {
      min-width: fit-content;
      width: 20vw;
  }

  input[type="submit"] {
      min-width: fit-content;
      width: 10vw;
  }

  input[type="submit"]:hover {
      background: #444;
  }

  @keyframes fadedeferred {
      from {
          opacity: 0;
      }
          }

      25% {
          opacity: 0;
      }

      to {
          opacity: 1;
      }
  }

  .bottom {
      position: absolute;
      bottom: 4vh;
      animation: fadedeferred 3s;
  }
}
  </style>
</head>
<body class="centered">
  <form class="centered" id="main" action="/gateway" method="GET" autocomplete="off">
  <img id="logo" src="data:image/jpeg;base64,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">
  <h1>SHMS</h1>
  <p>Yay a Shms themed proxy</p>
  <p><a>By The Creator @rom!</a>
  </p>
  <input type="text" name="url" placeholder="youtube.com" required><input type="submit" value="Onward!"></form><p class="bottom"><a href=>Inspierd by Forge!</a></p></body></html>
