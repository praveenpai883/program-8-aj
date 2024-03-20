<!DOCTYPE html>
<html>
<head>
 <title>Login Form with Validation</title>
 <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"> 
 </script>
</head>
<body ng-app="myApp">
<div ng-controller="LoginController">
 <h2>Login Form</h2>
 <form name="loginForm" novalidate>
 <label>Username:</label>
 <input type="text" ng-model="user.username" name="username" required>
 <span ng-show="loginForm.username.$error.required && 
loginForm.username.$dirty">Username is required.</span>
 <br>
 <label>Password:</label>
 <input type="password" ng-model="user.password" name="password" ngpattern="/^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$/" required>
 <span ng-show="loginForm.password.$error.required && 
loginForm.password.$dirty">Password is required.</span>
 <span ng-show="loginForm.password.$error.pattern && loginForm.password.$dirty">
 Password must be alphanumeric and at least 8 characters long.
 </span>
 <br>
 <button ng-click="login()" ng-disabled="loginForm.$invalid">Login</button>
 </form>
 <div ng-show="isLoggedIn">
 <p>Login successful! Welcome, {{ user.username }}!</p>
 </div>
</div>
<script src= “Program8.js”> </script>
</body>
</html>
Program8.js
 var app = angular.module('myApp', []);
 app.controller('LoginController', function ($scope) {
 $scope.user = { username: '', password: '' };
 $scope.isLoggedIn = false;
 $scope.login = function () 
 $scope.isLoggedIn = true;
 };
 });
