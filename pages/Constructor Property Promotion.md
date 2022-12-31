- ```php
  // php 7.4
  class User {
  	public string $firstName;
    	publich function __construct(
        string $firstName
      ) {
        $this->firstName = $firstName;
      }
  }
  ```
-
- ```php
  // php 8.0
  class User {
  	public function __construct(
  		public string $firstName,
  		public string $lastName
    ) {}
  }
  ```
-