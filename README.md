# open-crd

> A universal toolkit to manage any resources as CRD. say a cloud service, an account on a site or app.
it composite of three parts. A path towards declarative service/api.

1. Describe, communicate with service provider to get an update on state of resources, which may very well be changed without the toolkit's notice. (you changed it on the site/app as you normally do.). after `describe`, toolkit now obtain a latest state of your resources. and the resources will be represented as a bunch of yaml files.

2. Edit, you change the yaml files however you like. Bulk operations regardless the service provider provided or not.

3. Apply, you ask the toolkit to apply accordingly to your service.


## The Architecture

1. Describer
    We need a describer to talk to the service. and some config for it. (like username/password or api token).
    and various api adapters to get state from service.

2. Converter
    We need converter to map api results to declarative state yaml files.

3. Planner
    We need some way to figure out what's the difference between the yaml files user changed and state the service currently at. and output the actions to be made to achieve the target state.

4. Executor
    Actually calling the api and make the changes.