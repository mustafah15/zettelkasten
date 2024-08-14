---
tags:
  - tools
related: "[[PHP]]"
type: permanent
---
implementing an array of objects can be tricky in PHP since it does not support generics, 

there are three solutions that I can see so far 

- one is to implement `ArrayObject` class to your type for example 

```PHP
<?php

class UserCollection extends ArrayObject {
// same as push
	public function append(User $user): void()
	{
		///
		parent::append($user);
	}
}

```

- using collection package by ramsy which somehow has workaround to implement generics
- 
