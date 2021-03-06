# Angular 103

## AngularFire

Follow the general guidelines in the [AngularFire Quick Start](https://www.firebase.com/docs/web/libraries/angular/quickstart.html), but be sure to use your Bower dependencies, and not their CDN links.

Use [Firebase Arrays](https://www.firebase.com/docs/web/libraries/angular/guide/synchronized-arrays.html) instead of objects. They are easier to work with for your browser applications.

### Loading songs

To start using AngularFire, you need to include it as a dependency to your application.

```js
var app = angular.module("SongApp", ['firebase', 'ngRoute']);
```

Now you can include `$firebaseArray` as an object to use in your controllers.

```js
app.controller("SongCtrl", 
  ["$scope", 
   "$firebaseArray", 
  function($scope, $firebaseArray) {

  // Just like in the RequireJS version of Music History, make a reference
    var ref = new Firebase("https://nss-demo-instructor.firebaseio.com/songs");

  // Instead of snapshot.val(), use this syntax to get songs
    $scope.songs = $firebaseArray(ref);

  }
]);
```

### Showing individual songs

```js
app.controller("SongDetailCtrl",
  ["$scope", "$routeParams", "$firebaseArray",
  function($scope, $routeParams, $firebaseArray) {
    $scope.selectedSong = {};
    $scope.songId = $routeParams.songId;

    var ref = new Firebase("https://nss-demo-instructor.firebaseio.com/songs");
    $scope.songs = $firebaseArray(ref);

  // Make sure you use the $loaded promise handler, which waits
  // for all songs to be loaded from the reference before you try
  // to grab the record the user wanted.
    $scope.songs.$loaded()
      .then(function() {
      // The $getRecord method on a $firebaseArray is very useful
        $scope.selectedSong = $scope.songs.$getRecord($scope.songId);
      })
      .catch(function(error) {
        console.log("Error:", error);
      });
  }]
);
```

### Adding a new song

> **partials/song-form.html**

```html
<section>
  <div>
    Song name: <input type="text" ng-model="newSong.name" />
  </div>
  <div>
    Album Name: <input type="text" ng-model="newSong.albumName" />
  </div>
  <div>
    Album Year: <input type="text" ng-model="newSong.albumYear" />
  </div>
  <div>
    Artist: <input type="text" ng-model="newSong.artist" />
  </div>
  <button ng-click="addSong()">Add Song</button>
</section>
```

> **app/controllers/SongFormCtrl.js**

```js
app.controller("SongFormCtrl", ["$scope", "$firebaseArray",
  function($scope, $firebaseArray) {

    var ref = new Firebase("https://nss-demo-instructor.firebaseio.com/songs");
    $scope.songs = $firebaseArray(ref);
    $scope.newSong = {};

    $scope.addSong = function() {
      $scope.songs.$add({
        artist: $scope.newSong.artist,
        name: $scope.newSong.name,
        album: {
          name: $scope.newSong.albumName,
          year: $scope.newSong.albumYear
        }
      });
    };
  }
]);
```