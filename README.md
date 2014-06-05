YIICheatSheet
=============

CheatSheet for Yii 1.x

## Active Record


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

### Criteria

```php
  $criteria = new CDbCriteria();
  
  // Select columns example 1
  $criteria->select = array('id', 'username', 'email');
  
  // Select columns example 2
  $criteria->select = "id, username, email";
  
  // Where attribute equals
  $criteria->compare('age', '18');
  
  // to specify another where clause just add another $criteria->compare()
  $criteria->compare('age', '18');
  $criteria->compare('age', '24', 'OR');
  
  $model = MyModel::model()->findAll($criteria);
```


## Command line yiic

### Migrations

For migrations the best place to run yiic is from the app/protected/yiic

#### Creating a migration

```bash
  php yiic migrate create create_user_table
```

##### Running the migration

###### Running the migration up method

```bash
  php yiic migrate up
```

###### Running the migration down method

```bash
  php yiic migrate down
```
