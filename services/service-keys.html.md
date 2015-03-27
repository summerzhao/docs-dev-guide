---
title: Managing Service Keys with the CLI
---

_This page assumes you are using cf CLI v6._

Service Key is a service credentials for a particular service instance, it's a set of key value pairs, such as `password`, `username`, `url`, and other such information are used to allow a service client to bind and use a service.

## <a id='create'></a>Create a Service Key ##

Creating a service key.

<pre class="terminal">
$ cf create-service-key myservice mykey
Creating service key mykey for service instance myservice as me@example.com...
OK
</pre>

## <a id='list'></a> List Service Keys of a particular service instance ##

Listing services keys of a particular service instance.

<pre class="terminal">
$ cf service-keys myservice
Getting service keys for service instance myservice as me@example.com...

name
mykey1
mykey2

</pre>

## <a id='detail'></a>Get the detail of a particular service key ##

Getting the detail credentials of a particular service key, the service key is specified by the name of service instance and service key.
User can specify --guid to get the guid of the service key instead of the credentials.

<pre class="terminal">
$ cf service-key myservice mykey
Getting key mykey for service instance myservice as me@example.com...

{
  uri: foo://user2:pass2@example.com/mydb,
  servicename: mydb
}
  

$ cf service-key --guid myservice mykey
Getting key mykey for service instance myservice as me@example.com...

e3696fcb-7a8f-437f-8692-436558e45c7b

OK
</pre>

## <a id='delete'></a>Delete a Service Instance ##

Deleting a service key. Add option -f to force the deletion without confirmation.

<pre class="terminal">
$ cf delete-service-key myservice mykey

Are you sure you want to delete the service key mykey ? y
Deleting service key mykey for service instance myservice as me@example.com...

OK
</pre>

<pre class="terminal">
$ cf delete-service-key -f myservice mykey

Deleting service key mykey for service instance myservice as me@example.com...

OK
</pre>


