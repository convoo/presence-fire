# Presence-Fire

<p align="center">
  <img alt="presence-fire" src="PresenceFire400.png" width="300">
</p>

<p align="center">
Simple way to add presence to your app using firebase.
</p>

<p align="center">
  <a href="https://beta.webcomponents.org/element/convoo/presence-fire"><img src="https://img.shields.io/badge/webcomponents.org-published-blue.svg"></a>
  <a href="https://gitter.im/convoo/general"><img src="https://img.shields.io/badge/gitter-join%20chat-brightgreen.svg"></a>
</p>

---

## Install

```
bower install presence-fire --save
```

# \<presence-fire\>

An element that saves the presence of the user at a route and gets all other users at that route.

```html
<link rel="import" href="/bower_components/presence-fire/presence-fire.html">
```

<!--
```
<custom-element-demo>
    <template>
        <link rel="import" href="../polymerfire/firebase-app.html">
        <link rel="import" href="../login-fire/social-login-fire.html">
        <link rel="import" href="../paper-button/paper-button.html">
        <link rel="import" href="../paper-input/paper-input.html">
        <link rel="import" href="../paper-toggle-button/paper-toggle-button.html">
        <link rel="import" href="presence-fire.html">
        <body>
            <template is="dom-bind">
                <next-code-block></next-code-block>
            </template>
        </dom-bind>
        <script>
function _changeRoute(a){
    document.querySelector("#route").value = a;
}
        </script>
        <style>
.photoContainer{
    min-height: 45px;
}

.photo {
    animation: fadein 1.5s;
    border-radius: 50%;
    width: 40px;
    height: 40px;
}

@keyframes fadein {
    from { opacity: 0;}
    to   { opacity: 1; }
}
        </style>
    </template>
</custom-element-demo>
```
-->
```html
<!--What you need:-->
<firebase-app
    name="presencefire"
    api-key="AIzaSyAhoCXxkY-ffNwA_7L7HIwBVpASYj1btNE"
    auth-domain="convoo-login-demo.firebaseapp.com"
    database-url="https://convoo-login-demo.firebaseio.com">
</firebase-app>

<presence-fire
    app-name="presencefire"
    uid="[[user.uid]]"
    photo="[[user.photoURL]]" 
    name="[[user.displayName]]" 
    route="{{route}}"
    status="{{status}}"
    present="{{present}}"
    private="{{private}}">
</presence-fire>

<!--Just for the demo:-->
<social-login-fire 
    twitter 
    app-name="presencefire"
    user="{{user}}">
</social-login-fire>

<div>
    Currently here:<br><br>
    <div class="photoContainer">
        <template is="dom-repeat" items="{{present}}">
            <img src$="{{item.photo}}" alt="{{item.name}}" class="photo">
        </template>
    </div>
</div>

<paper-input id="route" label="Route" value="{{route}}" readonly></paper-input>

<br>

<paper-button raised onclick="_changeRoute('a')">Route A</paper-button>
<paper-button raised onclick="_changeRoute('b')">Route B</paper-button>
<paper-button raised onclick="_changeRoute('c')">Route C</paper-button>

<br><br>

<paper-toggle-button checked="{{private}}">Private Browsing</paper-toggle-button>
```

## Contributing

### Install the Polymer-CLI

First, make sure you have the [Polymer CLI](https://www.npmjs.com/package/polymer-cli) installed. Then run `polymer serve` to serve your application locally.

### Viewing Your Application

```
$ polymer serve
```

### Building Your Application

```
$ polymer build
```

This will create a `build/` folder with `bundled/` and `unbundled/` sub-folders
containing a bundled (Vulcanized) and unbundled builds, both run through HTML,
CSS, and JS optimizers.

You can serve the built versions by giving `polymer serve` a folder to serve
from:

```
$ polymer serve build/bundled
```

### Running Tests

```
$ polymer test
```

Your application is already set up to be tested via [web-component-tester](https://github.com/Polymer/web-component-tester). Run `polymer test` to run your application's test suite locally.