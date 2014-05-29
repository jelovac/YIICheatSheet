YIICheatSheet
=============

CheatSheet for Yii 1.x

Active Record
-------------

### Insert record

```php
  // Example 1
  $model = new MyModel();
  $model->attributes = $_POST('MyModel');
  $model->save(); // returns boolean
  
  // Example 2
  $model = new MyModel();
  $model->username = $_POST('username');
  $model->email = $_POST('email');
  // etc..
  $model->save(); returns boolean
  
```

### Update record

```php
  // Example 1
  $model = MyModel::model()->findByPk($id); // Get the model by ID
  $model->attributes = $_POST('MyModel');
  $model->save(); // returns boolean
  
  // Example 2
  $model = MyModel::model()->findByPk($id); // Get the model by ID
  $model->username = $_POST('username');
  $model->email = $_POST('email');
  // etc..
  $model->save(); returns boolean

```

### Delete record

```php
  // Example 1
  $model = MyModel::model()->findByPk($id);
  $model->delete();
  
  // Example 2
  MyModel::model()->deleteAll($condition, $params);
  
  // Example 3
  MyModel::model()->deleteByPk($key, $condition, $params);
```
