- you can match (switch case) between item and value
- ```php
  $type = match($className) {
    'Converstation' => 'conversation_started',
    'Reply' => 'replay_started',
  }
  
  ```
- depend on the `$className` value you will get the type
  if it's `Conversation` the `$type` will be assigned to `converstation_started` if the `$className` value is `Reply` the `$type` will be equal `replay_started`
- you can consider this as syntax suger as well
-