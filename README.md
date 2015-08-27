Track this issue [https://github.com/jspm/jspm-cli/issues/1068](https://github.com/jspm/jspm-cli/issues/1068).



See my repositories [jspm-issue-03-application](https://github.com/ncochard/jspm-issue-03-application) and [jspm-issue-03-module](https://github.com/ncochard/jspm-issue-03-module).

[jspm-issue-03-application](https://github.com/ncochard/jspm-issue-03-application) is an application written using [JSPM](https://github.com/jspm/jspm-cli) that has a dependency on [jspm-issue-03-module](https://github.com/ncochard/jspm-issue-03-module).

[jspm-issue-03-module](https://github.com/ncochard/jspm-issue-03-module) only has one JavaScript file `index.js` that is exporting one `default` function.

	export default function(){
		return "Hello world...";
	}

From the application, I should be able to reference it using the following syntax, but `x` is always null.

    import x from 'jspm-issue-03-module';
	(function() {
		console.log(x);//ERROR: x is null
	})();

However, if I import the `/index` module directly, it works.

    import y from 'jspm-issue-03-module/index';
	(function() {
		console.log(y);//y is not null
	})();

Is that a bug in SystemJS?
