# ngHelperAirbrake

Integrate AirBrake into an angular.js application

### Install ng-helper-airbrake
```
bower install ng-helper-airbrake --save
```
Ensure that the dependency entry comes directly after the angular dependency. Are you not sure? Check & modify the bower.json.

### Include the angular module
```javascript
angular.module('appApp', [
    'ngHelperAirbrake'
]);
```
### Register the project id
Airbrake requires a project id and secret. This can be configured via the application start in the run function as follows:

```javascript
.run([ '$airbrake', function($airbrake) {

      // configure airbrake
      $airbrake.setProject('<<PROJECTID>>', '<<PROJECTSECRET>>', '<<EnvironmentOptional>>');

      // configure host (optional step for self hosted environments)
      $airbrake.setHost('https://yourdomain.com');
}]);
```

The Airbrake plugin is not available as long the setProject method is not called. Only when this method is called exception
will be catched from the subsystem.

### Filtering errors
The airbrake module exposes an addFilter method that can be used in the exact same way as [airbrake-js](https://github.com/airbrake/airbrake-js)

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :)

## Contributors

* [Derek Eisenberg](https://github.com/dei79)
* [Stephen Bartlett](https://github.com/srbartlett)
* [Bubl Technology](http://www.bublcam.com/)

## License

[MIT License](https://github.com/ngHelper/ngHelperAirbrake/blob/master/LICENSE.txt)
