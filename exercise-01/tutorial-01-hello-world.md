Exercise 1 - Create a Adobe I/O Hello World Action
===========

## Objective

![Image of ex1 outcome](../Resources/ex1.png)  


## Tasks

```diff
- WARNING: PLEASE REPLACE seat-{YOUR_FIRSTNAME}-{YOUR_LASTNAME} with your FIRSTNAME and LASTNAME: Example: seat-john-doe
```
	
1. Go into the `adobe-cif-extension-sample` project
	
	```ruby
	cd adobe-cif-extension-sample/exercise-01
	```
	
5. Create a OpenWhisk Package (make sure to use a format seat-firstname-lastname)
	```diff
	- WARNING: PLEASE REPLACE {YOUR_FIRSTNAME} with your firstname and {YOUR_LASTNAME} with your lastname: seat-john-doe. If not done, you will get conflicting errors**
	```
	
	```ruby
	wsk package create seat-{YOUR_FIRSTNAME}-{YOUR_LASTNAME}
	```
	
	**Expected Output**
	
	```diff
	+ ok: created package seat-{YOUR_FIRSTNAME}-{YOUR_LASTNAME}
	```
	
    Learn more about [OpenWhisk Packages](https://github.com/apache/incubator-openwhisk/blob/master/docs/packages.md)
	
6. Create a action for hello world using a sample provided 
	
	```ruby
	wsk action create seat-{YOUR_FIRSTNAME}-{YOUR_LASTNAME}/hello-world hello-world.js
	```
	
	**Expected Output**
	
	```diff
	+ ok: created action seat-{YOUR_FIRSTNAME}-{YOUR_LASTNAME}/hello-world
	```
	
	Learn more about the [action command](https://github.com/apache/incubator-openwhisk/blob/master/docs/actions.md)
	
7. Execute and see results with params
	
	```ruby
	wsk action invoke seat-{YOUR_FIRSTNAME}-{YOUR_LASTNAME}/hello-world --result --param firstName Gary --param lastName Kirsten
	```
	
	**Expected Output**
	
	```ruby
	{
        "payload": "Hello Gary Kristen"
	}
	```
	
8. Good to know: OpenWhisk Namespace and properties are already deployed for you. Checkout the .wskprop using below command on terminal

	```ruby
	cat ~/.wskprops
	```
	
	Parameters file
	
	>> Try invoking the action using the param-file flag and passing the parameters.json file.
	
	```ruby
	wsk action invoke seat-{YOUR_FIRSTNAME}-{YOUR_LASTNAME}/hello-world --result --param-file parameters.json

	```

9. Good to know: `wsk activation poll` lets you tail the logs	
		
10. Overall outcome

![Image of ex1 outcome](../Resources/ex1.png)  

	

