# Adding-content-with-directives-and-modules
Basic example of using an Angular JS directive and an Angular JS module to add HTML component to a page


#### Dependencies:
- angular.min.js

#### Using a directive:

&lt;div ng-controller="appCtrl"&gt;&lt;div app-directive&gt;&lt;/div&gt;&lt;/div&gt;

#### Using a module:

&lt;app-module&gt;&lt;/app-module&gt;

#### template.html:

&lt;p ng-repeat="data in $ctrl.modulecopy"&gt;{{data.name}}&lt;/p&gt;

#### The JS:
````js
angular.module('myApp', [
	'appModule'
]);

angular.module('appModule', []);

angular.module('appModule').component('appModule', {
    
templateUrl: 'template.html',

controller: function appModuleController() {
    
    this.modulecopy = [
        {
        name: 'This content was added using a module'
        }
    ];

}
}).controller('appCtrl', ['$scope', function($scope) {
	$scope.template = {
		name: 'This content was added using a directive'
	};
}])
.directive('appDirective', function() {
	return {
		template:'&lt;p&gt;{{template.name}}&lt;/p&gt;'
	};
});
````
